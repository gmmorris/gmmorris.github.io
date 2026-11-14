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

When Kent Beck wrote *Extreme Programming Explained* in 1999, one of the core practices was the **On-Site Customer**: a real customer, sitting with the team, answering questions and making priority calls as the work happened.

It's easy to remember this as a convenience: someone to ask. That was never the point. XP started from the assumption that requirements are *discovered*, not gathered. You don't know what the customer needs until you've built a little and watched them react, and they often don't know either. The customer in the room was there to shorten the loop between a wrong assumption and its correction, from months to hours.

There's a part of this that I think gets forgotten. XP made a bold claim: that its practices could flatten the cost-of-change curve. The conventional wisdom, going back to Barry Boehm's work in 1981, was that the later you discover a mistake, the more expensive it is to fix. <!-- VERIFY: Boehm 1981, and how Beck framed the flattened curve in the 1st edition --> XP argued that with small steps, tests and refactoring, you could defer decisions safely. **But that flat curve rested on the customer being there to catch the wrong turns early.** Take the customer away and you're making decisions blind, and the curve bends right back up.

The practice didn't survive contact with reality unchanged. In the second edition, in 2004, On-Site Customer was split into Sit Together, Whole Team and Real Customer Involvement, with the last one demoted to a "corollary" practice, something you build up to rather than start with. <!-- VERIFY: wording and Beck's reasoning, from the book itself --> The industry had found that a full-time customer was hard to come by, and had filled the gap with proxies. Beck's answer wasn't to drop the principle. It was to make it a property of the team.

### Agents don't flatten the curve either

The current version of the flat-curve claim is that agents make rework cheap. If the spec was wrong, regenerate it. If the code was wrong, rebuild it.

That's true in the short term. If you catch a mistake the same afternoon, an agent really can make undoing it almost free. But the later a decision is reversed, the more has been built on top of it, and agents build on top of things *very* quickly. **Agents flatten the cost of producing code, not the cost of being wrong.** The further ahead of the feedback your spec runs, the more a wrong assumption compounds before anyone notices.

And it isn't only a theoretical worry. [Some engineers are starting to notice it](https://lnkd.in/p/es9MVCJV) day to day: when an agent hits a bug, it patches the one case in front of it rather than stepping back to question the design that caused it, even when explicitly asked to rethink. Each patch is another thing built on top of the original decision, which makes that decision more expensive to undo. Agents haven't made rework cheaper. They've made it easier to put off.

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
