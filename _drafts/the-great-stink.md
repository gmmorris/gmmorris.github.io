---
layout: post
title: "The Great Stink"
categories: [Agentic-Extreme-Programming]
redirect_from:
  - "/agentic extreme programming/2026/11/21/the-great-stink/"
tags: [extreme programming, lean, DORA, AI, agents]
icon: seedling
description: "The flush toilet was a triumph. It also sent far more downstream than Victorian London could carry. AI is doing the same to our engineering systems, and the answer, then and now, is foundations."
# TODO: banner image
# image-desc: ""
# image: "/images/banners/"
# image-desc-link: "/images/banners/"
---
At the Great Exhibition of 1851, in the glass halls of the Crystal Palace, a plumber named George Jennings installed something most visitors had never used: public flushing toilets. They cost a penny a go, and over the months the exhibition was open, more than 827,000 people paid it. It's where the British got the phrase "to spend a penny".

The flush toilet caught on fast. It was cleaner, more convenient and more civilised than anything that came before, and the number of water closets in London nearly doubled in the first half of the 1850s.

Every one of them sent far more water downstream than the city had ever had to deal with. London's waste had mostly gone into cesspits, some 200,000 of them, and the cesspits overflowed. The authorities' answer was to have houses connect their drains to the sewers instead. But the sewers had been built to carry rainwater, and they emptied straight into the Thames: the same river much of London drew its drinking water from. Cholera swept through the city more than once. A commission set up to fix the drainage considered dozens of plans and authorised none of them.

Then came the hot summer of 1858. The river, by now an open sewer running through the middle of the capital, began to smell so badly that it became known as the Great Stink. Parliament, which sat right on the riverbank, hung curtains soaked in chloride of lime over its windows. Benjamin Disraeli described the Thames as *"a Stygian pool, reeking with ineffable and intolerable horrors"*. After years of argument, a bill to fund a proper sewer system passed in about eighteen days.

The flush toilet wasn't the problem. It was a triumph, and nobody seriously suggested going back to chamber pots. It just sent far more downstream, into a system that had never been safe in the first place.

## Spending a penny

Yes, I'm about to compare AI-generated code to sewage. Bear with me; that includes mine.

Engineers have said for years that **code is a liability, not an asset**. Every line has to be read, tested, deployed, run, understood and maintained by someone, for as long as it lives. The value is in what it does for the people using it, and the code is the cost of getting there.

AI has made producing that code almost effortless, the way the flush toilet made disposal effortless. That's a genuine improvement, and I'll come to why I'm excited about it. But all of it still flows downstream: into review, into the test suite, into the deployment pipeline, into production, into the heads of the team who'll have to change it next year, and in front of the customers who'll have to live with it.

Most teams have always had some practices that were quietly unsafe: tests nobody trusts, a deploy that needs a particular person, pull requests that sit for days, a customer nobody talks to. At the old volume, we got away with them. The cesspit was nasty, but it held. Turn up the flow, and those practices don't just become bottlenecks, they become the point where everything overflows.

The wider conversation doesn't help. It has become polarised: on one side, blind optimism, where every problem is a prompt away from solved; on the other, blind pessimism, where it's all hype and slop and best ignored. Each side's excesses seem to push the other further towards its extreme, and there's very little room left in between.

I'm somewhere in that middle. I'm genuinely excited about what AI makes possible. I'm also watching a lot of waste, and real harm, to individuals as well as to businesses, as companies throw themselves at it without asking what it needs in order to work. <!-- NOTE: consider one concrete example of the harm to individuals (e.g. layoffs justified by AI, burnout, deskilling) --> If we approach AI as what it is, a powerful new tool that has to be learned and fitted into how we work, there's a real opportunity here. If we go all in blindly, many companies are going to burn through huge amounts of runway for little or no return.

So I'll be blunt about where I stand, because I think both halves matter:

* **Ignoring AI is a professional mistake.** Teams that sit this out will fall behind the teams they compete with, they'll struggle to have the impact they want to have, and they're missing out on what is, honestly, a lot of fun.
* **Adopting AI without the foundations to carry it is worse than not adopting it at all.** Every place where a team falls short on the fundamentals is a place where AI will make them pay, and pay dearly.

## Why I'm excited

Nobody in 1858 was arguing for a return to the chamber pot, and I'm not arguing for a return to hand-writing every line either. Anything we've worked out the mechanics of should be handed to a machine: the pipeline, the deploy, the tests, the boring bits nobody should have to think about. AI pushes that further than anything has before, and I have no aversion to it.

But for me, AI isn't only automation. Automation is when you've figured out the mechanics of something and teach a machine to do it for you, over and over, so you don't have to think about it anymore. AI overlaps with that heavily, but it's non-deterministic, which means I can never fully trust it as lights-out automation. Not yet, anyway.

What I *do* get from it is two things.

The first is a better way to investigate my own thinking. It's a rubber duck that talks back, in ways that beat the rubber duck. There are pitfalls, and I've [written about one of them]({% post_url 2026-11-08-whose-decision-was-that-anyway %}): we readily adopt an agent's lean as our own. So I try to go in with a view of my own, and make it argue with me rather than for me.

The second is reach. There's a lot I don't know: technologies I've never used, APIs I've never integrated. AI can get to a huge amount of information very quickly, and as long as I don't trust the first answer it gives me, as long as I interrogate what comes back, it lets me move much faster than I ever could before.

**In the past year, I've achieved in hours and days what would previously have taken me weeks.** There's no doubt about that in my mind. Anyone who claims that can't be true is either not really trying it, or is experiencing some kind of bias. <!-- NOTE: consider softening, e.g. "If you've tried it seriously and still don't believe that, I'd gently suggest looking again at how you tried it." -->

I can't say for sure why it's worked so well for me. Part of it, I suspect, is twenty-five years of building software. Not because experience stops me believing the things an agent makes up; the research is fairly clear that it doesn't. But it taught me what to look at, when something smells off, and how to keep an agent moving in small, reliable steps, so that each one gives me the confidence to take the next. Not everyone has had twenty-five years to learn that. But it's something a team can provide.

Look at what both of those uses have in common: *don't trust the first answer*. The gains are real, and every one of them has depended on what happens downstream of the agent.

## Downstream

DORA's research on AI tells this story in numbers. The 2024 report found that as AI adoption went up, delivery throughput and stability went *down*: by an estimated 1.5% and 7.2% respectively for a 25% increase in adoption. The [2025 report](https://dora.dev/dora-report-2025/) put the explanation plainly: **AI is an amplifier**. It magnifies the strengths of high-performing teams, and the dysfunctions of struggling ones. It speeds up development, and that speed exposes whatever is weak downstream.

That fits with what DORA has been finding for over a decade: speed and stability aren't a trade-off. {% include footnotes/footnote_link.html content='The teams that deploy most often are the ones with the lowest change failure rates and the fastest recovery' count=1 %}, and it isn't a coincidence. The foundations are what let you go fast.

Lean has a name for what happens when flow outruns capacity: inventory. Work that's been started but can't move on is waste, and it piles up in front of the bottleneck. With agents, the bottleneck has moved. Writing code used to be the slow part. Now it's everything after it, and if those stages were already fragile, they don't just slow down. They overflow.

## A map of uncharted ground

It would be easy to turn this into a list of practices: do TDD, do trunk-based development, pair, deploy continuously. But nobody has charted this territory yet, me included, and I'd be suspicious of anyone who tells you there's a single route across it. Copying another team's practices doesn't copy their foundations.

So instead, here's my chart so far: the *confidences* I think a team needs to get real value out of AI. For each one, I'll share how I've got there in the past, but that's my route, not *the* route. If your team gets the same confidence another way, you've arrived.

Rather than a starting point, I'd suggest two questions. **Which of these is your team shortest on?** That's where AI will cost you first. And **where is your team quietly dumping into the river today?** Whatever you've been getting away with at the old volume is what will overflow at the new one.

## The confidences

### "I can change this without fear"

You can open any part of the codebase, change it, and know within minutes whether you broke something. The signal is a low change failure rate, and a team that doesn't flinch at the parts of the system everyone else avoids.

My route has always been TDD and a fast test suite people actually trust. AI is genuinely brilliant here: wrapping characterisation tests around the code nobody dares touch used to take weeks of archaeology. Be careful, though: tests written by the same agent that wrote the code tend to confirm what the code does, not what it should do.

*At the new volume: a test suite nobody trusts becomes many times more changes nobody can verify.*

### "If I'm wrong, I can undo it in minutes"

Something goes wrong in production and nobody panics, because putting it right is routine. The signal is a short time to restore service.

My route: good observability, rollbacks that are boring, and feature flags so that a release and a deploy aren't the same thing.

*At the new volume: more change means more things going wrong. If recovery is slow and painful, every one of them costs more, and they start to overlap.*

### "I can ship this today, and again this afternoon"

Changes flow to production in small pieces, many times a day, and nobody thinks it's remarkable. The signals are deployment frequency and lead time.

My route: trunk-based development, small batches and an automated path to production. This is the confidence agents erode most quietly, because their default is the big batch: a big plan, a big diff, a big review. I wrote about this in [No Spec Survives Contact with the Customer]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}).

*At the new volume: a deploy that needs a particular person, or a pull request that waits days for review, becomes the cesspit everything else backs up into.*

### "We solved the right problem"

The hardest one to measure, and I'd rather be honest about that than invent a metric for it. You know you've got it when the team regularly hears from the people using what you built, and changes course because of what they hear.

My route: conversations with customers, small steps, and lately, throwaway prototypes built with agents that exist only to start those conversations (a topic I still owe you a post on).

*At the new volume: when building is cheap, building the wrong thing is cheap too, right up until you've built a great deal of it, and every line of it is a liability.*

### "We all know why it works this way"

Decisions are made in the open, challenged while they're being made, and understood by more than one person. You know you've got it when anyone on the team can explain why the system is the way it is.

My route: pairing, rotating pairs, and Architecture Decision Records for the decisions that matter.

*At the new volume: more decisions than ever are being made in one person's conversation with a machine, and [nobody else ever sees them]({% post_url 2026-11-08-whose-decision-was-that-anyway %}).*

## Muscle and tendon

Anyone who's taken up a sport seriously as an adult has probably met a version of this. When you train hard, muscle adapts quickly: you can feel yourself getting stronger within weeks. Tendons and ligaments adapt far more slowly, over months. That gap is why people who ramp up too fast get injured: the muscle can now produce more force than the connective tissue can safely carry. Climbers know this well; a beginner's arms get strong long before their fingers do.

AI grows the muscle. Output goes up almost immediately. The connective tissue (the tests, the deployment pipeline, the shared understanding, the conversations with the customer) adapts at its own pace, and only if you train it deliberately. And everything that makes agents exciting adds load: bigger tasks, more autonomy, agents running in parallel while you're in a meeting.

So this is how I think about how far to let an agent run. **Give agents as much autonomy as your foundations can carry, and no more.** Autonomy beyond that is borrowing against a debt you can't see yet.

The early signs of that debt are easy to miss. Some engineers are [noticing](https://lnkd.in/p/es9MVCJV) that when an agent hits a bug, it often patches the one case in front of it rather than question the design that caused it. Each patch is a little more sent downstream, and nobody notices the smell until the weather turns.

## Before the summer

London knew it had a problem long before 1858. There had been cholera outbreaks, reports, a commission, and dozens of plans. What it didn't have was the will to act until the smell reached Parliament's windows. Then it found the money in weeks.

I see a lot of teams in the years before 1858. The signs are there: a review queue that keeps growing, incidents that keep repeating, a codebase that's harder to change every month. And the bill for AI without the foundations doesn't arrive straight away, which is what makes it so easy to defer. In [METR's 2025 study](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/), experienced open-source developers took 19% longer to complete tasks with AI than without it, while believing it had made them 20% *faster*. I don't think that contradicts my own experience. Those developers were working in large, mature codebases they already knew well, which is where AI's reach matters least. But it does show how easily the feeling of speed and actual speed come apart. And as I've [argued before]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}), rework only *feels* cheap: its real cost turns up later, compounded.

So here's the strongest version of my position. **If what's downstream can't carry the flow, turning the flow up just puts more sewage in the river.** You'd be better off holding back on handing your delivery to agents until it can.

That doesn't mean ignoring AI in the meantime. Point it at the foundations you're shortest on. Use it to write the characterisation tests, to build the pipeline, to untangle the coupling, to set up the measurement that tells you where you actually stand. Some of the best uses of AI I've seen have been in digging the sewers.

## Where I've got to

The engineer London turned to was Joseph Bazalgette. Over the following years, his teams built some 82 miles of great intercepting sewers to catch the waste before it reached the river, fed by around 1,100 miles of smaller street sewers, and carried it away downstream of the city. The work was largely complete by 1875, and cholera never again took hold in London the way it had.

Bazalgette designed the system for a population roughly double the one London had at the time, and {% include footnotes/footnote_link.html content="as the story goes, he then doubled the size of the pipes on top of that" count=2 %}: "we're only going to do this once, and there's always the unforeseen." By the time he died, London's population had more than doubled. His sewers are still in use today; the city only recently finished a new "super sewer" beneath the Thames to extend them.

London didn't give up the flush toilet. It built something that could carry it, with room to spare, and then got on with growing.

That's what I'd want any team to take from this. Whether you've ignored AI so far or jumped in head first, the foundations on this map are all within reach, and AI can help you build them. I'm genuinely excited about what that makes possible, and I want every team I work with to get the most out of it, without burning their runway to find out what it can't do.

But before you turn up the flow, find out where it goes.

{% capture footnotes %}
You'll notice I haven't used DORA's old elite/high/medium/low performance tiers. The 2025 report moved away from them in favour of seven team archetypes, each balancing performance, stability and well-being differently, which fits rather well with the idea that there's no single route.

The quote is repeated everywhere, including by the Institution of Civil Engineers, but I couldn't find a primary source for it, so take it as legend rather than record. The part that's well documented is that the system was sized for a far larger population than London had at the time. There's a lovely irony in the story too: most of the people who pushed for the sewers believed disease spread through bad air, the "miasma" theory, rather than through contaminated water, as John Snow had argued. They built the right thing for the wrong reason. Which, I suppose, is another argument for focusing on the outcome rather than the route. <!-- VERIFY: Bazalgette quote provenance; "cholera never again" (1866 East End outbreak hit an area not yet connected) -->
{% endcapture %}

{% include footnotes/footnote.html notes=footnotes %}
