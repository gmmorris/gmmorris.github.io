---
layout: post
title: "Old Men Yelling at Specs"
categories: [Agentic Extreme Programming]
tags: [extreme programming, spec-driven development, wicked problems, customers, AI, agents]
icon: seedling
description: "Spec-driven development will be misunderstood the same way Agile was. It works for discovering one small step of a wicked problem with the customer, and fails when we use it to plan the whole thing ahead of time."
# TODO: banner image
---
<!--
STRAW DRAFT. Not for publishing. Things marked VERIFY need checking against
primary sources before any of this survives.
-->

There's a familiar argument playing out at the moment, and I'm on both sides of it.

On one side are the agile veterans. They watch a team hand an agent a feature request, get back a few thousand lines of `spec.md`, approve it, and let the agent build the lot. They recognise the shape immediately: requirements gathered up front, a big document signed off, a long build, and the customer at the far end of it. *That's waterfall*, they shout. *We spent twenty years getting away from this.*

On the other side are the people actually shipping with agents, who are tired of being told they're doing it wrong by people who learned their craft when typing was the bottleneck. The tools have changed. Writing a spec used to be expensive and now it's nearly free. Rework used to be painful and now an agent will rewrite the module before lunch. Why should the rules from 2001 still apply?

I think both sides are right, and both are missing something. **Spec-driven development is going to be misunderstood in exactly the way Agile was.** Used as a tool for working out the next small step of a problem *with* the customer, it's genuinely useful, and closer to XP than either camp would like to admit. Used to plan the whole problem ahead of time, it fails, and it fails most on the problems that matter most. The trouble is that agents make the second way the easy one.

## Why XP put the customer in the room

When Kent Beck wrote *Extreme Programming Explained* in 1999, the **On-Site Customer** was one of the original twelve practices: a real customer, sitting with the team, answering questions and making priority calls as the work happened. In the second edition, in 2004, it was folded into Whole Team, with Real Customer Involvement as a corollary, something you build up to rather than start with. <!-- VERIFY against both editions -->

It's easy to remember this as a convenience: someone to ask. But the practice rests on a handful of assumptions, and they're worth spelling out, because agents have quietly changed every one of them.

### Requirements are discovered, not specified

XP started from the assumption that no document captures the requirements up front. You don't know what the customer needs until you've built a little and watched them react, and often they don't know either. That's why a user story was never a spec. It's a placeholder for a conversation.

An agent doesn't change this. It just makes it much easier to skip the conversation and write the placeholder out in full.

### Waiting is the expensive part

A developer blocked on a question has two options: stall, or guess. Sitting together made an answer cost minutes rather than days, so people asked instead of guessing.

Agents have removed the stall entirely. You never have to wait, because the agent will happily fill the gap. **But filling the gap is guessing. It's just guessing fluently, and at scale.**

### Developers shouldn't make business decisions

XP's planning game splits decisions deliberately. Business people decide scope, priority and dates. Technical people decide estimates and technical consequences. A developer's guess at a business rule is a decision made by the wrong person.

With an agent in the loop, it's often not even the developer making that decision. I [wrote recently]({% post_url 2026-11-08-whose-decision-was-that-anyway %}) about how readily we adopt an agent's lean as our own. A business rule invented by an agent, accepted by an engineer and buried in line 412 of a spec, is a decision made by *two* wrong parties, and neither of them will remember making it.

### There is one voice

The on-site customer had the authority to decide, and to settle conflicts between stakeholders, so developers didn't have to arbitrate. When sales wanted one thing and support wanted another, someone with the standing to choose was in the room.

Agents don't arbitrate. They reconcile. Hand one two conflicting requirements and it will find a way to satisfy both on paper, which usually means neither in practice. The conflict doesn't get resolved. It gets hidden.

### A wrong guess compounds

Misunderstandings get built on, so the cheapest moment to correct one is the moment it happens. Feedback in minutes beats feedback each iteration, which beats feedback at the end.

This is where XP made its boldest claim: that its practices could flatten the cost-of-change curve. The conventional wisdom, going back to Barry Boehm's work in 1981, was that the later you discover a mistake, the more expensive it is to fix. <!-- VERIFY: Boehm 1981, and Beck's framing of the flattened curve --> XP argued that with small steps, tests and refactoring you could defer decisions safely. **But that flat curve rested on the customer being there to catch the wrong turns early.** Take the customer away and the curve bends right back up.

The modern version of the flat-curve claim is that agents make rework cheap. That's true in the short term: if you catch a mistake the same afternoon, an agent really can make undoing it almost free. But the later a decision is reversed, the more has been built on top of it, and agents build on top of things *very* quickly. **Agents flatten the cost of producing code, not the cost of being wrong.**

And it isn't only a theoretical worry. [Some engineers are starting to notice it](https://lnkd.in/p/es9MVCJV) day to day: when an agent hits a bug, it patches the one case in front of it rather than stepping back to question the design that caused it, even when explicitly asked to rethink. Each patch is another thing built on top of the original decision, which makes that decision more expensive to undo. Agents haven't made rework cheaper. They've made it easier to put off.

### The customer's time is cheap compared with rework

Putting a customer in the room was always a bet: that the cost of their time was lower than the cost of building the wrong thing.

Agents have changed the maths, or at least they appear to. If rework feels free, the customer's time starts to look expensive by comparison, and the bet looks like a bad one. That's the trap. The rework only *feels* free because its real cost turns up later, compounded, on someone else's sprint.

### Understanding is built by being together

Context travels through conversation, overheard talk and shared artefacts, not through handoffs. The on-site customer didn't just answer questions. They were *around*, and the team absorbed the domain by being near it.

This is the assumption agents have eroded most. More and more decisions are being made in silos: one engineer, one agent, one long conversation nobody else sees. The context still exists. It's just trapped in a chat history.

### Talk is cheap

<!-- TODO: tie in the Spotify "talk is cheap" point. Need the source/reference from Gidi. -->

[Placeholder: the Spotify "talk is cheap" point.]

Talk has always been cheap. That was the whole point: a five-minute conversation is the cheapest feedback loop there is. What's changed is everything around it. When code was expensive, talking first was obviously sensible. Now that code is cheap too, it's tempting to think talk has lost its advantage. I think it's the opposite. **When we're making more decisions than ever, alone with an agent, the conversation is the only thing that puts a second mind on them.** Talk is cheap, and it's never been worth more.

## Tame problems and wicked problems

In 1973, Horst Rittel and Melvin Webber published *Dilemmas in a General Theory of Planning*, and gave us a distinction I keep coming back to: **tame problems** and **wicked problems**.

A tame problem can be fully specified before you start. You know when you've solved it, and the solution is either right or wrong. A wicked problem is different: you can't define it until you've tried to solve it, there's no point at which it's clearly done, and every attempt changes the problem. As they put it, the information needed to understand the problem depends on one's idea for solving it. <!-- VERIFY exact quote -->

I want to be clear about this, because the agile camp often isn't: **for tame problems, writing the spec up front is fine, and often the best thing to do.** A CSV parser, a migration between two well-documented APIs, a CRUD service over a known schema. Write it down, hand it to the agent, check the result. That's where spec-driven development earned its reputation, and it deserves it.

Wicked problems are where it breaks. Not because people aren't disciplined enough to write a good spec, but because the information the spec needs **doesn't exist yet**. It's created by building something small, putting it in front of people, and watching what they do with it.

## Wicked problems in disguise

The obvious wicked problems aren't the dangerous ones. Nobody sits down to spec "fix healthcare" in one go. The dangerous ones look tame: a checkout flow, an onboarding form, a reporting dashboard. They look like CRUD until real people start using them, and then they turn out to be about trust, or fear, or politics, or something nobody in the planning meeting would have guessed.

<!--
ANECDOTE GOES HERE. Candidates so far: the Lucky Iron Fish (shape mattered more
than chemistry; later, possibly the wrong problem), Nextdoor's posting flow
(adding friction reduced racial profiling), M-Pesa (built for loan repayments,
used to send money home). Ideally something surprising that only showed up
because someone shipped a small step and watched.
-->

> **[Anecdote: a problem that looked tame, and a discovery that no up-front spec would have contained.]**

**You often can't tell a problem is wicked until you've started building it.** Which means the first step of any spec has to be small enough to tell you what kind of problem you're dealing with.

## What the evidence says

This isn't just an old man's intuition. <!-- tone check -->

**Most ideas don't work, even when experts have them.** Ron Kohavi and his colleagues ran experimentation at Microsoft for years. Their finding was that only about a third of ideas tested improved the metric they were designed to improve, and on mature products like Bing the success rate was lower still. <!-- VERIFY figures against Kohavi et al. and "Trustworthy Online Controlled Experiments" (2020) --> These were experienced people, with data, building things they believed in. A spec is a stack of untested ideas, and most of them are going to be wrong in ways you can't see until they meet users.

**Big plans have fat tails.** Bent Flyvbjerg's dataset of over 16,000 projects found that only a tiny fraction delivered on time, on budget and with the benefits they promised, and IT projects have some of the worst tails of all: a minority blow up catastrophically. <!-- VERIFY: How Big Things Get Done (2023); Flyvbjerg & Budzier, HBR 2011 --> The interesting twist is that Flyvbjerg's prescription is *more* planning: "think slow, act fast". But look at what he means by planning: Pixar re-cutting storyboards dozens of times, Frank Gehry iterating on models. That's not a spec written up front. It's discovery, done cheaply, before the expensive commitment.

**The feeling of progress is unreliable.** In METR's 2025 study, experienced open-source developers were measurably slower with AI tools, while believing they'd been faster. <!-- VERIFY numbers --> A few thousand lines of well-structured spec feel like a lot of progress. They might be.

**And the industry numbers are heading the wrong way.** <!-- TODO: DORA 2025 on user-centric focus, if it says what I think it says; CircleCI 2026 State of Software Delivery figures on spend vs. outcomes --> [Placeholder: we're spending more on AI than ever, and getting less back.]

## Why we reach for the big spec anyway

If the evidence is this consistent, why does the big spec keep winning?

I've [written before]({% post_url 2026-11-08-whose-decision-was-that-anyway %}) about the path of least resistance, and this is another version of it. **The customer's attention is the scarcest thing on any project.** Every conversation has to be booked, prepared for and followed up. Writing everything down once, and sparing everyone the conversations, is enormously tempting. Agents have made it almost free. So specs balloon, because the cheapest thing to produce is more spec.

And for most engineers, the customer was never in the room anyway. In most companies I've worked with, the customer isn't someone who turns up asking for things. It's someone the sales team spent months courting, and account managers can be fiercely protective of them, often with good reason. Engineers are honest about the product in ways that can be alarming to a customer who's still deciding whether to trust you. So there are guardrails, and gatekeeping, and an hour a fortnight if you're lucky.

XP's on-site customer assumed access that most teams simply don't have. The big spec is what fills the gap.

## Where SDD and XP actually agree

Here's the part I think both camps miss. **Test-driven development was always spec-driven development, at the smallest possible scale.** You write the spec as a failing test, make it pass, and find out what you got wrong. XP's story cards and acceptance tests were specs too. Nobody in XP was against writing down what you intend to build.

So the real argument isn't spec versus no spec. It's **how far ahead of the feedback the spec runs.** A spec for the next small step, written with the customer and checked against their reaction before the next one is written, is about as XP as it gets. A spec for the whole problem, written before anyone outside the team has seen anything, is the thing the old men are shouting about, and they're right to.

## Using agents to get to the customer

If the agent can build something before the meeting is booked, then maybe the meeting should be about what it built.

One approach I've been experimenting with: build a throwaway prototype, and when you show it to a customer, frame it as **something you built for a different customer**. It isn't scalable, it isn't for sale, and it isn't on the roadmap. You're showing it to them because they seem engaged in the problem and you'd value their reaction. <!-- TODO: finish this thought, the original message was cut off -->

That framing does a lot of work. It lowers the stakes for the sales team, because nobody is promising anything. It lowers the stakes for the customer, who can be honest without worrying they're committing to it. And it uses the agent's speed to *start* the conversation, instead of using it to avoid one.

## Where I've got to

The old men are right: the customer matters more than the spec, and on wicked problems a spec that runs ahead of the feedback will be wrong in ways that compound. The young people are right too: the tools really have changed, and the way we reach the customer, and what we bring to them, should change with them.

**Write the spec for the next step, not the whole problem.** Then go and find out what you got wrong.
