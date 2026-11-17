---
layout: post
title: "Old Men Yelling at Specs"
categories: [Agentic Extreme Programming]
tags: [extreme programming, spec-driven development, wicked problems, customers, AI, agents]
icon: seedling
description: "Spec-driven development will be misunderstood the same way Agile was. It works for discovering one small step of a wicked problem with the customer, and fails when we use it to plan the whole thing ahead of time."
image-desc: "The Clockmaker's Counter"
image: "/images/banners/wicked-problems.png"
image-desc-link: "/images/banners/wicked-problems.png"
---


"This is the final form of the capsule," says the engineer in [*The Right Stuff*](https://www.youtube.com/watch?v=C-qEmmpGYvA), and it is, for about two minutes. His audience is the Mercury Seven: America's first astronauts, the best pilots the military had, and the men who'll be sitting in that thing when it leaves the atmosphere. They're the only people in the room whose lives depend on it, yet nobody thought to show it to them until it was done, and it shows.

The machine doesn't need them at all. It flies itself. There's no window, no hatch they can open, nothing to steer with. "We want a window," says Al Shepard, and by the end of the scene the astronauts have all three. That's what they gained, but what the engineer gained is just as critical: a correct understanding of what he's been building. It isn't a capsule, it's a *spacecraft*. And the man inside isn't the "astronaut occupant"; he's the *pilot*.

*No spec survives contact with the customer.* Months of careful design had produced exactly the right machine for a passenger. But his customer was a *pilot*.

## Here we go again

If you've been following the debate around AI agents lately, some of this may sound familiar. It's at the heart of an argument playing out a new, but as old as engineering.

On one side are veterans of the agile movement. They watch a team hand an agent a feature request, get back a few thousand lines of `plan.md`, approve it, and let the agent build the lot. They recognise the shape immediately: requirements gathered up front, a big document signed off, a large build, and the customer at the far end of it. *That's waterfall*, they shout, *we spent twenty years getting away from this.*

On the other side are the people actually shipping with agents, who are tired of being told they're doing it wrong by people who learned their craft at a time where constraints were objectively different. The tools have changed. Writing a spec used to be expensive and now it's nearly free. Rework used to be painful and now an agent will rewrite the module before lunch. *Why should the rules from the late 1900s still apply?*

What they're arguing about is spec-driven development (SDD), and listening to both sides, I have landed on a hunch: **SDD is going to be misunderstood in exactly the way agile was.** 

As a guiding principle, used to work out the next small step of a problem *with* the customer, SDD might be genuinely useful, and closer to XP than either camp would like to admit. Used to plan the whole problem ahead of time, it fails, in precisely the way XP set out to avoid. People being people, I believe most will take the path of least resistence, which is precisely why XP failed to gain traction and why SDD is doomed to fail as well.

### Small steps, big specs

The idea behind SDD is simple: before an agent writes any code, you write down what you want built and why, and the agent turns that into a plan which is reviewed, approved and documented accordigly. The agent is then sent off to implement and ship the feature. It answers a real problem agents created: the conversation between an engineer and an agent, where much of the thinking happens, lives in an ephemeral terminal and is gone when the session ends. A spec gives those decisions somewhere to live.

Its advocates aren't asking for a big spec up front. Many argue for [small steps, each suitably documented](https://brooker.co.za/blog/2026/04/09/waterfall-vs-spec), with the spec evolving alongside the code. But in practice, [some are finding](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html) that even a small bug fix turns into four user stories with sixteen acceptance criteria. The advocates ask for small steps, and the tools blow them up anyway.

For agents, it seems, a *big spec* is the default behaviour, making it the path of least resistance, and most of us will likely take it.

## Why XP put the customer in the room

XP has never been big on specs. The Agile Manifesto, which Kent Beck co-signed, values "working software over comprehensive documentation", and {% include footnotes/footnote_link.html content="XP's answer to the spec was the conversation" count=1 %}. But XP conversation over documentation a *safe* bet, and that starts with the customer in the room.

When Kent wrote *Extreme Programming Explained* in 1999, **On-Site Customer** was one of the original twelve practices: a real customer, sitting with the team, answering questions and making priority calls as the work happened.

That customer wasn't meant to be a product manager, or a stakeholder with opinions. It was meant to be someone who would actually use the software: someone who does the job, lives and breathes the domain, and knows what they need because they need it every day.

That's who the astronauts in *The Right Stuff* were: people who'd fly the thing, looking at what had been built for them. The engineers weren't careless. They'd built a sound answer to the problem as they understood it. Tasked with launching a person out of the atmosphere, they wrote a spec that did just that. They may have spoken to a dozens pilots in writing their spec, but none of those pilots mentioned needing a window, because it never crossed their mind that the engineers tasked with building a spacecraft wouldn't know that. No one told them what the spacecraft meant to the people flying it: that they were pilots, not passengers. That only surfaced when the people who'd do the job saw what was being built.

It's easy to misintepret the guardrail of an on-site customer as simple convenience: someone available to ask, but that was never the point. **XP starts from the assumption that requirements are *discovered*, not specified**. No document captures them up front, because you don't know what the customer needs until you've built a little and watched them react, and often they don't know either. That's why a user story was never a spec, but a placeholder for a conversation.

### Talk is cheap

This is all part of XP's devious scheme to nudge us into a path of least resistence that is more likely to produce the outcomes we want.

A developer with an unanswered question has two options: stall, or guess. Stalling is expensive, so most people guess, and every guess is a small bet. Sitting your team together, including the customer, makes it cheaper to answer questions, so people ask instead.

I've always liked the maxim that: **Every line of code is a business decision**. Whether an expired discount still applies at checkout, what happens to a half-finished order, which error a customer sees and what it tells them: none of these feel like business decisions when you're writing them, and all of them are. A developer who isn't regularly talking to the customer, and to the rest of the business, is still making those decisions. They're just making them alone.

I hear Spotify have a saying internally, *"Talk is cheap"*. usually a put-down, the Spotify team use it to mean the opposite: debate thoroughly before building, because talking costs very little and building the wrong thing costs a great deal. That's the economics behind the on-site customer.

### A wrong guess compounds

A five-minute conversation is the cheapest feedback loop there is; but it's also the first conversation agents and specs let us skip. Why ask anyone, when the agent makes a guess for you and bakes it into a spec instead? A skipped conversation turns into a guess, and guesses compound.

Misunderstandings get built on, so the cheapest moment to correct one is the moment it happens. Feedback in minutes beats feedback each iteration, which beats feedback at the end. Having a customer in the room was always a bet that their time cost less than building the wrong thing. Take them away and the cost bends right back up, and the conversation is skipped.

This is why the practice was about being *together*, not just being available. Context travels through conversation, overheard talk (aka [Osmotic Communication]({% post_url 2022-02-20-remote-isnt-distributed %})) and shared artefacts, not through handoffs. The on-site customer didn't just answer questions. They were *around*, and the team absorbed the domain by being near it.

This is the same argument behind pairing, TDD, automated testing, and many other XP practices. Emerse yourself in a system offast feedback loops, in the right places, and you produce better outcomes.

## Why we skip conversations

Agents haven't changed why the conversation matters. They've changed how easy it is to do without it, and what it costs when you do.

### The guess got fluent

The stall is gone. You never have to wait for an answer, because the agent will happily fill the gap, with a business rule that sounds plausible and a justification to match. **But filling the gap is still guessing.** It's just guessing fluently, and at scale, and the developer is now often not even the one making the guess. I [wrote recently]({% post_url 2026-11-08-whose-decision-was-that-anyway %}) about how readily we adopt an agent's lean as our own. A business rule invented by an agent, accepted by an engineer and buried in a spec is a business decision made by two wrong parties, neither of whom even remembers making.

### Rework only feels cheap

A common argument against my thesis is that agents make rework cheap. That's true in the short term: if you catch a mistake the same afternoon, an agent really can make undoing it almost free. But the later a decision is reversed, the more has been built on top of it, and agents build on top of things *very* quickly. **Coding agents flatten the cost of producing code, not the cost of being wrong.**

This isn't only a theoretical worry. [Some engineers are starting to notice it](https://lnkd.in/p/es9MVCJV) day to day: when an agent hits a bug, it often patches the one case in front of it rather than stepping back to question the design that caused it, even when explicitly asked to rethink. Each patch is another thing built on top of the original decision, which makes that decision more expensive to undo. Agents haven't made rework cheaper. They've made it easier to put off.

That changes how the customer bet looks. If rework feels free, the customer's time starts to look expensive by comparison, and putting them in the room looks like a bad trade. That's the trap. The rework only *feels* free because its real cost turns up later, compounded, on a future sprint.

### Decisions made alone

More and more decisions are being made in silos: one engineer, one agent, one long conversation nobody else sees. The context still exists. It's just trapped in a chat history.

You could argue agents have broken the "talk is cheap" logic. *If building is nearly free too, why bother talking first?* But the comparison was never really talk versus building. It was talk versus **being wrong**, and being wrong hasn't got any cheaper. And when we're making more decisions than ever, alone with an agent, **the conversation with another person is the only thing that forces us to second guess our work.** Talk is still cheap. It's never been worth more.

## Tame problems and wicked problems

By now you might be thinking: surely this is a solved problem. If specs are full of guesses, talk to the customer *before* you write one. Do the requirements gathering properly: interview the people who'll use it, sit with them, write down what they tell you. Then the spec isn't a guess. It's a record.

Sometimes that works. Whether it does depends less on how hard you try than on what kind of problem you're facing.

In 1973, Horst Rittel and Melvin Webber published *Dilemmas in a General Theory of Planning*, and gave us a distinction I keep coming back to: *tame problems* and *wicked problems*.

A tame problem can be fully specified before you start. You know when you've solved it, and the solution is either right or wrong. A wicked problem is different: you can't define it until you've tried to solve it, there's no point at which it's clearly done, and every attempt changes the problem. As they put it, *the information needed to understand the problem depends on one's idea for solving it*.

I want to be clear about this, because the agile camp often isn't: **for tame problems, writing the spec up front is fine, and often the best thing to do.** A CSV parser, a migration between two well-documented APIs, a CRUD service over a known schema. Write it down, hand it to the agent, check the result. That's where spec-driven development is a no-brainer.

**Wicked problems are where it breaks.** Not because people aren't disciplined enough to write a good spec, and not because nobody asked the customer. Requirements gathering assumes the customer already knows what they need and is just waiting to be asked. On a wicked problem they don't, and neither do you. The astronauts didn't know to ask for a window until they saw a spacecraft without one. The information the spec needs **doesn't exist yet**. It's created by building something small, putting it in front of people, and watching what they do with it.

### Wicked problems in disguise

The obvious wicked problems aren't the dangerous ones. Nobody sits down to spec "fix healthcare" in one go. The dangerous ones look tame: a checkout flow, an onboarding form, a reporting dashboard. They look like CRUD until real people start using them, and then they turn out to be about trust, or fear, or politics, or something nobody in the planning meeting would have guessed.

**You often can't tell a problem is wicked until you've started building it.** Which means the first step of any spec has to be small enough to tell you what kind of problem you're dealing with.

## Why we reach for the big spec anyway

So if most of a big spec is going to be wrong, why does it keep winning?

I've [written before]({% post_url 2026-11-08-whose-decision-was-that-anyway %}) about the path of least resistance, and this is another version of it. **The customer's attention is the scarcest thing on any project.** Every conversation has to be booked, prepared for and followed up. Writing everything down once, and sparing everyone the conversations, is enormously tempting. Agents have made it almost free. So specs balloon, because the cheapest thing to produce is more spec.

And for most engineers, the customer was never in the room anyway. In most companies I've worked with, the customer isn't someone who turns up asking for things. It's someone the sales team spent months courting, and account managers can be fiercely protective of them, often with good reason. Engineers are honest about the product in ways that can be alarming to a customer who's still deciding whether to trust you. So there are guardrails, and gatekeeping, and an hour a fortnight if you're lucky.

This isn't a new problem. Even XP's on-site customer didn't survive contact with reality. In the second edition, in 2004, Beck reframes customer involvement as something you build up to rather than start with. The industry has found that a full-time customer is hard to come by, and has filled the gap with proxies. But Beck didn't drop the principle, instead he made it a property of the team, in the form of cross-functional domain experts who sit alongside the engineers.

Back then, proxies filled the gap. Today, the big spec does.

## Using agents to get to the customer

If the agent can build something before the meeting is booked, then maybe the meeting should be about what it built.

One approach I've been experimenting with: build a throwaway prototype, and when you show it to a customer, frame it as **something you built for a different customer**. It isn't scalable, it isn't for sale, and it isn't on the roadmap. You're showing it to them because they seem engaged in the problem and you'd value their reaction. <!-- TODO: finish this thought, the original message was cut off -->

That framing does a lot of work. It lowers the stakes for the sales team, because nobody is promising anything. It lowers the stakes for the customer, who can be honest without worrying they're committing to it. And it uses the agent's speed to *start* the conversation, instead of using it to avoid one.

## Where I've got to

The old men are right: the customer matters more than the spec, and on wicked problems a spec that runs ahead of the feedback will be wrong in ways that compound. The young people are right too: the tools really have changed, and the way we reach the customer, and what we bring to them, should change with them.

**Write the spec for the next step, not the whole problem.** Then go and find out what you got wrong.


{% capture xp-decision-documentatin %}
This has a cost, and I've felt it. On the XP teams I've been part of, knowledge lived in conversations, which meant it lived in people. The old-timers knew why the system worked the way it did, and when they left, the reasons often left with them. Tests were meant to be the documentation, and they're good at recording *what* the software does, but in my experience they're poor at recording *why*. I've [written before]({% post_url 2022-02-22-a-chain-of-archived-context %}) about how much context we lose this way, and it's part of why the appeal of SDD resonates with me. That said, I'm a big advocate of [Architecture Decision Records](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions) (ADRs) as the answer to this, rather than a spec for every piece of code written. I suspect we'll end up with far more specs than we ever needed ADRs.
{% endcapture %}

{% include footnotes/footnote.html notes=xp-decision-documentatin %}
