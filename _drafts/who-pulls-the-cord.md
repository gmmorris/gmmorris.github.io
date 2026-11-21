---
layout: post
title: "Who Pulls the Cord?"
categories: [Agentic-Extreme-Programming]
redirect_from:
  - "/agentic extreme programming/2026/11/21/who-pulls-the-cord/"
tags: [extreme programming, lean, DORA, AI, agents]
icon: seedling
description: "Somewhere between the hype and the dismissal, AI is a real opportunity, but it rewards the teams that already have the confidence to stop the line. Here's my map of the confidences worth having."
# TODO: banner image
# image-desc: ""
# image: "/images/banners/"
# image-desc-link: "/images/banners/"
---
In 1982, General Motors closed its assembly plant in Fremont, California. By most accounts it was one of the worst plants the company had: absenteeism running at 20% or more, over 700 outstanding grievances, and a culture where quality was something an inspector checked at the end of the line, if anyone checked at all. <!-- VERIFY: sabotage/drinking anecdotes if we want them (TAL 403) --> A union official later summed up the rule on the floor: *"You saw a problem, you stopped that line: you were fired."* <!-- VERIFY: quote and attribution (Bruce Lee, This American Life 403) -->

Two years later the plant reopened as NUMMI, a joint venture between GM and Toyota. Toyota brought the Toyota Production System. The workforce, for the most part, came back: nearly all of the production workers had worked at GM-Fremont, and they were members of the same union. Some of them were flown to Japan to learn a new way of building cars.

Above every workstation hung a cord. The *andon cord*. If you see a problem, you pull it. A light goes on, and a team leader comes over to help. If the two of you can't sort it out before the car reaches the end of your station, the line stops. At Toyota's plant in Georgetown, Kentucky, the cord was reportedly being pulled around 2,000 times a week, against {% include footnotes/footnote_link.html content='roughly twice a week at a comparable Ford plant' count=1 %}. The line rarely stops, though, because most of the time help arrives in time.

The same people who'd been told that stopping the line would get them fired were now being asked to stop it, and NUMMI went from one of GM's worst plants to one of its best. <!-- VERIFY: timeline and quality comparison (Adler's NUMMI papers / MIT Sloan) -->

GM tried to take the lesson home. Cords went up in other plants, and workers who pulled them were reprimanded for stopping production. At Van Nuys, the managers' bonuses depended on the number of cars rolling off the line, so stopping it was the last thing they wanted. Quality at Van Nuys never improved, and GM closed the plant in 1992.

GM's workers knew what happened to people who stopped the line. A new length of rope above their heads didn't change that.

## Installing cords

Most AI rollouts I see look a bit like GM installing cords. Licences get bought, agents get wired into the IDE and the CI pipeline, someone shows a slide with the number of lines of code written by AI, and everyone waits for the output to go up. Sometimes it does, for a while.

The wider conversation doesn't help. It has become polarised: on one side, blind optimism, where every problem is a prompt away from solved; on the other, blind pessimism, where it's all hype and slop and best ignored. Each side's excesses seem to push the other further towards its extreme, and there's very little room left in between.

I'm somewhere in that middle. I'm genuinely excited about what AI makes possible. I'm also watching a lot of waste, and real harm, to individuals as well as to businesses, as companies throw themselves at it without asking what it needs in order to work. <!-- NOTE: consider one concrete example of the harm to individuals (e.g. layoffs justified by AI, burnout, deskilling) --> If we approach AI as what it is, a powerful new tool that has to be learned and fitted into how we work, there's a real opportunity here. If we go all in blindly, many companies are going to burn through huge amounts of runway for little or no return.

So I'll be blunt about where I stand, because I think both halves matter:

* **Ignoring AI is a professional mistake.** Teams that sit this out will fall behind the teams they compete with, they'll struggle to have the impact they want to have, and they're missing out on what is, honestly, a lot of fun.
* **Adopting AI without the confidence underneath it is worse than not adopting it at all.** Every place where a team falls short on the fundamentals is a place where AI will make them pay, and pay dearly.

GM had the cords. What it didn't have was a workforce confident that pulling one would bring help rather than trouble, and a management confident that stopping the line would make it faster rather than slower. **You can install the cord. You can't install the confidence.**

## Why I'm excited

Toyota automated heavily, and so should we. Anything we've worked out the mechanics of should be handed to a machine: the pipeline, the deploy, the tests, the boring bits nobody should have to think about. AI pushes that further than anything has before, and I have no aversion to it.

But for me, AI isn't only automation. Automation is when you've figured out the mechanics of something and teach a machine to do it for you, over and over, so you don't have to think about it anymore. AI overlaps with that heavily, but it's non-deterministic, which means I can never fully trust it as lights-out automation. Not yet, anyway.

What I *do* get from it is two things.

The first is a better way to investigate my own thinking. It's a rubber duck that talks back, in ways that beat the rubber duck. There are pitfalls, and I've [written about one of them]({% post_url 2026-11-08-whose-decision-was-that-anyway %}): we readily adopt an agent's lean as our own. So I try to go in with a view of my own, and make it argue with me rather than for me.

The second is reach. There's a lot I don't know: technologies I've never used, APIs I've never integrated. AI can get to a huge amount of information very quickly, and as long as I don't trust the first answer it gives me, as long as I interrogate what comes back, it lets me move much faster than I ever could before.

**In the past year, I've achieved in hours and days what would previously have taken me weeks.** There's no doubt about that in my mind. Anyone who claims that can't be true is either not really trying it, or is experiencing some kind of bias. <!-- NOTE: consider softening, e.g. "If you've tried it seriously and still don't believe that, I'd gently suggest looking again at how you tried it." -->

I can't say for sure why it's worked so well for me. Part of it, I suspect, is twenty-five years of building software. Not because experience stops me believing the things an agent makes up; the research is fairly clear that it doesn't. But it taught me what to look at, when something smells off, and how to keep an agent moving in small, reliable steps, so that each one gives me the confidence to take the next. Not everyone has had twenty-five years to learn that. But it's something a team can provide.

Look at what both of those uses have in common: *don't trust the first answer*. Every gain I've had depends on being willing to stop, question, and pull my own cord.

## The line that stops is the line that flows

The counterintuitive thing about the andon cord is that Toyota's line wasn't fast *despite* people stopping it. It was fast *because* they did. A problem surfaced at the station where it was made, by the person who saw it, while it was still small. It didn't travel downstream, get built on, and turn up at final inspection as a car that needed taking apart.

That's the same finding DORA has been making for over a decade: speed and stability aren't a trade-off. {% include footnotes/footnote_link.html content='The teams that deploy most often are the ones with the lowest change failure rates and the fastest recovery' count=2 %}, and it isn't a coincidence.

DORA's research on AI tells the other half of the story. The 2024 report found that as AI adoption went up, delivery throughput and stability went *down*: by an estimated 1.5% and 7.2% respectively for a 25% increase in adoption. The [2025 report](https://dora.dev/dora-report-2025/) put the explanation plainly: **AI is an amplifier**. It magnifies the strengths of high-performing teams, and the dysfunctions of struggling ones. It speeds up development, and that speed exposes whatever is weak downstream.

In Toyota's terms, AI speeds up the line. And only a line that can stop can take the extra speed.

This is also why I keep coming back to feedback loops. The cord is feedback at the moment a defect is made, by the person making it. Inspection is feedback after the fact, by someone else. I argued in [Whose Decision Was That, Anyway?]({% post_url 2026-11-08-whose-decision-was-that-anyway %}) that code review is inspection, and that agents make it a weaker proxy than ever. The cord is the alternative. **The confidence to stop the line is what lets you speed it up.**

## A map, not a route

It would be easy to turn this into a list of practices: do TDD, do trunk-based development, pair, deploy continuously. But GM is the cautionary tale there. It copied the practice, down to the rope, and didn't get the outcome. There's no one-size-fits-all, and I'd be suspicious of anyone who tells you there is.

So instead, here's a map of the *confidences* I think a team needs to get real value out of AI. For each one, I'll share how I've got there in the past, but that's my route, not *the* route. If your team gets the same confidence another way, you've arrived.

And rather than a starting point, I'd suggest one question: **where would your team hesitate to pull the cord?** Whichever confidence you're shortest on is where AI will cost you first.

## The confidences

### "I can change this without fear"

You can open any part of the codebase, change it, and know within minutes whether you broke something. The signal is a low change failure rate, and a team that doesn't flinch at the parts of the system everyone else avoids.

My route has always been TDD and a fast test suite people actually trust. AI is genuinely brilliant here: wrapping characterisation tests around the code nobody dares touch used to take weeks of archaeology. Without this confidence, though, an agent just helps you produce changes you can't verify, faster. And remember that tests written by the same agent that wrote the code tend to confirm what the code does, not what it should do.

*Would you refactor the module everyone's scared of?*

### "If I'm wrong, I can undo it in minutes"

Something goes wrong in production and nobody panics, because putting it right is routine. The signal is a short time to restore service.

My route: good observability, rollbacks that are boring, and feature flags so that a release and a deploy aren't the same thing. AI means more change, and more change means more things going wrong. If recovery is slow and painful, every one of them costs more.

*Would you roll back on a hunch?*

### "I can ship this today, and again this afternoon"

Changes flow to production in small pieces, many times a day, and nobody thinks it's remarkable. The signals are deployment frequency and lead time.

My route: trunk-based development, small batches and an automated path to production. This is the confidence agents erode most quietly, because their default is the big batch: a big plan, a big diff, a big review. I wrote about this in [No Spec Survives Contact with the Customer]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}). Without the confidence to ship small, agent output piles up as work in progress, and in Lean terms, inventory is waste.

*Would you stop a deploy?*

### "We solved the right problem"

The hardest one to measure, and I'd rather be honest about that than invent a metric for it. You know you've got it when the team regularly hears from the people using what you built, and changes course because of what they hear.

My route: conversations with customers, small steps, and lately, throwaway prototypes built with agents that exist only to start those conversations (a topic I still owe you a post on). AI makes building cheap, and when building is cheap, building the wrong thing is cheap too, right up until you've built a great deal of it.

*Would you tell the customer you built the wrong thing?*

### "We all know why it works this way"

Decisions are made in the open, challenged while they're being made, and understood by more than one person. You know you've got it when anyone on the team can explain why the system is the way it is.

My route: pairing, rotating pairs, and Architecture Decision Records for the decisions that matter. With agents, more decisions than ever are being made in one person's conversation with a machine, and nobody else ever sees them.

*Would you overrule the agent in front of your pair?*

## Automation with a human touch

The Toyota Production System rests on two pillars. One is just-in-time. The other is *jidoka*, usually translated as "automation with a human touch".

Its roots go back to Sakichi Toyoda's looms. His Type G automatic loom, completed in 1924, would stop itself when a thread broke, rather than carry on weaving defective cloth. A machine that can detect its own problems and stop means one person can look after many machines, because they only need to step in when something's gone wrong. And when they do, the job is to fix the cause, not just restart the loom.

The andon cord is jidoka for people. And jidoka was never lights-out automation, which is exactly why I find it such a useful way to think about AI. If you accept, as I do, that we can't trust AI to run unattended, then the question becomes how to automate *with a human touch*.

Agents are now workers on our line, and that raises three questions:

* **Do they stop?** A failing check, a test that won't pass, an ambiguity in the problem: does your agent halt and ask, or does it press on?
* **Do they pull the cord, or patch around the problem?** Some engineers are [noticing](https://lnkd.in/p/es9MVCJV) that when an agent hits a bug, it often patches the one case in front of it rather than question the design that caused it. That's an agent cutting the cord. A team that lets it is installing cords and never pulling them.
* **When the line stops, does a person fix the cause?** The human touch is judgment: someone who understands *why* the line stopped, and who owns the decision about what happens next.

This is also how I think about how far to let an agent run. Bigger tasks, more autonomy, agents running in parallel while you're in a meeting: all of it is drawing on your confidence. **Give agents as much autonomy as your cord can handle, and no more.** Autonomy beyond that is borrowing against a debt you can't see yet.

An agent with no cord, on a line nobody stops, isn't going to make you faster. It's going to make you [red beads]({% post_url 2026-11-08-whose-decision-was-that-anyway %}), and lots of them.

## When nobody pulls the cord

Van Nuys had cords. It had managers who'd seen NUMMI work, and some who'd worked there. What it didn't have was the confidence, and it ended in closure.

The bill for AI without the fundamentals doesn't arrive straight away, which is what makes it dangerous. In [METR's 2025 study](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/), experienced open-source developers took 19% longer to complete tasks with AI than without it, while believing it had made them 20% *faster*. I don't think that contradicts my own experience. Those developers were working in large, mature codebases they already knew well, which is where AI's reach matters least. But it does show how easily the feeling of speed and actual speed come apart. And as I've [argued before]({% post_url 2026-11-18-no-spec-survives-contact-with-the-customer %}), rework only *feels* cheap: its real cost turns up later, compounded.

So here's the strongest version of my position. **If nobody on your team would pull the cord, adding agents adds speed to a line that can't stop.** You'd be better off holding back on handing your delivery to agents until it can.

That doesn't mean ignoring AI in the meantime. Point it at the confidence you're shortest on. Use it to write the characterisation tests, to build the pipeline, to untangle the coupling, to set up the measurement that tells you where you actually stand. Some of the best uses of AI I've seen have been in building the cord, not running the line.

## Where I've got to

The part of the NUMMI story I find most hopeful is that it was the *same workers*. The people who'd made Fremont one of GM's worst plants made NUMMI one of its best. Nobody hired better engineers. The system changed, and the confidence came with it.

That's what I'd want any team to take from this. Whether you've ignored AI so far or jumped in head first, the confidences on this map are all within reach, and AI can help you get to them. I'm genuinely excited about what that makes possible, and I want every team I work with to get the most out of it, without burning their runway to find out what it can't do.

But before you put more agents on the line, ask who's going to pull the cord, and what happens when they do.

{% capture footnotes %}
The Georgetown and Ford figures come from a BBC report from the late 2000s, and pull counts vary a lot between sources and counting methods. Treat them as an illustration of the culture rather than a benchmark. It's also worth knowing that a pull doesn't stop the whole factory: it stops your section of line, at a fixed position, and only if the problem can't be resolved in time. <!-- VERIFY: BBC report year (2007 vs 2008) -->

You'll notice I haven't used DORA's old elite/high/medium/low performance tiers. The 2025 report moved away from them in favour of seven team archetypes, each balancing performance, stability and well-being differently, which fits rather well with the idea that there's no single route.
{% endcapture %}

{% include footnotes/footnote.html notes=footnotes %}
