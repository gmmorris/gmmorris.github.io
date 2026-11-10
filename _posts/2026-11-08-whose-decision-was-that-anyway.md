---
layout: post
title: "Whose Decision Was That, Anyway?"
date: 2026-11-08 12:00:00
categories: [Agentic Extreme Programming]
tags: [extreme programming, pairing, code review, AI, agents]
icon: seedling
description: "Agents are making our decisions upstream of review, and we're signing off on them as our own. Why I'm doubling down on pairing."
image-desc: "The Inspector at the Press"
image: "/images/banners/the-inspector-at-the-press.jpg"
image-desc-link: "/images/banners/the-inspector-at-the-press.jpg"
---
Picture a company with one job: making white beads. It isn't a real company. It's W. Edwards Deming's Red Bead experiment, a teaching exercise that has been run in quality-management seminars for decades.

Volunteers from the audience play "willing workers" and inspectors. A box holds beads, about one in five of them red and the rest white. Each worker dips a paddle into the box and lifts out a random handful, and the inspectors count the red beads in it. Red beads are defects. The workers are told, repeatedly, to produce only white ones.

They can't, of course. No matter how hard they try, they can't choose which beads the paddle picks up. The red beads were never the workers' doing. They were in the box. The system settled the result before anyone picked up a paddle, yet management on stage praises the workers with fewer red beads, scolds the ones with more and, in some versions, lays off the worst performers, and the whole room spends the day attributing the result to individuals.

The inspectors, meanwhile, did their jobs impeccably. It's a lovely, rigorous process for measuring something that was determined before any of them arrived. Deming's advice to managers was to cease depending on inspection to achieve quality. Inspection only finds defects after the fact; it doesn't change what produced them, so quality has to be built into the product in the first place. Counting red beads, however carefully, doesn't change what's in the box.

## A pairing session of one

PR review is our version of the inspectors in Deming's experiment, and [advocates of pairing](https://a4al6a.substack.com/p/stop-using-pull-requests) such as myself have long used his work against it. When agentic AI started picking up, I was naive: I assumed the flood of generated code would make pull requests painful enough to push everyone towards pairing. Instead, a lot of people have burrowed deeper into async, and some are shedding review altogether.

At first I wrote it off: perhaps people don't know how effective pairing is, so they carry on with what they know best? But what made my ears prick up was hearing people say that coding with an agent is like pairing, making superficial PR reviews sufficient, or even entirely unnecessary.

I don't think the evidence points that way. It was never the pain of volume that made me suspicious of async review; it was the delayed feedback. With AI, that delay adds an illusion of pairing: with generative AI, the other party isn't a person who shares accountability for what ships, and it has no stake in challenging the decision. With autonomous coding agents, the illusion only gets stronger.

None of this makes me less excited about the new capabilities and scale agentic AI offers, but to leverage it effectively, and get the outcomes we actually want, we need to challenge the delayed feedback loops it introduces into our decision making.

## What we learn from a coin flip

In [a recent study](https://www.anthropic.com/research/agents-judgment-calls), fifty professional analysts used an AI agent to advise a fictional farming co-operative on whether to roll out an advisory programme or discontinue it. In the scenario, the analysts are tasked with achieving a 3–4% productivity gain, and need to make four analytical judgment calls, such as how to measure productivity or how to weight the farms.

For each decision, the researchers introduced a coin flip, secretly setting which of two defensible options the agent would lean towards. It was told to hold that view, voice it, and make the best honest case for it, without lying or hiding data. None of the analysts suspected the agent had been tampered with.

The results were fascinating. **The analysts went with the agent's lean 86% of the time, where chance would give 50%.** Afterwards, 52% reported the final recommendation as being more their own than the agent's. Yet the agent's lean had influenced them too, and the difference between the two groups was within the margin of error; so essentially the same. When asked to justify their choices, 77% repeated the agent's talking points, yet only 15% mentioned the agent. Experience didn't predict who followed the lean, though most people did.

Earlier decisions shape later ones. The lean on the final decision — whether to roll out the programme or not — had a smaller effect, probably because the recommendation mostly followed from whether the estimate cleared the 3–4% target, but the four earlier coin flips alone predicted 82% of the recommendations, since the estimated productivity gain was already shaped by them.

The takeaway isn't that the agent misled anyone. **It's the influence an agent can have on the person making the decision** — no matter how well the evidence supports its lean — that is important. Here that influence was strong and statistically significant, which fits our tendency to go with a confident opinion even when it's no better supported. And we seem to have a natural habit of seeing the outcome of a conversation with an agent as more ours than the agent's, the result of our own effort.

Critically, the decisions were settled early, and nothing inspecting the result could have told the difference.

## Review is too late

Code review is inspection: it happens after the decisions are made. A sign-off is a proxy, and I've [written before]({% post_url 2022-02-23-managing-distributed-teams %}) about how we lean on proxies that are easy to read even if they are a bad signal. We read an approval as "a competent person looked at this and made their own call".

Agents make that worse in four ways:

* **Less attention.** The attention paid to the code was already thin, and agents thin it further.
* **Nothing looks wrong.** Agent output is fluent and consistent, and the tests pass. But tests written by the same system that wrote the code only confirm what the code already does, so they reassure without checking anything, and the cues that might make a reviewer slow down are gone.
* **The decision isn't in the diff.** Review has always rested on an unspoken assumption: the person who wrote the code made the decisions in it. I knew the author's experience and past work, so I could judge whether a decision came from a good understanding of the system and the problem. Agents now take many of those decisions out of people's hands, in conversations I never see as the reviewer, so that signal is weaker and more indirect, and I trust it less. A decision reached independently and one adopted from the agent look the same in the diff, and asking the author "why?" will often echo the agent's answer.
* **The inspectors share the box.** A reviewer who uses an agent is often checking the work with the same system that produced it. Models are non-deterministic, but their biases are sticky, so even a fresh run of the same model will have similar blindspots.

The inspectors are doing their jobs, but the box was loaded with red beads upstream. Reviews look more and more like a bad proxy.

The study didn't test code review, so I'm extrapolating. But I've noticed a few familiar characters in the reviews I see these days, and I describe them with a lot of love: **the Relay**, who asks the agent to review the PR and raises its comments with the author in their own voice; **the Second Pair of Eyes**, who reviews with the same model that built it, so two sets of eyes count as two votes with one set of priors; and **the Author**, who pastes the agent's answer to "why?" into the PR description and is subconsciously convinced it was their idea all along (see the 77% mentioned above).

To be transparent, I recognise all three of them in the mirror, and this isn't a criticism. Pull requests are reaching us at such a rate that the friction of delaying one feels higher than ever, and agents have lowered the barrier to saying yes and moving on. People are going to be people, and leaning on a tool that makes the easy path this easy is natural.

**Deferring to the agent is the path of least resistance.** In 77% of decisions the agent voiced a side before the participant had taken one (yes, two different measures hit 77%, I double checked my notes against the paper). It's fluent, it arrives with a ready-made justification, and accepting it costs nothing. Not accepting it means forming a view, articulating your assumptions, and arguing with something that can out-write you in seconds.

So how do we avoid the path of least resistance? In [that same post]({% post_url 2022-02-23-managing-distributed-teams %}) I asked why we'd ever deliberately add friction to how a team works, and the only good answer I found was: to remove a worse friction. Pairing might feel like adding friction, but it might be the better friction when measured against bad outcomes.

## Pairing is in the loop

Extreme programming is, and always has been, about feedback loops: the shorter your loop, the sooner you can identify and correct a mistake. Pairing is the shortest one, because decisions get challenged while they're being made, not after. That echoes Deming's work, and there's nothing novel here; we've known it for decades.

XP doesn't prescribe a specific way to pair, and every team I've been on has done it their own way. As many folks have never experienced XP, indulge me as I share what pairing looked like on the most effective engineering team I've ever been on:

Each day starts at stand-up, where you divvy up the prioritised user stories. Every two people, a pair, pick up one user story. A user story isn't a spec; it's a placeholder for a conversation with a stakeholder, customer or domain expert about a problem they have. The pair spends the day understanding that problem, identifying on small step towards solving it, implement that step and delivering it. This is repeated until the day is done or the story is completed. The next day you rotate: one engineer leaves the user story, someone new joins, and you pick up the next slice.

The point is that two people work on the problem together every day, and they rotate every day so someone new can weigh in. The feedback, the discussion and the delivery are constant, and they all happen concurrently. I describe this in more detail in [A Case Study of Two Extremes]({% post_url 2022-03-20-case-study-of-two-extremes %}), but this is just anecdotal experience; I maintain there's no *right way to pair*.

### Pairing in the age of agents

My impression from building several XP teams in the past few years, is that pairing is evolving in significant ways in the age of agentic AI. Pairs used to spend a lot of their time on syntax: the mechanics of translating an idea into working code. Agents can take that away, and I think that's great. It frees the conversation for what matters most: the problem we're solving, the design behind it, the security posture and the real implications of getting it wrong. Let the agent do the rest. Just don't let it drive the design.

I think pairing can actually be more effective now than it ever was. In a classic pair, one person drives and the other navigates. Now the agent can drive and both people can navigate: two minds on where we're going, instead of one watching someone else type. The waiting while the agent works isn't dead time either. It's when the pair talks about the next small step, the risks, and whether this is still the right thing to build.

### The catch

Pairing is the only way I know to get a real review of decisions, because it puts them in front of another person while they're being made. That assumes the pair isn't simply handing off to the agent. A second person helps, since it can feel embarrassing to let the agent decide everything when someone is watching, but two people will probably still default to whatever the agent proposes first.

So the behaviour has to change too: design thinking and conversation before anyone prompts. My hope is that two people, slowing each other down and forcing each other to articulate what they're thinking, make it less likely that the agent drives the decisions. There's a reason to think articulation matters: the study's authors suggest experts often work out what they think while weighing options, and with only one side argued, the analysts adopted the agent's assumptions without finding their own. Being observed by another teammate, and being forced to articulate what you're doing, might nudge experts to push back on the agent.

It's also an argument for diversity of experience. If experience doesn't protect an individual, one experienced reviewer isn't a safeguard. Two people with the same background tend to share assumptions without noticing, so there's nothing to say out loud. When they see the problem differently, the difference has to be put into words for the other person to follow. A less experienced engineer asking *why* the agent said what it said may be the precise nudge a more experienced person needs to actively push back.

### So why isn't everyone pairing?

Part of the reason, I think, is that the path of least resistance is to hand an agent a large task instead of a small one. It feels efficient, but a large task takes a while, so a pair ends up waiting for the machine to catch up, and that's uncomfortable: they don't know what to talk about while the code churns out. Moving in smaller steps helps, and it shortens the loop, which is what XP has always advocated for. But either way, agents still *feel* slower than our thinking and our conversation. They're always catching up, and that creates an async feedback loop that makes pairing less comfortable.

This is an area I will likely write more about in the coming months.

## Where I've got to

I don't think the answer is to use agents less. The paper ends on the thought that how we split the work between people and AI can be something we choose rather than something we drift into.

Drifting is the default. The skill is noticing when the path of least resistance is at its most enticing and pushing back, but we all know that being disciplined requires energy that we don't always have. Pairing can provide the friction that keeps a team off that path, but not magically, and not on its own. None of this negates the hard work necessary to make pairing an effective way to build products. That's a topic for a different set of posts, much of it covered already in [my series on building an effective team]({% post_url 2018-07-28-the-secret-sauce-to-an-effective-team %}).

**An approval is only ever worth the judgment behind it.** I don't always remember that myself.
