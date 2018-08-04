---
layout: post
title:  "Betting On Reason"
date:   2018-07-14 15:21:00 +0100
tags: javascript, reasonml, ocaml
icon: user-astronaut
description: "Why I chose to bet on Javascript and why I'm now betting on ReasonML"
banner: banner-arrowhhead
banner-desc: "The Arrowhead"
banner-img: "/assets/img/banners/arrowhead.png"
banner-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14598153437/"
---
{::options parse_block_html="true" /}
<section class="cl2">
Approximately a decade ago I found myself at a sort of crossroads.  
I was about to reach my notice period and was contemplating my options.

Having accumulated just over seven years with my first employer, during which I had spent my time predominantly building applications on **Microsoft's .Net framework**, it felt like I shhould broaden my horizons and explore other options.
</section>

## My first job search
<section>
As I began to assess what the Tel Aviv tech scene had to offer, I found most employers didn't care as much about the specific languages I had worked in, as in my ability to learn and grasp the basic grammar of their chosen flavour.  

I had several offers on the table and chose to go with the company that offered me a trifecta of tech stacks to play around with - these three were **PHP**, **Java** and **Javascript**.
Not much is left of it these days, but in its heyday, _Metacafe_ had gained the reputation amongst junior engineers as an excellent place to learn, and has since left behind a strong legacy of engineers throughout the industry who I still run into from time to time.

It really did prove to be a great school and really exposed me to both the benefits and downsides of those different stacks.
</section>

<section>
Sadly my time at _Metacafe_ was cut short by the company's decision to relocate its R&D department to the United States, at which point I found myself yet again having to consider my options.  
The difference this time was that I had now amassed experience in three different verticals of the software engineering practice:
1. I had worked on building systems in staticly & strongly typed languages, building systems which were intended to run on large and powerful servers - what we would colloquially refer to as *Back End Development*.
2. I had worked in environments of fast paced iteration over various online user interfaces - what we would colloquially refer to (in those days, as that has changed somewhat), as *Web Development*
3. I had worked on a variety of approaches to writing code which was intended to run inside of the web browser itself on the end user's machine - what we would today refer to as *Front End development*, but which was mostly referred to at the time as just *Front End*, as it wasn't considered development. Not really.

I had now reached a point where my skillset as a generalist meant I could easily find work, but I constantly felt I was a step behind all of the established developers around me. They all seemed to know so much and that caused my imposter syndrome to kick into high gear.  
I came to the conclusion that it was time for me to choose a specialism. A focus.
</section>

### Choosing a specialty
<section>
Considering the three verticals I had gained experience at, it was clear that there are two good choices and one risky one.

If I chose to focus on *Back End Development*, I had reasoned, I will have plenty of work, as servers have played a pivotal role in most forms of software engineering for as far back as I care to remember. A safe bet, if you ask me.

If I were to chose *Web Development* then surely I'll have work for many years to come. At that time the web had already been established as the biggest revolution of modern times, with its usage becoming ubiquitous and mostly accepted by society as an integral part of life.  
Facebook hadn't yet broken out into my parents' generation, but all Millenials were already on board, and was famously built in the very language I had experience with - **PHP**, so it seemed like a logical choice as well.

Then there was *Front End*.

I'll never forget how aggressive the _gate keepers_ in the early days of my career were whenever the topic of **Javascript** came up.  
The profanity, the ridicule and the general lack of interest in the language would seem absolutely crazy to anyone coming into the industry these days, but back then, writing **Javascript** was considered a necessity to be avoided as much has possible.

In fact, I recall one of the tech leads at _Metacafe_ going as far saying, back when **Node.js** was initially released, that any developer who would consider using it in production would be a failure as a software engineer. Before you try and defend that statement by arguing that Node wasn't _production ready_ when it was originally released, allow me to clarify - this lead's reasoning wasn't because Node was a new technology, but rather for the simple reason that it was running **Javascript**, and no engineer in their right mind would advocate using **Javascript** in production.

So, what do i choose? The safe bet of *Back End Development*, the established but still early days of *Web Development* or do I bet on the pariah of development languages and an ecosystem deemed lesser than the others?
</section>

## Betting on Javascript
<section>
I can't quite explain where it came from, but I had a gut feeling that the community of developers around me was wrong.  
In the early days of my career, when I was still a teenager and my entire interaction with code was driven by fun, rather than making a living, there was a community of passionate web designers and code monkeys called *guiStuff*.

![](/assets/img/2018/07/guistuff.png)

_guiStuff_ was a playground and a community of people all learning together, experimenting together and _becoming_ together. These kinds of online communities don't seem to exist any more, and I have many theories why, but at that time these communities provided a breeding-ground for new ideas.  
One of the ideas that the guiStuff community was slowly becoming obsessed with was crafting user experiences in the browser that would _feel pleasant_. At that time browsing the web often meant jittery experiences, with the whole window refreshing and jumping around on every interaction. Led by aesthetically driven web designers we we're experimenting with trickery using both graphics and code to craft user experiences, at a small scale, which would push the boundaries of what the industry seemed to think was possible inside of a browser.

Having come from that community, I had a gut feeling that Javascript and the browser held a power easily overlooked.  
I couldn't shake this feeling that the product manager, software engineers and tech leads around me were wrong - the web experience we were providing was *not* good enough and I had this visceral feeling that as products on the web matured, so would the expectations and hence the opportunities.

I chose to focus on Javascript, CSS and user Experience as a specialism; a choice I now hold as the single strongest evidence that I should always follow my gut instinct.
</section>

### The target platform
<section>
Much has been said about how Javascript has taken over the tech industry. I don't want to repeat what others have written far better than myself, but what I would like to hammer in is the state of Javascript as a *target platform*.

Over the decade or so in which I have focused on Javascript as a specialism, I have seen the language go from a _browser language_ to a _general purpose language_.  
If we look at a hypothetical developer, lets call her _Naomi_, coming into the industry today she can chose to learn Javascript as her first language and by doing so she gets to chose from a whole wide variety of target platforms.

For instance, by learning *Javascript* she can start building basic _User Interfaces_ in the browser and interact with real users.
She can also build a _service_ on a server which will empower those _UIs_ to actually deliver value very quickly - which is the reason we're actually there, right?
She can then use this skill set to write software for a small micro-controller which will track the water consumption in a war struck village in Yemen and notify benefactors in order to raise funds for more supplies.

The only limits to what you can achieve using Javascript these days is your imagination, and there's probably an _npm_ module for that too.
</section>

### Diagram of Javascript as a target platform
<section>

If Naomi were to come to me and ask:
> "What are all the platforms I can target with Javascript"_

I would show her the following diagram:

![](/assets/img/2018/07/jsstack.svg)

As you can see from this diagram, the **Javascript** language, coupled with **Node.js** and the community behind **npm**, powers a very powerful ecosystem with a very wide variety of tools at it's disposal for delivering true and lasting value to humanity.

OK, that's the spiel. But clearly, there is no need for a spiel as by virtue of being true we can infer that many people have already bought into it, right?

So why are we here?
</section>

## Javascript as the target, ReasonML as the vehicle
<section>
As much as I love Javascript, I have found over the years that there is one recurring problem I continue to encounter as the systems I build on top of it grow in complexity and size.

_I keep breaking things_.

![](/assets/img/2018/07/dididothat.gif)

I used to think that these breakages were just a result of a lack of specialism. I thought that if only my team and I would focus more on learning the language and ecosystem inside out, making sure everyone understood the internals of _Javascript_ and _Node.js_, and the nuances of asynchronous code, we could avoid these mistakes.

But now I am no longer so sure that's the case.

Over the past several years I have gone back to working in Java. I will write another blog post about the transition I made from a purely Javascript-focused specialist back to working in Java, but for now lets just accept this as a given fact: I have gone back to, mostly, using a statically typed language for my bread and butter, rather than the language I honestly prefer to work in (by far), which is Javascript.

My reasons for transitioning back to *Back End Development* are personal and super subjective, but my biggest take away from the past few years has been this: *there is no runtime substitute for the safety of compile time typing*.
</section>

### Going static
<section>

I have come to the conclusion that by having a strong type system on my side, I can truly provide better value than I can without it.

This is by no means a new argument. You'll find developers debating this question all the way back to the 50s when Lisp first introduced Dynamic Typing to the general development community. With that in mind, you might be asking yourself, if this is nothing new and you're just repeating what others have said, _why are you wasting my time with this blog post?_

Well, while this argument isn't new, what _is_ new is that I have have recently found that the main argument prevalent in the Javascript community _against_ going static isn't necessarily correct.
</section>

### Static means slow
<section>
The main argument which has kept me away from going back to statically typed languages with my personal work has been the claim that working in these languages is slow, inflexible and hard to change.  
While these are truly subjective measurements, it has been my anecdotal experience that after a decade of _thinking in Javascript_, especially with _functional programming paradigms_ gaining popularity in the community, these characterisations are true for the languages I have used, such as _Java_ and  _C#_ **\***.


Spending the last few years writing Java has only reinforced my feelings that prototyping in Java is needlessly slow and overly verbose, that changing complex Object Oriented systems is often doubly so and that this lack of flexibility actually hinders my ability to remain agile (agility isn't about speed, these are different problems).

That said, what I *have* enjoyed has been the safety provided by the type system. Additionally, the self documenting nature of a typed codebase makes it easier to express intent, to build confidence in my deployment process and to experiment in production.

The frustration with this disconnect drove me into months of experimentation.

I began by experimenting with _Flow_ and _Typescript_ - two options for using Static Types over Javascript.  
I found both of these options reasonable, but nowhere near as powerful as my experience with Java, as it was too easy for me to game the compiler. While escape hatches are helpful, they can also be detrimental when too easy to use.

I then experimented with _Scala_, _Closure_ **\*\***, _Haskell_, _Elm_ and _Erlang_ but all of them had issues I simply couldn't stomach. Mostly it was a lack of interoperability with Javascript which is still my _target platform_ of choice, or a lack of _general purpose_ support at language level (I'm looking at you _Elm_).

With other, I found that I simply didn't *think* in them; meaning that their syntax didn't allow me to express myself well.
  
> <sub>**\*** I suspect this might be less true for **F#** and **Scala**, but they aren't particulalrly good for targeting the Javascript runtime.</sub>

> <sub>**\*\*** Closure isn't Statically Typed, but I heard that _thinking in Lisp_ encourages safer code. I remain unconvinced.</sub>
</section>

### Enter ReasonML
<section>
What finally began to change my perception of static typing has been my introduction to **ReasonML** and by extension to **OCaml**.
Reason is a dialect of OCaml (simply speaking, it's a different syntax, but under the hood it's still OCaml) which has been designed to resemble Javascript.

There have been many great blog posts introducing ReasonML, so I'd suggest reading them, instead of me running through it all here, but the bucket list is thus:
1. It is statically typed.
2. It has _extremely_ good type inference.
3. It can compile to Javascript using a compiler called Bucklescript.
4. It can compile to native & bytecode, running on a well proven production ready platform, as OCaml has been in use as a systems language for over 20 years.

If you look at the following example, from some production ReasonML code, I find it has a very familiar feel to it as a Javascript developer, but at the same time, it is fully typed.
</section>


```reasonml
let readCacheServiceConfigAndDecode = (configJson) =>
  switch (configJson |> Js.Json.decodeObject) {
  | None => raise(Json.Decode.DecodeError("Invalid Cache Config"))
  | Some(data) =>
    data |> Js.Dict.map((. json) => CachingServiceConfig.decode(json))
  };

let getCacheConfigByEnv =
    (
      environment: environment,
      cacheServiceConfig: Js.Dict.t(cachingServiceConfig),
    ) =>
  switch (Js.Dict.get(cacheServiceConfig, environment.sspConfig.cacheEntity)) {
  | Some(config) => config
  | None =>
    raise(InvalidEnvironment("Caching Service Coinfiguration is missing"))
  };
```

### Static doesn't have to mean slow
<section>
While **ReasonML** is staticlly typed, I find it isn't slow to work with.
As stated above it has extremely good type inference, which means you don't have to repeatedly add type signatures wherever you go.
Whenever a type conflicts with how you're using it, the compiler will tell you.
The syntax for defining records and functions is very concise, and no where near as verbose as that of languages like _Java_.

All of the above make it fast to spike solutions without having to slow down too much or compromise on type safety.

I have compiled and deployed code from ReasonML straight to _AWS Node.js Lambdas_ and have had no issues other than the ones inherent to learning a new language.  
The interoperability with existing packages from _npm_ has been surprisingly easy and adding typed bindings around these modules (when lacking) has definitely been a new experience, but *Bucklescript*'s _Foreign Function Invocation_ syntax (which allows us to tell the compiler how to interact with untyped Javascript code) has been easier than my equivalent experience with _C++_ and _php_.
</section>

### The Expanded Target Platform
<section>
Last point, but by no means the least, is that of the expanded target platform.

As ReasonML can be compiled to Javascript, it can be used to write code for _any platform targetable by Javascript_.  
This means that as a Javascript developer, you don't lose any potential deliverable value by adopting ReasonML.

But, in addition to compiling to Javascript, you can compile your ReasonML code down to what we call *native* or alternatively to *bytecode*.

When you compile to _native_ you're essentially compiling your code down to whatever is considered native to the platform you're targeting. This means you can compile your code to the specific specification of a whole variety of servers and computing platforms.

When compiling to _bytecode_ you're essentially targeting whichever platforms are supported by the _OCaml_ runtime, which is installed separately from your code and is also supported by a variety of computing platforms.

With all that in mind, our diagram now looks like this:

![](/assets/img/2018/07/reasonstack.svg)

You might ask how this is different than simply compiling to Javascript and running on Node.js, and the answer is simple: The OCaml runtime is a highly performant systems platform with good support for concurrency and even multicore.
This means that where you were previously limited by some of the aspects of the Javascript runtime, such as the fact that it is single-threaded, you can now use ReasonML to build separate systems which get around these downsides. By having both options while using the same programming language, you get the best of both worlds.

By choosing ReasonML you're not only retaining your power as a developer on the _Javascript target platform_ but also gaining more power on _highly performant native platforms_.
</section>

## In Summary
<section>
I still adore Javascript, and I owe the success of my career thus far to the bet I made on it a decade ago, but I'm making a new bet and that's on ReasonML.
Lets revisit this bet in a decade and see if I'm a one trick pony.
</section>