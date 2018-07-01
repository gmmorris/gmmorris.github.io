---
layout: post
title:  "Simmer.js: A Javascript reverse CSS selector engine"
description: "How I designed a Javascript library for calculating the CSS selector of an element on an a webpage"
date:   2015-07-26 14:00:00 +0100
icon: stream
---
{::options parse_block_html="true" /}
<section class="cl2">
As Front End developers we use CSS selector engines all the time. Most commonly, Sizzle, which is baked into jQuery.
The selector engine provides us with a comfortable way to search for elements on the page in the same way as we’re already used to doing in our stylesheets, which makes it simple for us to wrap our brain around.

But what happens when instead of having a selector in hand and finding it’s corresponding element on the page, what I have is the element and what I want is a corresponding CSS selector?
</section>

### tl;dr

> I’ve built and open sourced an engine which generates a CSS selector for an element on the page so that you can persist it and find it later, and its on Github at [SimmerJS](https://github.com/gmmorris/simmerjs).

### But why?

<section class="cl2">
Why indeed? Well, why not?
There are many situation which I can think of in which we would want to translate an element to a persistable selector.
The specific reason I had to develop this was a project I worked on a while back for an AB testing company. This company, which has now sadly gone the way of all flesh, provided it’s users with the ability to mark parts of their page and then generate scripts which would find those parts on every page load and replace them with some predefined content.
This was done on the Front End for many reasons, which I won’t go into, but what is important to note is that this tool could be used anywhere on the web, ranging from simple static landing pages to complex web apps- hence the saying *It’s A Jungle Out There* was more accurate than ever for this particular project.
</section>

### The Concept
<section>
Approaching the challenge of building this reverse selector engine, I made note of several issues I’d have to deal with:

1. The pages in which this engine would be used could be dynamic, so identifying the element consistently was going to be very tricky. Any selector would have to be specific enough to consistently choose the right element over and over again, but it wold also need to be flexible enough to deal with changing pages with revolving DOM structures (a very common occurrence on advertising landing pages which often contain dynamic ad sections).

1. The selectors created by this engine would have to be relatively backwards compatible because many of our clients were targeting a very wide audience with relatively older browsers, so we’d have to keep our usage of CSS3 down to a minimum, and always opt where possible for simpler selectors.
This also meant that we need to take into account how quirky some browsers are in regards to CSS selector parsing, such as broken nth-child selectors in older versions of IE.

1. We would often have to run our components on auto-generated HTML pages or pages maintained by people whose understanding of HTML was mediocre at best, hence we would have to deal with malformed HTML (to a point), getting around broken tags or duplicate IDs on the page.
</section>

## The Challenge

The way to approach finding a unique selector for an element is to find a balance between the most specific way of describing an element to the one with the least number of moving parts.

To understand what I mean, lets look at these two CSS selectors and associated DOM:

{% highlight html %}
<div id="new_panel">
  <div>
      Lorem ipsum...
  </div>
  <div class="blurb">
    <div>
      Lorem ipsum...
      <div>
        <em>This is what we're doing!</em>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}
{% highlight css %}
#new_panel .blurb em {
  
}

#new_panel > div.blurb > div > div > em {
  
}
{% endhighlight %}

<section class="cl2">
It is very clear that if the element we’re trying to parse is the **em** element then both of those selectors will work, but knowing that the first is shorter (less elements in the query) we have a little more wiggle room for the danger of that DOM being changed by some dynamic content.
That said, it is also true that the shorter selector is also less specific, and is more prone to becoming invalid if the dynamic content generates some element on the page that happens to answer to the same selector.

This balance, between specificity and flexibility, is a tough nut to crack, but I think I’ve managed to achieve a working one. The current implementation, which I’ll describe in a moment, has been used on hundreds of sites and has performed at a very satisfactory level. For the vast majority of pages and tests we managed to achieve very predictable results.
</section>

## The Building Blocks

<section class="cl2">
At first, the process of calculating this well balanced selector wasn’t as clear as I’d thought it would be when I first started.
Like every Front End developer I knew that different CSS selectors have different strengths. For example I knew that an ID is stronger than a class and that a selector consisting of a class and a tag was weaker than two class, but I wasn’t sure how exactly that calculation is done and I had to make sure this calculation is done to the letter, otherwise I might end up with a result which is different than that which the selector engine would actually need when deciphering the selector later.

For this I had to dig into the actual spec for CSS. Something I never thoght I’d actually need to do.
Luckily for us, the spec is actually [very clear and readable](http://www.w3.org/TR/css3-selectors/#specificity) in regards to calculating what we call a selector’s **Specificity weight**.
The Specificity Weight is the score we give a selector by which the browser can then decide which CSS selector “wins” when choosing how to style that element.
In our case we don’t need to choose between two competing selector. What we need is to find a selector which is specific enough to narrow down a whole document to a specific element of interest.
</section>

Essentially the guideline for calculating specificity is this:

1. IDs are worth 100 point each.
1. Classes, attributes and pseudo classes are worth 10 points each.
1. Tag names and pseudo elements are worth 1 point each.

To be accurate, as my Friend [Ronny O](https://github.com/RonnyO) (of [Really Good](http://www.reallygood.co.il/)) likes to remind me, this isn’t a standard Base 10 system (you can [learn more about that here](https://css-tricks.com/specifics-on-css-specificity/)) but for the sake of this article it simplifies the explanation.

Knowing that this is the hierarchy of specificity really simplifies things, because it means that if we can generate a selector using an ID or even a pair of IDs, then we should have a winner. It also tells us that if we need to resort to a selector made out of a bunch of classes we’ve got a very weak and breakable selector.

## The Algorithm

The sequence for finding the most specific selector while still maintaining a less breakable structure boils down to the following

1. HIERARCHY = A stack of the element’s hierarchy, climbing up the DOM tree
2. For each element in the HIERARCHY analyse the following in sequence:
  1. Check for an ID
  2. Check for unique Attributes
  3. Check Tags
  4. Check sibling relations
3. Merge the resulting stack into a single CSS selector

Seems simple enough, right? Well, not quite.
Here are some notes about this sequence:

### Hierarchy

<section class="cl2">
Lets start by looking at the hierarchy we build.
If you’ve looked at the library you may have noticed we have a **depth** configuration value, which by default has the value **3**.
This means we will, by default, only look at the element’s parent and grand parent when calculating the selector.
I found this to be the best depth simple pages but on our production version for the AB testing component we actually expanded that to a depth of **6** because we found that gave us the best balance between specificity and flexibility. The reason we had to climb so high was due to most of our clients using very “semantically bad” web pages, with tables in tables in tables, which meant they often needed a selector for a TD element with no classes or IDs on it’s ancestor row and table.
</section>

### IDs

<section class="cl2">
Checking for a ID on an element in the hierarchy seems straight forward enough, but as I mentioned — its a jungle out there. More often than not we fond that people do not adhere to the whole *only one unique element to an ID* *paradigm*.

Checking for a ID on an element in the hierarchy seems straight forward enough, but as I mentioned — it’s a jungle out there. More often than not we fond that people do not adhere to the whole *only one unique element to an ID* *paradigm*.

Though that may seem ridiculous it actually is a serious problem, because if you have two elements with the same ID you may think you have a specific selector in hand, but infact, it’s useless. So when using an ID you also need to check it’s uniqueness.

You may have noticed we check for unique attributes before testing for classes. This may seem like a surprising choice, but it is actually for a very simple reason — unique attributes, such as a unique HREF or SRC attribute are more common than a unique class. Since classes are by their very nature reusable, it is actually unlikely to find a unique class on an element.
</section>

### How far do we go?

Another thing to note about the algorithm is that, in theory, it could end up with a very complex selector which breaks our need for flexibility and simplicity in our ideal selectors.

To get around this we have specified another configurable property called **specifictyThreshold**. This threshold is esentially the minimum specificity weight we need our selector to reach before we say enough.


<section class="cl2">
If, for example, I find a selector which consists of a unique ID on the page, then I have a specificity of 100 points. This means that if I set my threshold to 100 points, the engine will deem this selector as *specific enough* to quit the parsing process:

```css
#myUniqueElement
```
</section>
<section class="cl2">
That is, assuming, that the IDed selector is specific enough to provide us with the original element. If, for example, the ID isn’t on our element, but rather on our element’s parent, we may need another layer in there — such as the element’s tag, and we’ll finish with a elector worth 101 points in specificity, such as:

```css
#myUniqueElement > em
```
</section>

### Sibling relations
The last point I’d like to point out is sibling relation selectors, such as ***:nth-child(x)*** or ***:nth-of-type(y)***.

<section class="cl2">
These selectors may seem the ideal selectors for this kind of unique selector generation, but in fact, I found these to be severally lacking.

The main reason is that these are actually very unreliable on malformed pages. In fact, so much so, that I had to disable *:nth-of-type* all together!

This is why we keep these selectors to the end, as a sort of last resort, and we avoid them when possible.

There are several situations where these selectors break down. These are often browser specific problems, rather than a general rule and you may be surprised to hear that IE is far from being the only culprit, with Safari, and even Firefox, actually giving me much grief as well.
</section>

Here are several examples:

1. When you have a self closing element, such as a ```<br/>``` the behaviour is very erratic, with some browsers skipping these element when they aren’t closed properly, which can then, accidentally, be skipped by their implementations of *:nth-of-type*.

1. When a block element is placed in a non block element, such as a div inside of a paragraph, some browsers will eject the div from the paragraph, while others might duplicate the paragraph element, placing it twice on the page. Which seems to effect the pseudo-selectors worse than the class and ID selectors, as the browsers usually skip the duplication of these attributes.

```html
<p> <div>Lorem Ipsum</div>
</p>
```

Might become:

```html
<p></p> <div>Lorem Ipsum</div>
<p></p>
```

There are several more problems with these selectors which make them less reliable than their counterparts.

## The vetting process

<section class="cl2">
At this point there was still one more element to this puzzle. How would this engine actually check which selectors work best?
Sure, we can calculate a very specific selector, but that doesn’t mean it really is unique.

To address this issue I built Simmer with an internal mechanism for finding the best possible query engine for it to use.
We knew that we’d be packaging jQuery with both our AB testing manipulation library and Simmer’s editing environment, so we knew that we could count on the same algorithm being used wherever we used Simmer, but I also wanted the engine to be a comfortable engine to drop-in in other projects.

To that end Simmer has been equipped with a “super complex mechanism” — it asks the page what it can use.
It looks around for a jQuery engine and if it find one — it uses that. If it can’t find jQuery it searches for a stand-alone Sizzle engine. If that can’t be found either it defaults to the browser’s *document.querySelectorAll* implementation.

It also provides a configurable callback for querying in case the developer want to use an other DOM querying language.
</section>

## Final thoughts
<section class="cl2">
I loved writing Simmer. It was a fun and challenging project, but I don’t think it is anywhere near done. I still have so many ideas, such as expanding configuration to give developers a higher level of control over the final selectors and allowing developers to plug in their own parsing functions to expand support for custom doctypes and tags (React module and JSX support, perhaps?).

As CSS3 gains wider adoption (we’re almost there now, aren’t we) additional selectors could be, and should be, added into the mix. Also, as Selector Level 4 (wrongly referred to as CSS4, while in is in fact extensions to CSS3) gains adoption we’ll need to add these too.

I’ve been involved in two companies that needed this tool, so I have a sneaky suspicion there is more need for Simmer than initially meets the eye. Though legal realities forced me to set Simmer aside for a while, it is now officially Open Sourced and available for usage, so I can finally put the effort into it that it deserves.
I hope more people find this library useful and find an interest in helping me take this code base to the next level.
</section>

The [Github repo](https://github.com/gmmorris/simmerjs) is waiting for you!
