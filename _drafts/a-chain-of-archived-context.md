---
layout: post
title:  "Distributed by Design: A Chain of Archived Context"
date: 2022-01-28 00:00:00
categories: [Communication]
tags: [distributed,remote]
icon: seedling
description: ""
image: "/images/banners/taking-in-cargo.png"
banner-img: "/images/banners/taking-in-cargo.png"
image-desc: "Taking in Cargo"
image-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14595291879/"
---
In the first part of this blog series we covered what we mean when we talk about _asynchronous communication_, and I introduced you to the two tools that Elastic uses to set a baseline of _expectations_ for it's distributed teams.

Your continued interest in the topic of _Distributed by Design_ suggests you're, at the very least, intrigued by the possibility of asynchronous work, but you might not be _entirely sold_ on the merits. Given the challenges inherent to asynchronous work, I couldn't blame anyone for doubting whether the return justifies the effort, especially if your team is [not _distribted_, but rather merely _remote_](/communication/2022/01/27/intentionally-asynchronous#remote-distributed).

In part II we explore what I believe to be the immediate and tangible benefit inherent to asynchronous work: what I call the _chain of archived context_. While there are other, arguably more valuable, benefits (such as a healthier work-life-balance and inclusivity) it is this chain that gave me my first _aha-moment_ regarding asynchronous communication.

# Part II: A Chain of Archived Context

## The Challenge

One of the problems I've struggled with throughout my career, at every single company (Elastic included), is _remembering why_. Why we made a decision at some point in the past.<br/>
_Remembering why_ we made a certain decision in the past empowers us to make better informed decisions in the present, and even though I'm generally far more interested in talking about where we're going than where we've been, changing a decision is always safer when you understand why that decision was made in the first place.

### In Relation to Documenting Working Agreements
A common metaphor for the challenge of _remembering why_ is [the parable of the five monkey experiment](https://intersol.ca/news/organizational-culture-and-the-5-monkeys-experiment/), which describes how a group of individuals can easily end up following a certain rule without knowing _why_ they follow it.

I've seen this first hand in many engineering teams, where the team follows a certain practice because _that's how it's always been done_.<br/>
At some point, the team made a decision, such as setting a limit of one browser-based end-to-end test per UI component in order to keep the test duration low. Years have passed and each compontent ended up with dozens of test-cases baked into one, single, automated test. Hard to maintain, error prone, and unreliable. The team had agreed to follow this rule years ago, documented this rule on their official _Working Agreements_ wiki page, and even added a linting rule that verified this behaviour, so every new engineer who joined the team fell in line and followed the rule.

What the team had forgotten was that this decision, made in the early days of the company, was the result of a limited budget on the team's CI server. They could only afford to run a certain amount of tests per month, and to avoid running out of budget chose to optimise for CI server resources, at the expense of test maintainability and quality.<br/>
This decision made sense at the time, but now, years later, the company no longer had this budget problem. In fact, they had moved to a completly different CI system, where they had no limits what so ever. The team continued to follow a rule that was no longer relevant, but none of them realised, as they had forgotten _why_ they had set it in the first place.

_The question is, how do you retain this knowledge, and how do you make it discoverable?_

### In Relation to Documenting Technical Decisions
When it comes to architectural decisions, the topic of decision documentation is far from underdiscussed.
Engineering leaders have struggled with this for years, and a variety of solutions have sprung up, most popular among them seems to be the [Architecture Decision Record (ADR)](https://www.youtube.com/watch?v=rwfXkSjFhzc).<br/>
For those who are unfamiliar, ADRs are documents that capture an architectural decision along with the context and the known consequences inherent to it. This document is, in my opinion, invaluable and I am a huge advocate of theirs. The problem is, I also find it hard to implement them in the real world for two reasons: they require a high degree of self discipline, and they are often too _lossy_.

The need for self discipline is inherent in that, in a typical engineering environment, these decisions are made in synchronous meetings and conversations, often followed up by the actual implementation of the decision, and only then are they documented in an ADR.<br/>
This is because ADRs aren't documenting the decision to explore an idea, but rather the end result where the idea has already been implemented. This means that these decisions require an additional step, often after the _[definition of done (DOD)](https://www.leadingagile.com/2017/02/definition-of-done/)_ has been achieved by the engineers. Granted, the ADR _should_ be part of the DOD, but as ADRs are generally only used to document _architectural_ decisions, they are often omitted for most of the engineering team's workload.

The lossyness becomes apparent when you read an ADR and realise that, though it communicates the decision and why it was made, it rarely includes a broader context. Context such as alternate options that were rejected, or the broader conversation that took place at the time, tend to get lost.
This is reasonable, as ADRs are intended to be easy to consume, and including too much context would make this harder and less useful.

_The question is, how do you make it easier to document decisions sooner, as they're being made, and how do we include the broader context?_

## Documenting the Broader Context

A year or so into my time at the company I had a true _aha-moment_ about working at Elastic.

Both of the examples above have historically been hard for me to tackle because the broader context, such as the discussions that take place prior to a decision being made, isn't usually documented.

In hindsight, this makes sense, as documenting these things is generally hard. These sort of conversations often take place in face-to-face meetings, at the watercooler, at a dedicated meeting, or spread out across many such meetings. This is _a lot_ of content, yet good documentation needs to be searchable and easily consumed, which means it has to be concise. Including this sort of context would actually defeat the purpose of most documentation efforts.

This means that documenting the broader context has to exist _in addition_ to the documentation of the actual decision, and it likely requires a richer media format than a simple text file, such as an ADR, is able to provide.

Do you see where I'm going with this yet?

### Why This is Easier For Distirbuted Teams

The difference for teams who practice asynchronous communication is that, unlike in a co-located team, this broader context is far easier to document.

Conversations are always documented, possibley in writing as part of an Email thread, but more likely in a _Github issue_ if the topic is technical, or a Zoom call if it requires a burst of synchronous collaboration.

Whether we're talking about a Github issue, a document, or the recording of a Zoom call, all this context is easy (and cheap) to recorded and _link_ to the _source of truth_.

By _source of truth_ I mean, the place where a future teammate (or a future self) will likely go looking for answers when they have questions. By linking the broader context to the _source of truth_ we can create a _chain_. A _Chain of Archived Context_.

### Example I: Working Agreements

One of the practices I carried over from Unruly to Elastic is our [Getting Better At]({% post_url 2018-08-26-getting-better-at %}) sessions.
Every once in a while my teams get together to tackle a specific practice, such as _PR Reviews_ or _Automated Testing_, and spend a concentrated synchronous hour tackling the question: _"How can we get better at this practice?"_.<br/>
The end result of every such session is a refresh of the team's _Working Agreements_, which are all documented in a dedicated Github Issue.

Where the _archive_ aspect comes into play is when a teammate asks: _"why do we do this thing we've always done?"_.
As an engineering manager I can tell you this happens quite often in team meetings, or one-to-one coaching sessions.

Whenever I'm asked this question, I point them at the _Working Agreements_ github issue, and suggest they go back to the recording of the relevant _Getting Better At_ session, and find out.
If they feel the reasoning is no longer valid, I suggest they bring it up with the team, and revisit the agreement.

![Why did we decide on this working agreement?](/images/2022/02/a-chain-of-working-agreements.png)

Back at Unruly, this was much harder, and was only possible because a handful of old timers had remained at the company for years and were available to answer these questions - assuming they recalled the reasoning themselves.

One such colleague, [benji](https://twitter.com/benjiweber), made [the same observation](https://benjiweber.co.uk/blog/2018/08/20/the-unsung-upsides-of-staying-put/) when he left Unruly, and interestingly he commented on the fact that some teams were in fact archiving of their stand-up meetings by recording them, but no one was actively consuming these recordings.

This observation was, in hind sight, a missed learning opportunity on my part, as I had taken note of the unnecesery need for recording those meetings, but entirely missed that the real problem was the lack of discoverability of these recordings. Recordings are only useful if they are archived in a discoverable manner. This is why linking the recordings to the source of truth, where the decision has been documented, as seen above with regards to our working agreements, is critical.

### Example II: Technical Implementation
**(Or Why the F\*\*k Did I Do It That Way?)**


What I have discovered over the past few years, is that working remotely makes this sort of thing far easier.

![Why did I do what I did back in 2020](/images/2022/02/an-archived-chain-of-communication.png)