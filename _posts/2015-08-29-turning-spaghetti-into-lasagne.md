---
layout: post
title:  "Turning Spaghetti into Lasagne"
date:   2015-08-29 13:10:00 +0100
icon: seedling
---
{::options parse_block_html="true" /}
<section class="cl2">
Just over a year ago I started a project which I went into thinking ‘I’m not sure how to do this’ and now, a year and a half later, it is finally almost done and I find myself reflecting on what I’ve learned from the process.

I thought I’d share a few of these lessons, as perhaps, someone else might find them relevant to their job as well.
</section>

## What was the job?

<section class="cl2">
I’ve been doing Web Development for about 12 years now, and during that time I’ve gone back and forth between the Front End and Back End of things, but since my stint as Pluralis’s Senior Front End developer I’ve found myself gravitating heavily to the client-side.

Just over a year and a half ago I took the role of Lead Front End Architect for Loveholidays.com. Yes, thats an explosive title that means absolutely nothing other than the fact that I am now responsible for anything relating to the e-commerce company’s actual website.

In essence I was hired because there was a growing feeling in the company that the Front End was becoming the *weakest link* in the company’s codebase, and as the company was in the early stages of a mass expansion (in my time in the company, so far, we have grown from 15 employees to over 180) the CTO wanted to make sure it wasn’t the Front End that caved under the pressure.
</section>
### The Challenge
<section>
In the year and a half prior I had been working as a freelance consultant for multiple companies, mostly helping them figure out Front End architectures for their greenfield projects.
This challenge was going to be quite different for several key reasons:

1. The site was already up and running, serving high traffic, generating revenue and there was a fear that a major overhaul of the codebase could do more harm than good.
1. The company was, and is, growing at a rapid pace and there was no time to *take a year off dev for a rewrite*. Any rewrite would have to be done in conjunction with product development.
1. Like any startup environment the product had gone through many different prototypes, contradictory directions and an overall approach of “duct tape it and deploy it”.
1. There was never any Front End leadership in the company, and over 5 years the company had had multiple Front End developers, many of which were contractors with contradictory approaches.
</section>
<section class="cl2">
The codebase was, to put it mildly, Spaghetti.
I'd like to stress though, that this is OK. Much has been said about startups finding the balance between writing clean code and finding business success.
I believe it's virtually impossible to find success in business without making serious concesions in terms of clean sustainable code. But once you have found a stable business model, it's important to face the mess and make it clean and hence sustainable.
Anyway, at the time of my arrival, we were at the point where the company needed to shift from "fast and messy" to "fast and sustainable" and that would mean slowing down abit.

Back to the code.
When I say Spaghetti, I don’t mean mild problems like “tight coupling”, which would imply a pile ofSpaghetti which fell off the plate.
No, when I say Spaghetti, I mean more like *Four different types of Pasta, one of them severally overcooked into a mush, tossed around by your two toddlers and smeared on the walls; sauce and all*.
OK OK, now I **know** I’m stepping on toes… and stomping on them.. but it really was that bad.
</section>

### The key problems in the Front End code
<section>
1. Almost no compartmentalization of the code. Most of the code was in variables on the global scope. That which wasn’t, was defined in two separate package libraries — one being Require.js (and an old outdated version, at that) and the rest was in some kind of in-house attempt at MVC which didn’t do much of a job in separating concerns as the definition functions shared a scope.

1. Components all communicated through document level event triggers on the document. So you never knew which component was talking to which and when. Try debugging that.

1. A rapidly evolving product led to a lot of redundant code which didn’t actually do anything, but was none the less, in the codebase. This also led to a lack of separation of concerns with different code, effectively, doing the same thing.
</section>

<section class="cl2">
I’m sorry if I sound harsh, especially considering I’m talking about what is now *my codebase*, but I have to respect the company’s CTO for identifying and flagging this problem and prioritising it enough to push for the company investing time and money into rewriting the codebase before it broke.

And now, a year and a half later, there is (almost) no legacy code left on the site, the whole site has been rewritten, with no downtime and with rapid product development.
</section>

## So, what have we learned?

So how did we do it? Well, here are the lesson we learned, which also explain how we did it.

### First Lesson: Don’t sell a rewrite, sell a feature

<section class="cl2">
The CTO and I realised that selling a rewrite to a non techie CEO would be no easy feat. To do so we would have to provide a real, business oriented, added value to rewriting the code.
Very early on we picked up on the CEO’s interest in improving the company’s revenue by A/B testing different portions of the site. It was also clear to me, based on my experience with Pluralis, that achieving this with the current code base was nearly impossible.

Hence, selling a rewrite of components throughout the site, with the express intention of AB testing their functionality would be easier to sell to the CEO.
We explained what we were doing, and that it would allow us to both develop new functionality and provide an ability for A/B testing but that due to our need to improve the quality of the codebase, it might take a little longer than planned (and with a few late nights we could cram in more than expected).

Understanding that *quality* is important, in addition to the *revenue* growth and *functionality* improvements, we found selling the rewrite a rather easy (even if lengthy) process.
</section>

### Second Lesson: Don’t rewrite pages, rewrite functionalities

<section class="cl2">
The first stage in rewriting the site was to start turning our Spaghetti into Lasagne.
To avoid a clash between our new code, which much of it would have to use similar (if not identical) module names and components to the legacy code, we would use [The Modularizer](http://gmmorris.github.io/Modularizer/) which would allow us to sandbox our new architecture and slowly grow it until it effectively takes over the whole site.
You can read more about this component [here](https://medium.com/@chekofif/why-on-earth-would-you-create-yet-another-package-manager-for-javascript-a5c5a232b3f).

Once in place we could start building a proper MVC layered architecture to build our site on top of.

Our Lasagne is made out of a stack of components (what is commonly referred to as N-Tier), layered on top of each other (hence, the Lasagne) to allow a logical progression and separation of concerns.

In effect, what this allowed us to do is convert pieces of the site’s functionality, one by one, stripping them out of the old legacy code and inserting new components in their place, providing a unified way of communicating between the two layers, but more on that in lesson three.
</section>

### Third Lesson: Analyse the legacy codebase’s weakness and exploit it

<section class="cl2">
The legacy codebase, with its many shortcomings actually provided us with one benefit. The usage of document level events to communicate between components, which is a very unmaintainable way of managing communication between components, is also very loosely coupled.

What I mean by that is that if a component, lets call it the **StateController**, needed to access the component in charge of calculating a navigation state, lets call it the **NavState**, it would do so by triggering an event on the page like so:
</section>

```javascript
var StateController = new function(){
    this.GetState = function(){
        $(document).trigger('navestate:giveMeTheState',this)
    };
    this.hereYouGo = function(navState){
		  // Do something with navState
    };
};

var NavState = new function(){
    var myNaveState = { nav : 'state' };
    $(document).on('navestate:giveMeTheState',function(e, giveItTo){
        giveItTo.hereYouGo(myNaveState);
    });
};

StateController.GetState();
```

<section class="cl2">
In turn, the NavState would then answer this document level event.
Very unmaintainable, but for us, this was actually a huge benefit!
We could build a new NavState object, wrap it in our new architecture, and then tap into the same document level event communication to communicate with legacy components, such as the StateController, until such time as we get the chance to rewrite said StateController, at which point we could change their communication to a more logical and maintainable method.

That said, obviously, we didn’t want our components using a global messaging method like that, because that would mean us rewriting our code into the same mess we were trying to escape.
Which leads me to the next lesson.
</section>

### Fourth Lesson: If its external, only reference it in one place

<section class="cl2">
Like most N-Tier architectures, at the bottom, we have a layer of controllers and routers, which provide us with the key logical tiers of the code.

**Thats a lie though**, because it isn’t really the bottom. 
Under that layer there is another layer — thats the library layer. The layer of external components we import and use to avoid writing everything from scratch our selves.
One of the lessons I learned early in my career, obviously the hard way, is that if you use a library it might, very likely, become a hindrance when your functional requirements diverge from the library creators’ assumptions.

Sometimes this will lead you to replacing the library with another one, or, more likely, you’ll have to hack around it’s functionality to support your own evolving requirements.

To provide us with a easier way to handle this kind of issue, we have inserted another layer between our controllers — our *engines*.

An engine is a component that separates out application from a library. All (or almost) library functionality goes through an engine, which means we have one single entry point to any external service or functionality, and hence, if (and when) a need for the removal of a library or a shim around it’s behaviour arrises — we only have one place to make the required changes.

Remember our document level event problem? How did we approach it? Well, we treated it like an external library.
A special component, called the **LegacyProtocol** was created. It would be the entry point for every communication with the legacy environment and it’s messy document level event methods. Any component in the new architecture interested in communicating with legacy components would use the protocol to setup and use that connection.
Hence, once we were ready to rewrite a component, we knew exactly where its communication was going and coming from, which made it much easier to remove later.

When we thought we’d finished our rewrite we checked the protocol to make sure no communication was still going through it. Now we could be certain no more legacy functionality was still being plugged into and we removed the protocol. Happy days!
</section>

## Whats next?

<section class="cl2">
There are actually more lessons we’ve learned, but I feel this article is long enough, so we’ll leave those for another day.

The next step for us though, is advancing our codebase to an even better place. The continued growth of the company seems unavoidable and one of our challenges now, like most tech companies, is recruitment.

Recruiting good people is very hard, and one of the key requirement good developers have of their employers is this- *I don’t want the codebase to piss me off*.
If it is a nightmare for me to work with your code, I need to either get the opportunity to fix that or I don’t want to be part of the company.

I’m happy to announce that the code no longer pisses me off. I love it. Its elegant, maintainable and most of all — built for 2015.
But now, we want it to grow. No more *Code of 2015* but rather, *Code of 2017*.
For that to happen we’re now dipping our feet in the deep waters and experimenting with moving our modules from the Modularizer’s capable hands, into those of ES2015's module system along with Babel to use them in our browsers. We’re starting to convert our views from Backbone views into React views and we’re looking into more technologies that are meant to both make our code more advanced and to assist in exciting our existing, and hopefully our future, developers on their day to day tasks.
</section>

**Exciting days ahead!**
