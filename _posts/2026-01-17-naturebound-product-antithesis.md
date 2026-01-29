---
layout: post
title: "NatureBound II: Testing the Thesis"
date: 2026-01-29 12:00:00
categories: [NatureTech]
tags: [product-management, biodiversity, agriculture, startups, climate]
icon: seedling
description: "Examining where our product thesis met reality - what we got wrong about building observability for nature, and what that teaches us about the space."
image-desc: "Birds in Platinotype"
image: "/images/banners/birds-in-platinotype-2.png"
image-desc-link: "https://www.flickr.com/photos/biodivlibrary/51280295750/in/album-72157719475318174"
---

In [Part 1: A Product Thesis]({% post_url 2026-01-10-naturebound-product-thesis %}), I laid out what my co-founders and I believed to be true when we built NatureBound.
The thesis was straight forward: corporations need biodiversity data for reporting, they'll fund data collection as part of compliance, this data can generate actionable insights for farmers and agronomists, these insights create measurable improvements, and improvements justify continued investment in a positive feedback loop.

The mechanism was elegant. The corporate sustainability officer gets compliance-ready reports. The food buyer de-risks their supply chain. The agronomist gains capabilities that let them compete with larger consultancies. The farmer cuts costs and improves yields. Everyone wins, and the ecosystem benefits from reduced chemical loading.

It was compelling enough that we spent almost two years building toward it. Compelling enough that early investors, advisors, partners and customers saw the logic. But compelling isn't the same as valid.

## Product Antithesis

**A product antithesis is the mirror image of your thesis** - it's where you actively try to prove yourself wrong. It's about testing your hypotheses as rigorously as possible, looking hard in the mirror to find the things that will kill your idea, and evolving your understanding based on what you learn. The goal isn't to defend your vision; it's to disprove your thesis as early as possible, before you've invested years building something nobody wants.

Every compelling vision has blind spots. Every elegant thesis has edge cases that don't fit. The antithesis isn't about admitting defeat, but rather about surfacing the weakest links in your thinking while you can still change course. It's the discipline of seeking out the uncomfortable truths that invalidate your assumptions, rather than waiting for reality to do it for you.

### What an Antithesis Is (and Isn't)

When a startup fails, there's a natural tendency to focus on execution: we didn't move fast enough, we ran out of runway, we hired the wrong people, we couldn't raise the next round. These are all real constraints, and they all matter. But they're not the most interesting questions to ask when examining what happened.

The more valuable question is: **Was the underlying hypothesis valid?** Not "Could we have executed better?" but "Were we solving the right problem in the right way for the right people?". This matters because if the thesis was fundamentally sound, someone else - maybe even me, in a different context - could pick it up and succeed where we didn't. But if the thesis itself was flawed, then no amount of execution excellence would have saved us.

So let me be clear about what this post is not: this is not a post-mortem about why NatureBound failed as a company. I'm not going to dissect our fundraising strategy, our go-to-market execution, or our team dynamics. Those are important questions, but they're not what I'm exploring here. This is about the product thesis itself. About potential invalidations we hadn't disproved by the time the company folded. About ways the thesis could be fundamentally wrong that we would need to take seriously if we ever picked this idea up again.

These aren't conclusions about what we got wrong - the company shut down, but that doesn't definitively prove which assumptions were invalid. What follows are the hardest questions, the ones that could kill the idea if they turn out to be true. Some we saw signals for. Others remain open questions. But all of them deserve rigorous examination, because if I'm only willing to defend the thesis, I haven't learned anything.

### Antithesis One: The Compliance Funding Model

{% include callout.html content="The biodiversity data needed for compliance reporting is far less than what's needed to generate actionable insights - meaning corporates will only fund the former, not the latter." %}

Here's what we believed: corporations facing TNFD and CSRD reporting requirements would need farm-level biodiversity data, and they'd pay for platforms that could collect, integrate, and report on that data. This spending would fund the data collection infrastructure that, as a byproduct, could generate insights for farmers and agronomists.

But what if compliance doesn't actually require the kind of detailed, holistic data we envisioned? What if companies can satisfy their reporting obligations with much cheaper, less precise approaches - consultant-written estimates, regional proxies, or industry averages that auditors will accept? If the compliance bar is lower than we assumed, then the funding we expected for detailed data collection evaporates.

The gap here is subtle but critical. Generating actionable insights in a complex domain like biodiversity requires a holistic picture - interlacing multiple data sources across time to understand ecosystem dynamics. But TNFD compliance might only require point-in-time snapshots and species lists. If corporates will only pay for what they need for reporting, they won't fund the richer data collection that would enable meaningful recommendations for farmers and agronomists.

Even more fundamentally, what if corporate sustainability teams simply don't have the budget authority we assumed? Sarah might desperately want real biodiversity data, but if her CFO views sustainability reporting as a compliance tax to be minimised rather than a strategic investment, she's not buying a platform subscription - she's hiring the cheapest consultant who can tick the regulatory boxes.

We saw signals of this in customer conversations - sustainability officers expressed genuine interest, but when discussions turned to budget, the numbers they mentioned were often an order of magnitude smaller than what we'd need. We also had a pilot project where a corporate initially showed willingness to contribute to data collection - in their case, they genuinely wanted to understand their impacts and dependencies, not just tick compliance boxes. But as the numbers became clearer, they pulled back. The cost of collecting enough data to build the holistic picture we'd need was more than they could justify, even with genuine intent. The gap between "data we can afford" and "data for decision-making" may be wider than our thesis assumed.

### Antithesis Two: The Actionability Gap

{% include callout.html content="Converting fragmented biodiversity data into actionable recommendations requires too much context-specific expertise to automate or scale." %}

Our thesis assumed that once we interlaced multiple data sources - eDNA, remote sensing, farm management data, environmental context - we could generate actionable insights relatively systematically. The [aphid and ladybird example from Part 1]({% post_url 2026-01-10-naturebound-product-thesis %}) works beautifully because it's a well-understood relationship with clear interventions.

But what if most ecological relationships aren't like aphids and ladybirds? What if they're too complex, too context-dependent, and require too much expertise to interpret systematically? When you're looking at eDNA results showing the presence of certain bat species, bioacoustic data on their activity patterns, remote sensing of hedgerow connectivity, and farm data on crop types and pest pressure, how do you translate that into a specific recommendation that will work for this particular farm in this particular context?

If the translation step - from data to insight to actionable recommendation - can't be automated as easily as we hoped, it would require constant input from expensive agronomic and ecological expertise. The platform could surface patterns and flag anomalies, but the final mile of "here's what you should do" might need human judgment that doesn't scale. You could hire experts initially - that's what VC funding is for - but if every recommendation requires manual analysis, you've built a consultancy with a software wrapper, not a scalable platform.

And there's a deeper concern: what if even with experts on staff, the data is simply too nuanced to support real decisions? Ecosystems are complex adaptive systems. The same data might mean different things in different contexts. An expert might look at the interlaced picture and still not be confident enough to recommend a specific intervention - not because they lack expertise, but because the system itself resists simple cause-and-effect reasoning. If that's true, the gap isn't just about scaling expertise; it's about whether the actionability we promised is even achievable.

### Antithesis Three: Misaligned Timelines

{% include callout.html content="The timeline for ecological interventions to show measurable results doesn't match corporate decision-making cycles or farmer cash flow needs." %}

Our north star scenarios painted a picture of relatively quick wins: plant wildflowers, see pollinator improvements next season. Release ladybirds, cut pesticide costs by 30% the following year. These timelines may feel reasonable when sketching out the vision - but what if ecological systems simply don't change on timelines compatible with business decision-making?

Building up beneficial insect populations takes time. Soil health improvements from reduced chemical inputs take years to materialise fully. Even when interventions work, demonstrating that they work - with sufficient data to prove causation rather than correlation - requires multiple growing seasons.

Meanwhile, Rajesh is evaluated quarterly on supply chain costs and reliability. Sarah needs to show progress in her annual sustainability report. António is farming on tight margins and can't afford interventions that might pay off in three years when he needs to cover costs this season. If the temporal mismatch between ecological change and business imperatives is as fundamental as it seems, it creates a tension our thesis may have underweighted.

The positive feedback loop we envisioned would be self-reinforcing once started, but what if completing even one full cycle takes too long? Collecting baseline data, implementing interventions, waiting for ecological response, measuring outcomes, and demonstrating ROI could easily take two to three years. If corporates won't keep funding and farmers won't stay engaged through that timeline, the loop never closes.

### Antithesis Four: The Trust Problem

{% include callout.html content="Farmers don't trust biodiversity recommendations from platforms funded by the corporations buying their produce." %}

António's scenario assumed he'd be skeptical but ultimately receptive to his agronomist's recommendations, especially when subsidised by the corporate buyer. But what if farmer skepticism about corporate-funded initiatives runs too deep to overcome?

When a big food company starts funding biodiversity monitoring on your farm and telling you to change your practices, what's the first thing you think? "They're trying to reduce what they pay me." Or "They're going to use this data to drop me as a supplier if my farm doesn't measure up." Or "This is about making their brand look good, not helping me."

The trust dynamics in agricultural supply chains are complicated. Farmers have been burned before by corporate sustainability programs that asked them to make costly changes, collected lots of data, generated nice reports for shareholders, and then moved on when priorities shifted. Why should this platform be different?

Our thesis assumed that demonstrating economic value - António cutting pesticide costs by 30% - would overcome skepticism. But what if the first intervention doesn't work as well as predicted? What if regional weather patterns that year mask the impact? What if the agronomist, working with imperfect regional data through the platform, makes a recommendation that fails? One bad experience could poison the well for future engagement.

The platform sits in a structurally awkward position: funded by corporates, delivering insights through agronomists, impacting farmers. Each handoff introduces trust friction. If that friction is higher than we assumed, it could make farmer adoption impossible regardless of the economic value proposition.

### Antithesis Five: The Agronomist Economics Don't Work

{% include callout.html content="The agronomist tier has no independent funding path - it only works if there's surplus from corporate data collection." %}

Amara's scenario assumed she'd subscribe to the agronomist tier, gain competitive advantage, and build her practice around biodiversity-informed advice. But the economics of this tier were never pressure tested.

Farmers don't have the margins to fund this - they're price-sensitive about agronomic advice and **may** pay for recommendations that directly impact yield or input costs, but "biodiversity insights" sound like a luxury when your margins are razor thin. So funding has to come from somewhere else. The thesis assumed corporate funding would flow down to enable this tier.

But even if we offered the agronomist tier at cost - treating it as a loss leader to build network effects and create a moat - we'd still be spending significant money on the data collection that makes such a tier valuable. High-resolution satellite imagery isn't cheap. Regional eDNA surveys aren't cheap. The data that would make Amara's advice genuinely differentiated has real costs, and those costs need to be funded somehow.

If corporates only fund enough data for their compliance needs (see Antithesis One), there may be no surplus to subsidise an agronomist tier. If agronomists can't pay enough to cover the data costs themselves, and farmers certainly won't, the question of who funds the data collection that makes this tier work remains unclear.

### Antithesis Six: The Integration Problem

{% include callout.html content="The NatureTech companies whose data we'd need to interlace have no incentive to make integration easy - and every incentive to resist it." %}

Creating a holistic picture of biodiversity from different monitoring technologies isn't just technically challenging - it may be structurally difficult to achieve. The companies working to crack eDNA, bioacoustics, remote sensing, and other monitoring approaches are all fighting for a piece of the same small pie. It isn't in their interest to make it easy for a third party like us to build on top of their products.

This is especially true if their own product thesis is that their proprietary technology should be enough to deliver actionable insights. In many ways, our thesis negates theirs: we're saying that no single monitoring technology is sufficient, that you need to interlace multiple data sources to understand complex ecosystems. If they believe that, they're admitting their technology alone isn't the answer. So partnering with us is a risk to their own positioning.

Without their collaboration - open APIs, standardised data formats, willingness to be one layer in a larger stack - building the interlaced picture we envisioned might prove impossible to scale. We'd be fighting not just technical complexity, but commercial resistance from the very companies whose services we rely on for our own model to work.

## Begin with the Antitheses

These antitheses are all things we were in the process of validating when we ran out of time. We never got far enough to definitively disprove any of them. They might all be thesis killers - we won't know until someone pushes forward far enough to find out. **If you're picking up this idea, these are where you should start.**

If the compliance funding antithesis is valid, the funding model can't rely primarily on compliance spending. Corporate sustainability budgets might be real but constrained, optimised for minimum viable compliance rather than maximum biodiversity impact. A viable model might need either much lower costs (can you deliver enough value with 10x cheaper data collection?) or a different primary buyer (governments? conservation organisations? outcome-based financing such as biodiversity credits?).

If the actionability antithesis holds, the problem needs a different solution. Either accept that human expertise is required and build a services business wrapped around the platform, or narrow the problem space dramatically to domains where automation actually works. Trying to be a pure platform play that covers all crops, all geographies, and all intervention types might be too ambitious.

If the timeline antithesis is true, the business model needs to acknowledge it explicitly. If ecological change takes three years to demonstrate, pricing and retention strategy need to account for that. Longer initial contracts, milestone-based payments, or patience capital that most venture investors won't provide. This is something we do see in a related space: carbon project developers, such as [Revalue](https://revalue.earth) where I'm currently Head of Engineering, often structure longer milestone-based payments where funding is released over time as projects progress and demonstrate impact.

If the trust antithesis is valid, trust needs to be designed into the product, not assumed. Maybe the platform can't be both corporate-funded and farmer-serving. Maybe it needs to be positioned as truly independent, funded in ways that don't create conflicts of interest.

If the agronomist tier has no independent funding path, the whole model becomes contingent on corporate surplus. Either find a way to make the agronomist tier self-sustaining, or accept that it only exists when and where corporate funding exceeds compliance needs.

If the integration problem is real, and NatureTech companies actively resist being commoditised into a layer, then the platform either needs to build its own monitoring capabilities (expensive and unfocused) or find a different value proposition that flips the narrative on interlacing third-party data such that it benefits these companies as much as it benefits the platform.

## Where We're At

Every product thesis is a bet on a particular view of the world. Ours was elegant and compelling, yet ultimately proved insufficient for us to build a sustainable company. But insufficient doesn't mean invalid. Validating the thesis remains the core question.

I still believe there's validity to the thesis. Biodiversity is genuinely complex, and no single monitoring technology will ever be enough. The challenge of interlacing came up so many times in our discovery work that I am confident there's something uniquely powerful in the aggregation - in the holistic picture that emerges when diverse data sources come together. Whoever builds the connective tissue between those who can fund the data collection, those who can perform it, and those who can act on it will unlock something significant. But the antitheses are equally compelling, and each one will require focused discovery and experimentation to learn from and evolve our product thesis.

The product thesis alone wasn't enough. Now we have an antithesis. And the synthesis? That's still being written, and I hope to continue taking part in writing it - stay tuned.
