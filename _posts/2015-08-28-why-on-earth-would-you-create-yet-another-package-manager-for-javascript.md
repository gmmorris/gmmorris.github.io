---
layout: post
title:  "Why on earth would you create yet another package manager for Javascript?"
description: "How and why I built a Javascript library for packaging modules"
date:   2015-08-28 12:06:00 +0100
tags: [javascript]
categories: [Javascript]
icon: stream
image: "/images/banners/shell.png"
image-desc: "The Shell"
image-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/21090105071/"
---


I recently got asked this question by a coworker…. as I tried to explain I found myself going back four years to my next to last job, where I developed the component I recently released known as The Modularizer at one of the most exciting rollercoasters I ever rode — the now deceased A/B testing startup Pluralis.

As I explained to my coworker what the needs were it occurred to me that as I also found a fresh usage for this component in my current role as Lead Front End Architect of Loveholidays, it might be worth explaining this publicly, so that perhaps it can help another company somewhere, now that I’ve open sourced it.


## What is it?


Well, simply put, Modularizer is a simplified Javascript package manager, built using the now standard AMD API (whose most widely used implementation is Require.js), which can exist completely independent of the global scope, unlike other AMD implementations which usually rely on a global-scoped set of functions.
You can read more technical details about it’s usage on the documentation page [here](http://gmmorris.github.io/Modularizer/), but what I’d like to explain in this post is the answer to the simple question: *Why bother?*


## Why Bother?


While Modularizer was created in 2011 (and of course maintained since then; It isn’t a relic, but hasn’t been open source for long, so I’m the sole maintainer), and today perhaps other available options are better, I still found it an ideal component for the recent rewrite of the Loveholidays website, which I spearheaded and recently completed.

Like I said, the main difference between Modularizer and other implementations like Require.js, is that it stays clear of the global scope. When I want to put together a package of JS modules, I simply create an instance of a Modularizer package and define the module inside of it, using the same API as RequireJS uses, but in a sandboxed environment, so that no clash can happen between the modules in my package and other packages on the page.

Usually this isn’t much of a requirement, because you usually have sole control of the JS modules on your pages, so there is little-to-no danger of a clash, but there is another situation where you might need a module package manager where the danger of a clash is very high — an embedded component which is injected into other people’s websites, and thats where Modularizer came into play and where it had it’s first *fire-test*.


## The Pluralis Use Case

To understand the need you must first understand what Pluralis did.
Pluralis was a crowd sourced A/B testing platform.
It tried to create a mix between the personalised A/B testing environment provided by the likes of *Optimizely* and the crowd sourced platforms like *99designs.*

<small>**take a deep breath and read the next two paragraphs quickly**</small>


The idea was that a client would visit our site, they would input their site’s url and would immediately be presented with their own website, but with our code injected into theirs, so that they could start marking sections they wanted tweaked and improved.
Our crowed sourced community would then be able to edit part of the client’s site, using an on page WYSIWYG editor, to optimize the client’s page for him. Whoever optimized the page to the best result (with Pluralis actally performing the Conversion Rate measurment between the different versions) would win a the contest and the client would pay the winning optimizer a bounty, after which, once all parties are paid, the client would receive a document explaining how to implement the optimized version on their site.

<small>**OK, breath**</small>



That was the idea… its not that relevant to this post, but rather the architecture required for this is the point. Pluralis had a need for a very complex Front End architecture (which, as the sole FE developer for the first 9 months of the company, rested solely on my shoulders), in which we had the following:



![Over simplified, but it gives a vague idea of the complexity any module manager would need to handle for our use case](/images/2015/08/pluralis.png)

*Over simplified, but it gives a vague idea of the complexity any module manager would need to handle for our use case*


This is an over simplified little slice out of an entire architecture, but the challenge for any module manager we chose was this: It had to be able to handle sharing different modules between several different packages, where each package had it’s own dependancies, own environment to live in and had to allow us a comfortable working platform for both Dev environments and Production environments.

These modules would also have to live well on both our own website and our clients’ websites, and as the saying goes: **its a jungle out there**.

The moment your code needs to live on other people’s website, it has to be as encapsulated and safe as possible.

If our product were to cause clashes on our clients’ websites and product — we were as good as finished. No one will use a product that hurts their website, and we had to be able to assure them, and ourselves, that our code cannot clash with theirs no matter what.


## The Technical Requirements

When Amnon Lahav, my CTO at Pluralis (and in fact, the only other developer in the room for the first 9 months or so), and I sat down to discuss our needs for a module package manager we stood in front of a white board and wrote down every requirement we had when analysing the existing libraries:

1. Has to be cross browser compatible, supporting everything from IE 7 and up.

1. Has to provide file fetching as well as module management.

1. Has to be as usable for us in Dev environments as on production, allowing us to work with our modules in both individual-file mode for easier development and debug, and also in concatenated and minified mode for production.

1. Wouldn’t clash with identical libraries on the client’s site — we couldn’t have our RequireJS environment clash with the client’s Require.js, and that kind of thing.

1. Would make it comfortable to maintain dependancies and make module names easy to handle (At the time Require.js only supported filenames as module identifiers, and we didn’t want the file’s location to limit our ability to reference a file, as a module would be shared between different packages at the same time. Today R.js can handle this, at the time, it couldn’t).

No package manager we could find (and we tried every single one that existed in 2011) could handle all of these requirements. Require.js came close, but fell short when used embedded in clients’ sites, and so the need to build our own came up.

I hacked up Modularizer in a week and I’ve been maintaining it ever since.
I only got permission to Open Source it last year when Pluralis finally bit the dust, and the first thing I did was repurpose it for Loveholidays’s rewrite for which I knew I needed a library to live side by side with a local Require.js installation, but more on that later.

## Is it really still useful?

I’ll be honest- I’m not sure it really is.
Its important to understand that when Modularizer was first written, in 2011, other options, such as Require.js, were still very young (a year old at most), lacking in features and build tools, and still had many bad assumptions in their code, such as code going directly to *window.define() *which made it almost impossible to keep them off of the global scope.

Today this is far from being the case.
First of all — we have Node.js and CommonJS on our side, and with ES2015 modules coming into play now, there really are many far better options.
Second — the better maintained tools like Require.js with it’s R.js build tool are far more feature rich and adaptable to our needs.

So why bother with Modularizer?
Only one reason — its a piece of engineering I’m still proud of. :)

This post is, by no means, a *call-to-action* on an open source project. It is simply me sharing my thoughts about a component I developed, which I think provides a slightly different approach than I’ve seen in other places. At least, in the Front End world (Most of the concepts behind Modularizer are “stolen” from Back End languages, and merged with Front End ones)…

… and Modularizer has served me well in both Pluralis and Loveholidays. I’ll be writing a more extensive article about the rewrite of Loveholidays.com, but that is for another day.

Cheers.
