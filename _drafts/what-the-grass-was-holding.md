---
layout: post
title: "What the Grass Was Holding"
categories: [Agentic-Extreme-Programming]
redirect_from:
  - "/agentic extreme programming/2026/11/21/what-the-grass-was-holding/"
tags: [extreme programming, lean, DORA, AI, agents]
icon: seedling
description: "Somewhere between the hype and the dismissal, AI is a real opportunity, but only for teams whose foundations can hold it. And some of us are busy ploughing those foundations up."
# TODO: banner image
# image-desc: ""
# image: "/images/banners/"
# image-desc-link: "/images/banners/"
---
In 1881, a land speculator named Charles Dana Wilber published a book promising settlers that the American Great Plains, long marked on maps as the "Great American Desert", wouldn't stay dry for long. All it would take was farming. Break the sod, plant crops, and the climate would change to suit them. He gave the idea a slogan that the railroads were happy to repeat: **rain follows the plough**.

It didn't, of course. But for a while, it looked as though it might.

The plains were covered in native grass, with roots that reached metres down into the soil and had held it in place through centuries of drought and wind. To anyone trying to grow wheat, though, the grass was just in the way. When wheat prices soared during the First World War, and tractors made it possible for one family to break far more ground than horses ever could, the ploughing began in earnest. <!-- VERIFY: role of tractors/mechanisation in the Great Plow-Up (Ken Burns' Dust Bowl, ep. 1) --> In the last five years of the 1920s alone, more than five million acres of native grassland on the southern plains were turned over.

The rains were good, the harvests were big, and the boom looked like proof.

Then, in the early 1930s, the rain stopped. Without the grass, there was nothing holding the soil, and it began to blow away. Dust storms, "black blizzards", rolled across the plains for years, burying fences, stripping farms down to hardpan, and pushing dust as far as the Atlantic coast. The worst of them, on 14 April 1935, became known as Black Sunday. Families lost their farms, banks failed, and hundreds of thousands of people left the plains altogether.

Nobody had thought of the grass as a foundation. It had just been in the way of the wheat.

## Ploughing up the grass

If you've spent any time in the conversation around AI and software engineering lately, you'll have heard some version of this. The practices that agile and lean teams spent decades learning (small batches, TDD, pairing, talking to the customer) are being described as friction. Relics of a time when writing code was expensive. *Why should the rules from the late 1900s still apply?* I've [written before]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}) about how tempting that argument is, and agents have made ploughing those practices up easier than ever.

The wider conversation doesn't help. It has become polarised: on one side, blind optimism, where every problem is a prompt away from solved; on the other, blind pessimism, where it's all hype and slop and best ignored. Each side's excesses seem to push the other further towards its extreme, and there's very little room left in between.

I'm somewhere in that middle. I'm genuinely excited about what AI makes possible. I'm also watching a lot of waste, and real harm, to individuals as well as to businesses, as companies throw themselves at it without asking what it needs in order to work. <!-- NOTE: consider one concrete example of the harm to individuals (e.g. layoffs justified by AI, burnout, deskilling) --> If we approach AI as what it is, a powerful new tool that has to be learned and fitted into how we work, there's a real opportunity here. If we go all in blindly, many companies are going to burn through huge amounts of runway for little or no return.

So I'll be blunt about where I stand, because I think both halves matter:

* **Ignoring AI is a professional mistake.** Teams that sit this out will fall behind the teams they compete with, they'll struggle to have the impact they want to have, and they're missing out on what is, honestly, a lot of fun.
* **Adopting AI without the foundations underneath it is worse than not adopting it at all.** Every place where a team falls short on the fundamentals is a place where AI will make them pay, and pay dearly.

And there are two ways to end up without those foundations. Some teams never had them, and are planting straight into bare soil. Others had them, and are ploughing them up because an agent makes them look unnecessary. The second group worries me more, because they're giving up something they've already paid for, and they won't notice it's gone until the rain stops.

## Why I'm excited

The tractor wasn't the villain of the Dust Bowl. The plains are farmed with machines today, more productively than ever. And I feel the same way about automation in our craft: anything we've worked out the mechanics of should be handed to a machine. The pipeline, the deploy, the tests, the boring bits nobody should have to think about. AI pushes that further than anything has before, and I have no aversion to it.

But for me, AI isn't only automation. Automation is when you've figured out the mechanics of something and teach a machine to do it for you, over and over, so you don't have to think about it anymore. AI overlaps with that heavily, but it's non-deterministic, which means I can never fully trust it as lights-out automation. Not yet, anyway.

What I *do* get from it is two things.

The first is a better way to investigate my own thinking. It's a rubber duck that talks back, in ways that beat the rubber duck. There are pitfalls, and I've [written about one of them]({% post_url 2026-11-08-whose-decision-was-that-anyway %}): we readily adopt an agent's lean as our own. So I try to go in with a view of my own, and make it argue with me rather than for me.

The second is reach. There's a lot I don't know: technologies I've never used, APIs I've never integrated. AI can get to a huge amount of information very quickly, and as long as I don't trust the first answer it gives me, as long as I interrogate what comes back, it lets me move much faster than I ever could before.

**In the past year, I've achieved in hours and days what would previously have taken me weeks.** There's no doubt about that in my mind. Anyone who claims that can't be true is either not really trying it, or is experiencing some kind of bias. <!-- NOTE: consider softening, e.g. "If you've tried it seriously and still don't believe that, I'd gently suggest looking again at how you tried it." -->

I can't say for sure why it's worked so well for me. Part of it, I suspect, is twenty-five years of building software. Not because experience stops me believing the things an agent makes up; the research is fairly clear that it doesn't. But it taught me what to look at, when something smells off, and how to keep an agent moving in small, reliable steps, so that each one gives me the confidence to take the next. Not everyone has had twenty-five years to learn that. But it's something a team can provide.

Look at what both of those uses have in common: *don't trust the first answer*. Every gain I've had has rested on habits I'd never think of ploughing up.

## The wet years

What made the Great Plow-Up so convincing was that, for a decade, it worked. The wet years hid what had been lost. The wind was always going to come; the only question was whether anything would be holding the soil when it did.

DORA's research on AI tells a similar story. The 2024 report found that as AI adoption went up, delivery throughput and stability went *down*: by an estimated 1.5% and 7.2% respectively for a 25% increase in adoption. The [2025 report](https://dora.dev/dora-report-2025/) put the explanation plainly: **AI is an amplifier**. It magnifies the strengths of high-performing teams, and the dysfunctions of struggling ones. It speeds up development, and that speed exposes whatever is weak downstream.

That fits with what DORA has been finding for over a decade: speed and stability aren't a trade-off. {% include footnotes/footnote_link.html content='The teams that deploy most often are the ones with the lowest change failure rates and the fastest recovery' count=1 %}, and it isn't a coincidence. The foundations are what let you go fast.

AI is the plough. It lets you break far more ground, far faster, than you could before. Whether that turns into a harvest or a dust storm depends on what's holding the soil.

## A map of uncharted ground

It would be easy to turn this into a list of practices: do TDD, do trunk-based development, pair, deploy continuously. But nobody has charted this territory yet, me included, and I'd be suspicious of anyone who tells you there's a single route across it. Copying another team's practices doesn't copy their foundations.

So instead, here's my chart so far: the *confidences* I think a team needs to get real value out of AI. For each one, I'll share how I've got there in the past, but that's my route, not *the* route. If your team gets the same confidence another way, you've arrived.

Rather than a starting point, I'd suggest two questions. **Which of these is your team shortest on?** That's where AI will cost you first. And **which of these is your team being told it no longer needs?** That's the grass someone is about to plough up.

## The confidences

### "I can change this without fear"

You can open any part of the codebase, change it, and know within minutes whether you broke something. The signal is a low change failure rate, and a team that doesn't flinch at the parts of the system everyone else avoids.

My route has always been TDD and a fast test suite people actually trust. AI is genuinely brilliant here: wrapping characterisation tests around the code nobody dares touch used to take weeks of archaeology. Without this confidence, though, an agent just helps you produce changes you can't verify, faster.

*The temptation: "the agent writes the tests now." But tests written by the same agent that wrote the code tend to confirm what the code does, not what it should do.*

### "If I'm wrong, I can undo it in minutes"

Something goes wrong in production and nobody panics, because putting it right is routine. The signal is a short time to restore service.

My route: good observability, rollbacks that are boring, and feature flags so that a release and a deploy aren't the same thing. AI means more change, and more change means more things going wrong. If recovery is slow and painful, every one of them costs more.

*The temptation: "the agent can just fix it forward." It can, until it's fixing forward on top of a fix it made an hour ago.*

### "I can ship this today, and again this afternoon"

Changes flow to production in small pieces, many times a day, and nobody thinks it's remarkable. The signals are deployment frequency and lead time.

My route: trunk-based development, small batches and an automated path to production. This is the confidence agents erode most quietly, because their default is the big batch: a big plan, a big diff, a big review. Without the confidence to ship small, agent output piles up as work in progress, and in Lean terms, inventory is waste.

*The temptation: "small batches were for when coding was slow." I [wrote about this one]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}) at length.*

### "We solved the right problem"

The hardest one to measure, and I'd rather be honest about that than invent a metric for it. You know you've got it when the team regularly hears from the people using what you built, and changes course because of what they hear.

My route: conversations with customers, small steps, and lately, throwaway prototypes built with agents that exist only to start those conversations (a topic I still owe you a post on). AI makes building cheap, and when building is cheap, building the wrong thing is cheap too, right up until you've built a great deal of it.

*The temptation: "we can build all the options and see." Building all the options is the plough. Someone still has to ask the customer.*

### "We all know why it works this way"

Decisions are made in the open, challenged while they're being made, and understood by more than one person. You know you've got it when anyone on the team can explain why the system is the way it is.

My route: pairing, rotating pairs, and Architecture Decision Records for the decisions that matter. With agents, more decisions than ever are being made in one person's conversation with a machine, and nobody else ever sees them.

*The temptation: "coding with an agent is like pairing." I've [argued]({% post_url 2026-11-08-whose-decision-was-that-anyway %}) that it isn't.*

## Muscle and tendon

There's a second way foundations fail, and it's subtler than ploughing them up. Anyone who's taken up a sport seriously as an adult has probably met it.

When you train hard, muscle adapts quickly: you can feel yourself getting stronger within weeks. Tendons and ligaments adapt far more slowly, over months. That gap is why people who ramp up too fast get injured: the muscle can now produce more force than the connective tissue can safely carry. Climbers know this well; a beginner's arms get strong long before their fingers do.

AI grows the muscle. Output goes up almost immediately. The connective tissue (the tests, the deployment pipeline, the shared understanding, the conversations with the customer) adapts at its own pace, and only if you train it deliberately. And everything that makes agents exciting adds load: bigger tasks, more autonomy, agents running in parallel while you're in a meeting.

So this is how I think about how far to let an agent run. **Give agents as much autonomy as your foundations can carry, and no more.** Autonomy beyond that is borrowing against a debt you can't see yet.

The early signs of that debt are easy to miss. Some engineers are [noticing](https://lnkd.in/p/es9MVCJV) that when an agent hits a bug, it often patches the one case in front of it rather than question the design that caused it. Each patch adds a little more load to whatever's underneath, and nobody feels it, until something tears.

## When the rain stops

The plough theory had in fact already failed once. Severe droughts in the 1890s should have finished it off, and mostly did, but some of its diehard proponents had an explanation ready: the ploughing simply hadn't been deep enough.

I hear an echo of that today. When AI doesn't deliver, the answer is often that the team didn't go far enough: not enough agents, not enough autonomy, too many humans in the loop. Sometimes that's true. But often the problem is what was, or wasn't, holding the soil.

The bill for AI without the foundations doesn't arrive straight away, which is what makes it dangerous. The feeling of speed arrives on day one. And as I've [argued before]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}), rework only *feels* cheap: its real cost turns up later, compounded.

So here's the strongest version of my position. **If your foundations can't carry the load, adding agents is ploughing up more grass in a wet year.** You'd be better off holding back on handing your delivery to agents until they can.

That doesn't mean ignoring AI in the meantime. Point it at the foundations you're shortest on. Use it to write the characterisation tests, to build the pipeline, to untangle the coupling, to set up the measurement that tells you where you actually stand. Some of the best uses of AI I've seen have been in replanting the grass.

## Where I've got to

In March 1935, a soil scientist named Hugh Hammond Bennett was testifying to Congress, arguing for a permanent national effort to conserve soil. He knew a dust storm from the plains was heading east, and as the story goes, he kept talking until it arrived. When the sky outside darkened, he walked the committee to the window. {% include footnotes/footnote_link.html content='The Soil Conservation Service was created that April' count=2 %}.

What followed was slow, unglamorous work. Grass was replanted. Hundreds of millions of trees went in as shelterbelts to break the wind. Farmers learned to plough along the contours of the land instead of straight across it. And the plains recovered. They're still farmed today, with machines far more powerful than anything the 1920s had, because the foundations are back underneath them.

That's what I'd want any team to take from this. Whether you've ignored AI so far, jumped in head first, or are halfway through ploughing up practices you used to rely on, the foundations on this map are all within reach, and AI can help you get to them. I'm genuinely excited about what that makes possible, and I want every team I work with to get the most out of it, without burning their runway to find out what it can't do.

But before you plough up another practice because an agent makes it look unnecessary, ask what it was holding.

{% capture footnotes %}
You'll notice I haven't used DORA's old elite/high/medium/low performance tiers. The 2025 report moved away from them in favour of seven team archetypes, each balancing performance, stability and well-being differently, which fits rather well with the idea that there's no single route.

Accounts differ on the details: some place Bennett before a Senate committee, others before the House, and the date is given as either 20 or 21 March. The dust storm, and the act that followed in April 1935, are well documented. It's also worth saying that historians still debate how much of the Dust Bowl was drought and how much was land use. Most agree it took both: the drought was the wind, but the ploughing was why there was nothing holding the soil. <!-- VERIFY: Bennett chamber and date against NRCS history -->
{% endcapture %}

{% include footnotes/footnote.html notes=footnotes %}
