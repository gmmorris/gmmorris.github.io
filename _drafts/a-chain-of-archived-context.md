---
layout: post
title:  "Distributed by Design II: A Chain of Archived Context"
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
In the first part of this blog series we covered what we mean when we talk about _asynchronous communication_, and I introduced you to the two tools that Elastic uses to set the baseline for the expectations we have of our distributed teams.

Your continued interest in the topic of _Distributed by Design_ suggests you're, at the very least, intrigued by the possibility of asynchronous work, but you might not be _entirely sold_ on the merits. Given the challenges inherent to asynchronous work, I couldn't blame anyone for doubting whether the return justifies the effort, especially if your team is [not _distribted_, but rather merely _remote_]({% post_url _drafts/2022-01-26-remote-isnt-distributed %}).

I don't personally believe asynchronous work, or distributed teams, are suited to everyone. In fact, I think it's a minority of people who are well suited for this approach to work, but I also believe this is a large enough subset of the tech industry that companies who approach this challenge well are well placed to grow more high-performing teams than they will ever know what to do with.


# Part II: A Chain of Archived Context

Lets explore what I believe to be an immediate and tangible benefit inherent to asynchronous work: something I call the _chain of archived context_. While there are other, arguably more valuable, benefits (such as a healthier work-life-balance and inclusivity) it is this chain that gave me my first _aha-moment_ regarding asynchronous communication.

## The Challenge

One of the problems I've struggled with throughout my career, at every single company (Elastic included), is remembering _why_ we made a decision at some point in the past.<br/>
Remembering why we made a certain decision in the past empowers us to make better informed decisions in the present, and even though I'm generally far more interested in talking about where we're going, rather than where we've been, changing a decision is always safer when you understand why that decision was made in the first place.

### In Relation to Documenting Working Agreements
A common allegory for the importance of _remembering why_ is [the parable of the five monkey experiment](https://intersol.ca/news/organizational-culture-and-the-5-monkeys-experiment/), which describes how a group of individuals can easily end up following a certain rule without knowing _why_ they follow it.

I've seen this happen first hand in many engineering teams, where the team follows a certain practice because _that's how it's always been done_.

At some point, the team made a decision, such as limitting their automated testing to _"one browser-based end-to-end test per UI component in order to keep the test duration low"_. Years have passed and the team finds itself in a state where each of their UI compontents has ended up with dozens of test-cases baked into one, single, automated test. Hard to maintain, error prone, and unreliable. The team had agreed to follow this rule years ago, documented this rule on their official _Working Agreements_ wiki page, and even added a linting rule that verified this behaviour, so every new engineer who joined the team fell in line and followed the rule.

What the team had forgotten was that this decision, made in the early days of the company, was the result of a limited budget on the team's CI server. They could only afford to run a certain amount of tests per month, and to avoid running out of budget chose to optimise for CI server resources, at the expense of test maintainability and quality.<br/>
This decision made sense at the time, but now, years later, the company no longer had this budget problem. In fact, they had moved to a completly different CI system, where they had no limits what so ever. The team continued to follow a rule that was no longer relevant, but none of them realised, as they had forgotten _why_ they had set it in the first place.

_The question is, how do you retain this knowledge, and how do you make it discoverable?_

### In Relation to Documenting Technical Decisions
As engineers we are notoriously bad at documenting technical decisions, and though this topic is far from underdiscussed, I find we tend to focus on architectural decisions rather than the ad-hoc technical discussions and decisions made in the day-to-day.

It's my anecdotal experience that we focus on the larger architechtual decisions, not only because we consider these decisions more impactful, but because it's the path of least resistence.<br/>
In a typical engineering environment, technical decisions are made in synchronous meetings and conversations, often followed up by the actual implementation of the decision. Documentation only takes place after the _[definition of done (DOD)](https://www.leadingagile.com/2017/02/definition-of-done/)_ has been achieved, at which point, lets me honest, most engineers<i class="fas fa-asterisk"></i> want nothing more than to put this problem behind them and move onto the next one.

There's a high degree of effort associated with slowing down in order to document decisions that were made days, weeks, or even months ago. This effort, perceived or otherwise, only grows as you go beyond the decision itself to explore the context and conversations that led to it being made. <br/>

I find it's easier to convince engineers of incurring the cost of this effort when the topic at hand is _architectural decisions_, as these tend to be bigger, more visibile, and more likely to get questioned at some point in the future. But when it comes to the smaller decisions, that we tend to make every day, this effort is deemed too high.<br/>
Engineering leaders have struggled with this for years, which is why for the most part we advocate for solutions at that level, such as [Architecture Decision Records (ADRs)](https://www.youtube.com/watch?v=rwfXkSjFhzc) (of which I'm a big advocate) and, following the path of least resistence, call it a day.

It's worth noting though, that even when an organisation successfully adopts ADRs, they might communicate the decision and why it was made, but rarely will it include a broader context. Context such as alternate options that were rejected, or the broader conversation that took place at the time explaining why this decisions was deemed a priority at all, tend to get lost.

This is reasonable, as ADRs are intended to be easy to consume, and documenting too much context would make this harder and less useful.

_The question is, how do you make it easier to document decisions earlier as they're being made? and how do we include the broader context without documentation becoming too much of an effort to consume?_

<small class="footnote"><i class="fas fa-asterisk"></i> To be clear, this isn't an _engineers_ problem, as I've seen the exact same behaviour exhibitted by product managers, business development people and more. I find humans struggle to think about their future needs once their immediate need has been addressed.</small>

## The Aha-Moment: Documenting the Broader Context

A year or so into my time as a member of a distributed team I had a true _aha-moment_.

I've historically found Both of the examples above hard to tackle as the broader context, such as the discussions that take place prior to a decision being made, isn't usually documented.

In hindsight, this makes sense, as documenting these things is generally hard. Most of these conversations took place in-person, either at the watercooler, on dedicated meetings, or spread out across multiple different face-to-face interactions. This is _a lot_ of content, yet good documentation needs to be searchable and easily consumed, which means it has to be concise.

Including this sort of context would actually defeat the purpose of most documentation efforts.

This means that documenting the broader context has to exist _in addition_ to the documentation of the actual decision, and it likely requires a richer media format than a simple text file, such as an ADR, is able to provide.

Do you see where I'm going with this yet?

### As a Distributed Team this is Easier

The difference for teams who practice asynchronous communication is that, unlike any co-located team I have ever been on, this broader context is actually straight forward to document.

Conversations are always documented in an Email thread, a _Github issue_, or, if a burst of synchronous collaboration is required, a Zoom call.

Whichever medium we choose, all this context is easy (and cheap) to recorded and _link_ with the _source of truth_. By _source of truth_ I mean, the place where a future teammate (or a future self) will likely go looking for answers when they have questions.

By linking the broader context to the _source of truth_ we can create a _chain_.<br/>
A _Chain of Archived Context_.

### Example I: Working Agreements

One of the practices I carried over from Unruly to Elastic is our [Getting Better At]({% post_url 2018-08-26-getting-better-at %}) sessions.
Every once in a while my teams get together to tackle a specific practice, such as _PR Reviews_ or _Automated Testing_, and spend a concentrated synchronous hour tackling the question: _"How can we get better at this practice?"_.

The end result of every such session is a refresh of the team's _Working Agreements_, which are all documented in a dedicated Github Issue.

Where the _archive_ aspect comes into play is when a teammate asks: _"why do we do this thing we've always done?"_.
As an engineering manager I can tell you this happens quite often in team meetings, or one-to-one coaching sessions.

Whenever I'm asked this question, I point them at the _Working Agreements_ issue, and suggest they go back to the recording of the relevant _Getting Better At_ session, and find out.
If they feel the reasoning is no longer valid, I suggest they bring it up with the team, and revisit the agreement.

![Why did we decide on this working agreement?](/images/2022/02/a-chain-of-working-agreements.png)

Back at Unruly, this was much harder, and was only possible because a handful of collegial old timers, who had remained at the company for years, were available to answer these questions - assuming they recalled the reasoning themselves.

One such colleague, [benji](https://twitter.com/benjiweber), made [the same observation](https://benjiweber.co.uk/blog/2018/08/20/the-unsung-upsides-of-staying-put/) when he left Unruly, interestingly commenting on the fact that some teams _were_ in-fact archiving their stand-up meetings by recording them, but no one was actively consuming these recordings.

Benji's observation was, in hind sight, a missed learning opportunity on my part, as I had taken note of the unnecesery need for recording those meetings, but entirely missed that the real problem was the lack of discoverability of these recordings.<br/>
Recordings are only useful if they are archived in a discoverable manner. This is why linking the recordings to the source of truth, where the decision has been documented, is critical.

### Example II: Technical Implementation

**(Or Why the F\*\*k Did I Do It That Way?)**

We've all been there.<br/>
A bug report comes in, we reproduce the issue locally and locate the offending code. Reviewing the code, a sigh escapes our lips, followed by a semi-rehtorical question: _"Why the f\*\*k did we do it this way?"_<br/>
`git blame`, we type in out console, just to see our own name staring back at us.<br/>
_"Oh... Why the f\*\*k did **I** do it this way?"_

The _working agreements_ example was a fairly straight forward one - hold a meeting, record it, and link to the recording next to the recording notes.
Hardly ground breaking.<br/>
This is where the _chain of archived context_, really shines, and this is where my true _aha-moment_ took place.

The _git blame_ command, which tells us who the developer was that commited the offending code, also gives us the _pull request_ that merged it.
The nice thing about how services like Github work, is that this _pull request_ also links us with the _issue_ where the user story and requirements were discussed.

This is already a great place to be as the issue includes lots of valuable context, thanks to the prioritisation of asynchronous communication.
But what if, in addition to the issue, we also have links to recordings of all the meeting where we discussed the work?
What if, thanks to the unusual _ease_ with which we were able to document and access this context, we can now spend an hour rewstching those meetings (at _x2 playback speed_, obviously), regaining all the context we had two years ago?

How much easier will it be for us to address this bug now that we know _why_ it was done this way?

Now, imagine if these meetings took place two years before you joined the company? These recording are no longer _reminders_, but rather discoverable and focused _onboarding_ material that your team put in place long before they knew you;d need it.
You're now better prepared to fix a legacy bug than I have ever been in any co-located team I have been on in 20 years.

Now **that's** an _aha-moment_!

![Why did I do what I did back in 2020](/images/2022/02/an-archived-chain-of-communication.png)

#### A Tip for Those Who Develop in the Open

While only a portion of Elastic's software is technically _open source_, the vast majority of it is developed in the open.
This means that, for the most part, our code, issues, pull requests, and documentation, are visibile to all on our [github account](https://github.com/elastic).

As an engineer I find _devlopeing in the open_ to be a wonderful and humbling experience, but at times it also feels _exposed_ and _observed_.
As a result, not all communication can, or should, take place in the open, and at times we wish to link a recording that we wish to keep internal, to an issue in our public repository.<br/>
We _could_ link to a password-protected recording, but love our community and believe this provides them with a poor experience when following such links.
Luckily, Github provides a very good facility for this: We can refer to issues the other way around.

We maintain dedicated issues in our private repositories where we can _reference_ issues in our public repositories, and provide a link to the recording there.
When the public issue is view, this _reference_ appears on the issue, but is only visible to users who have access to the private repository - meaning they are other Elasticians, who we wish to share this context with.

## Recording Intent the Easy Way

RFCs, ADRs, and other means of documenting decisions are all about recording the original intent in a discoverable manner.
When your culture instinctively records decisions in an asynchronous means of communication, it becomes easier to to maintain an archive of these decisions.

What I have discovered over the past few years, is that working remotely makes this sort of thing easier, but working _distributed_ makes these things _inuitive_ and as a result - the easiest.

An interesting nuance I have found is that truly distributed teams, where their members are spread out across mutltiple time zones, find this far easier than teams that are in the same timezone. We'll discuss this in the third part of this series, [Managing Distributed Teams]({% post_url _drafts/2022-01-29-managing-distributed-teams %}).
