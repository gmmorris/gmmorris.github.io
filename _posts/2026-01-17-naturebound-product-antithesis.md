---
layout: post
title: "NatureBound: Testing the Thesis"
date: 2026-01-17 12:00:00
categories: [NatureTech]
tags: [product-management, biodiversity, agriculture, startups, climate]
icon: seedling
description: "Examining where our product thesis met reality - what we got wrong about building observability for nature, and what that teaches us about the space."
image-desc: "Birds in Platinotype"
image: "/images/banners/birds-in-platinotype-left.png"
image-desc-link: "https://www.flickr.com/photos/biodivlibrary/albums/72157719475318174/with/50615322236/"
---

In [Part 1: A Product Thesis]({% post_url 2026-01-10-naturebound-product-thesis %}), I laid out what we believed when we built NatureBound.
The thesis was straight forward: corporations need biodiversity data for reporting, they'll fund data collection as part of compliance, this data can generate actionable insights for farmers and agronomists, these insights create measurable improvements, and improvements justify continued investment in a positive feedback loop.

The mechanism was elegant. The corporate sustainability officer gets compliance-ready reports. The food buyer de-risks their supply chain. The agronomist gains capabilities that let them compete with larger consultancies. The farmer cuts costs and improves yields. Everyone wins, and the ecosystem benefits from reduced chemical loading.

It was compelling enough that we spent almost two years building toward it. Compelling enough that investors, advisors, and early customers saw the logic. But compelling isn't the same as valid.

## What is a Product Antithesis?

A product antithesis is the mirror image of your thesis - it's where you actively try to prove yourself wrong. It's about testing your hypotheses as rigorously as possible, looking hard in the mirror to find the things that will kill your idea, and evolving your understanding based on what you learn. The goal isn't to defend your vision; it's to disprove your thesis as early as possible, before you've invested years building something nobody wants.

Every compelling vision has blind spots. Every elegant thesis has edge cases that don't fit. The antithesis isn't about admitting defeat, but rather about surfacing the weakest links in your thinking while you can still change course. It's the discipline of seeking out the uncomfortable truths that invalidate your assumptions, rather than waiting for reality to do it for you.

When a startup fails, there's a natural tendency to focus on execution: we didn't move fast enough, we ran out of runway, we hired the wrong people, we couldn't raise the next round. These are all real constraints, and they all matter. But they're not the most interesting questions to ask when examining what happened.

The more valuable question is: **Was the underlying hypothesis valid?** Not "Could we have executed better?" but "Were we solving the right problem in the right way for the right people?" This matters because if the thesis was fundamentally sound, someone else - maybe even me, in a different context - could pick it up and succeed where we didn't. But if the thesis itself was flawed, then no amount of execution excellence would have saved us.

So let me be clear about what this post is not: this is not a post-mortem about why NatureBound failed as a company. I'm not going to dissect our fundraising strategy, our go-to-market execution, or our team dynamics. Those are important questions, but they're not what I'm exploring here. This is about the product thesis itself. About potential invalidations we hadn't disproved by the time the company folded. About ways the thesis could be fundamentally wrong that we would need to take seriously if we ever picked this idea up again.

These aren't conclusions about what we got wrong - the company shut down, but that doesn't definitively prove which assumptions were invalid. What follows are the hardest questions, the ones that could kill the idea if they turn out to be true. Some we saw signals for. Others remain open questions. But all of them deserve rigorous examination, because if I'm only willing to defend the thesis, I haven't learned anything.

## Antithesis One: The Compliance Funding Model

{% include callout.html content="Corporate compliance requirements don't generate enough funding to build the platform needed to deliver actionable insights." %}

Here's what we believed: corporations facing TNFD and CSRD reporting requirements would need farm-level biodiversity data, and they'd pay for platforms that could collect, integrate, and report on that data. This spending would fund the data collection infrastructure that, as a byproduct, could generate insights for farmers and agronomists.

But what if compliance doesn't actually require the kind of detailed, farm-specific data we envisioned? What if companies can satisfy their reporting obligations with much cheaper, less precise approaches - consultant-written estimates, regional proxies, or industry averages that auditors will accept? If the compliance bar is lower than we assumed, then the funding we expected for detailed data collection evaporates.

Even more fundamentally, what if corporate sustainability teams simply don't have the budget authority we assumed? Sarah might desperately want real biodiversity data, but if her CFO views sustainability reporting as a compliance tax to be minimised rather than a strategic investment, she's not buying a platform subscription - she's hiring the cheapest consultant who can tick the regulatory boxes.

In customer conversations, we heard signals that suggested this might be the case. Sustainability officers expressed genuine interest, but when discussions turned to budget, the numbers they mentioned were often an order of magnitude smaller than what we'd need to build the platform we envisioned. This could mean the gap between "this would be valuable" and "I can pay for this" is wider than our thesis assumes - or it could mean we were talking to the wrong people, or that the market needs more time to mature. We don't know which.

## Antithesis Two: The Actionability Gap

{% include callout.html content="Converting fragmented biodiversity data into actionable recommendations requires too much context-specific expertise to automate or scale." %}

Our thesis assumed that once we interlaced multiple data sources - eDNA, remote sensing, farm management data, environmental context - we could generate actionable insights relatively systematically. The aphid and ladybird example from Part 1 works beautifully because it's a well-understood relationship with clear interventions.

But what if most ecological relationships aren't like aphids and ladybirds? What if they're too complex, too context-dependent, and require too much expertise to interpret systematically? When you're looking at eDNA results showing the presence of certain bat species, bioacoustic data on their activity patterns, remote sensing of hedgerow connectivity, and farm data on crop types and pest pressure, how do you translate that into a specific recommendation that will work for this particular farm in this particular context?

If the translation step - from data to insight to actionable recommendation - can't be automated as easily as we hoped, it would require constant input from expensive agronomic and ecological expertise. The platform could surface patterns and flag anomalies, but the final mile of "here's what you should do" might need human judgment that doesn't scale.

This would create a chicken-and-egg problem: to deliver value, you'd need expert agronomists and ecologists reviewing data and crafting recommendations. But to afford those experts, you'd need revenue from customers who would only pay once you'd proven you could deliver actionable insights. If this gap between automated insights and expert-crafted recommendations is as large as it might be, it could make the platform model unviable.

## Antithesis Three: Misaligned Timelines

{% include callout.html content="The timeline for ecological interventions to show measurable results doesn't match corporate decision-making cycles or farmer cash flow needs." %}

Our north star scenarios painted a picture of relatively quick wins: plant wildflowers, see pollinator improvements next season. Release ladybirds, cut pesticide costs by 30% the following year. These timelines felt reasonable when we were sketching out the vision.

But what if ecological systems simply don't change on timelines compatible with business decision-making? Building up beneficial insect populations takes time. Soil health improvements from reduced chemical inputs take years to materialise fully. Even when interventions work, demonstrating that they work - with sufficient data to prove causation rather than correlation - requires multiple growing seasons.

Meanwhile, Rajesh is evaluated quarterly on supply chain costs and reliability. Sarah needs to show progress in her annual sustainability report. António is farming on tight margins and can't afford interventions that might pay off in three years when he needs to cover costs this season. If the temporal mismatch between ecological change and business imperatives is as fundamental as it seems, it creates a tension our thesis may have underweighted.

The positive feedback loop we envisioned would be self-reinforcing once started, but what if completing even one full cycle takes too long? Collecting baseline data, implementing interventions, waiting for ecological response, measuring outcomes, and demonstrating ROI could easily take two to three years. If corporates won't keep funding and farmers won't stay engaged through that timeline, the loop never closes.

## Antithesis Four: The Trust Problem

{% include callout.html content="Farmers don't trust biodiversity recommendations from platforms funded by the corporations buying their produce." %}

António's scenario assumed he'd be skeptical but ultimately receptive to his agronomist's recommendations, especially when subsidised by the corporate buyer. But what if farmer skepticism about corporate-funded initiatives runs too deep to overcome?

When a big food company starts funding biodiversity monitoring on your farm and telling you to change your practices, what's the first thing you think? "They're trying to reduce what they pay me." Or "They're going to use this data to drop me as a supplier if my farm doesn't measure up." Or "This is about making their brand look good, not helping me."

The trust dynamics in agricultural supply chains are complicated. Farmers have been burned before by corporate sustainability programs that asked them to make costly changes, collected lots of data, generated nice reports for shareholders, and then moved on when priorities shifted. Why should this platform be different?

Our thesis assumed that demonstrating economic value - António cutting pesticide costs by 30% - would overcome skepticism. But what if the first intervention doesn't work as well as predicted? What if regional weather patterns that year mask the impact? What if the agronomist, working with imperfect regional data through the platform, makes a recommendation that fails? One bad experience could poison the well for future engagement.

The platform sits in a structurally awkward position: funded by corporates, delivering insights through agronomists, impacting farmers. Each handoff introduces trust friction. If that friction is higher than we assumed, it could make farmer adoption impossible regardless of the economic value proposition.

## Antithesis Five: The Agronomist Economics Don't Work

{% include callout.html content="Independent agronomists can't afford platform subscriptions on their existing business model, and farmers won't pay them more for biodiversity advice." %}

Amara's scenario assumed she'd subscribe to the agronomist tier, gain competitive advantage, and either retain more clients or win new business at higher rates. But what if farmers simply don't value biodiversity expertise enough to pay for it?

Most farmers, especially those on thin margins, are price-sensitive about agronomic advice. They'll pay for recommendations that directly impact yield or input costs, but "biodiversity insights" might sound like a luxury when you're worried about making payroll. If Amara tries to charge more for her services because she now has platform access, her farmer clients might just hire someone cheaper who sticks to traditional agronomic advice.

Even if some farmers see the value, the economics could be challenging. If Amara pays, say, £200/month for platform access but only gains one or two additional clients because of it, the ROI doesn't pencil out. She'd need either a much larger client base, much higher prices, or much lower subscription costs for the unit economics to work.

Our thesis assumed agronomists would pay because the platform made them more competitive. But competitive advantage only matters if you can monetise it. If the willingness-to-pay in the agricultural advisory market doesn't support premium pricing for biodiversity expertise - at least not yet - the agronomist tier might not be viable.

## Antithesis Six: Personas Might Not Be Distinct Users

{% include callout.html content="The four personas we identified might not represent distinct buying centers with independent budgets and decision-making authority." %}

Our multi-sided platform model assumed Sarah, Rajesh, Amara, and António were distinct users with different needs, different budgets, and different paths to value. But what if in practice, they're more entangled than this model suggests?

Sarah and Rajesh often work for the same company, reporting to the same executive leadership. Their budgets come from the same pool. If Rajesh funds farmer interventions as part of sustainable sourcing, does Sarah still need to buy biodiversity reporting separately, or can she just use the data Rajesh is already paying for? The platform needs both of them to justify its pricing, but from the company's perspective, they might see it as paying twice for the same thing.

Similarly, Amara and António's relationship isn't strictly buyer-seller. In many cases, the agronomist's fees are wrapped into the farmer's operating costs, or the agronomist is employed by a cooperative that serves multiple farmers. If Amara subscribes to the platform, does António pay nothing? If so, how much value does António-as-a-persona add to our business model? If António does pay, are we really asking one operation to fund two subscriptions for what looks like the same service?

The elegant separation of personas in our pitch deck may have obscured the messy reality of how agricultural businesses actually purchase and use technology. Multi-sided platforms work when each side has independent reasons to pay and independent budgets to pay with. If the actual buying behavior is more consolidated than we assumed, the multi-sided model might not capture enough value to work.

## What We Still Believe

It would be intellectually dishonest to only question the thesis. Despite these potential invalidations, some elements still feel sound.

The problem is real and getting worse. Data fragmentation is a genuine barrier to progress. The "so what?" gap - collecting data but not knowing how to act on it - remains the critical challenge in the NatureTech space. Corporate pressure for biodiversity reporting is increasing, not decreasing, and companies genuinely struggle to measure and report on nature-related dependencies and impacts with any rigour.

The platform approach still makes sense for this space. The economics of biodiversity monitoring - expensive data collection that could serve multiple use cases - suggest that aggregation and sharing create value. Someone will eventually solve the interlacing problem and build the connective tissue between data collectors, insight generators, and decision-makers.

The vision of "observability for nature" - empowering people to ask new questions of complex ecosystems rather than just monitoring predetermined metrics - remains compelling. The parallel to software observability is apt: both domains deal with complex adaptive systems, emergent behaviour, and the need for iterative exploration rather than static dashboards.

And the alignment of incentives, while perhaps harder than we assumed, isn't necessarily impossible. Corporate buyers do care about supply chain resilience. Farmers do want to reduce input costs. Agronomists do want competitive advantages. The question isn't whether these interests can be aligned, but whether a venture-scale platform is the right vehicle to do it, or whether the alignment happens through different mechanisms we haven't envisioned yet.

## Synthesis: What Would It Take?

If someone - perhaps a company like NatureMetrics, perhaps a future version of myself - wanted to build on these ideas, what would need to be true or different?

If the compliance funding antithesis is valid, the funding model can't rely primarily on compliance spending. Corporate sustainability budgets might be real but constrained, optimised for minimum viable compliance rather than maximum biodiversity impact. A viable model might need either much lower costs (can you deliver enough value with 10x cheaper data collection?) or a different primary buyer (governments? conservation organisations? outcome-based financing?).

If the actionability antithesis holds, the problem needs a different solution. Either accept that human expertise is required and build a services business wrapped around the platform, or narrow the problem space dramatically to domains where automation actually works. Trying to be a pure platform play that covers all crops, all geographies, and all intervention types might be too ambitious.

If the timeline antithesis is true, the business model needs to acknowledge it explicitly. If ecological change takes three years to demonstrate, pricing and retention strategy need to account for that. Longer initial contracts, milestone-based payments, or patience capital that most venture investors won't provide.

If the trust antithesis is valid, trust needs to be designed into the product, not assumed. Maybe the platform can't be both corporate-funded and farmer-serving. Maybe it needs to be positioned as truly independent, funded in ways that don't create conflicts of interest. Or maybe it needs to be owned and controlled by the farmers and agronomists it serves, not by the corporates paying for it.

And if the persona economics don't work as assumed, brutal honesty is required: which of these personas can actually pay? How much? How often? If the answer is "not enough to build a venture-scale business," that's important to know up front, because it changes what kind of company you're building.

## Conclusion

Every product thesis is a bet on a particular view of the world. Ours was elegant, compelling, and - we now know - insufficient to build a sustainable company. But insufficient doesn't mean invalid. We believed in observability for nature. We believed in aligning corporate compliance with ecological improvement. We believed in empowering agronomists and farmers with data-driven insights. The question isn't whether these beliefs were wrong, but whether the mechanism we envisioned could actually realise them.

I don't know which of these antitheses are true. The company shut down, but that doesn't definitively prove which assumptions were flawed. Maybe all of them. Maybe none of them, and we just needed more time or better execution. Maybe some combination that made the whole thing unviable even though individual pieces were sound.

What I do know is that the problem is still there. The opportunity is still there. And someone, somewhere, will figure out which parts of the thesis hold and which parts need rethinking. They'll find the right synthesis that makes it work.

Maybe it's NatureMetrics. Maybe it's another company that doesn't exist yet. Maybe it's a future version of something we tried to build. But the need for observability in nature - for turning invisible ecological relationships into visible, actionable insights - isn't going away.

The thesis alone wasn't enough. Now we have an antithesis. The synthesis? That's still being written, and I'm genuinely curious to see what form it takes.

---

_Have thoughts on this analysis? Found gaps in my reasoning? I'd love to hear them. [Reach out on LinkedIn](https://www.linkedin.com/in/gidi-morris/) or drop me a note._
