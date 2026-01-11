---
layout: post
title: "NatureBound: A Product Thesis"
date: 2026-01-10 12:00:00
categories: [NatureTech]
tags: [product-management, biodiversity, agriculture, startups, climate]
icon: seedling
description: "Reflecting on the product thesis behind NatureBound, a company I co-founded to address fragmented biodiversity data in agriculture - and why I still believe in the idea."
image-desc: "Birds in Platinotype"
image: "/images/banners/birds-in-platinotype-right.png"
image-desc-link: "https://www.flickr.com/photos/biodivlibrary/albums/72157719475318174/with/50615322236/"
---

I haven't written about this yet, and frankly, I wasn't sure when the right moment would come. But I've been thinking a lot about product theses and antitheses, and it felt like a good lens through which to process what we tried to build - and why it mattered, even though we didn't succeed.

In 2022, I left big tech to focus on climate change and nature. It was a deliberate shift, one I'd been contemplating for years as I watched the compounding effects of ecosystem collapse play out in real-time. I was suffering from pretty bad climate doomism at the time. It weighed on me that while I sat there, optimising ad delivery systems and improving observability tooling, it felt like the planet was dying, and like no one was doing anything about it. That wasn't true, of course - plenty of people were working on these problems - but that was my perspective from inside the tech bubble. The decision crystallised when I realised: what's the point of career ambition if there's no planet left to sustain it?

## NatureBound and the People Behind It

I co-founded NatureBound with two remarkable people who brought perspectives I could never have developed on my own.

[**Marianna**](https://www.linkedin.com/in/marianna-herold-9a4518/) is an entrepreneur who spent years in the food space, navigating the messy intersection of sustainability, supply chains, and consumer behavior. She understood the business realities of food production in ways I never could from my engineering background - the razor-thin margins, the complexity of global supply chains, the challenge of making "doing the right thing" economically viable.

[**Iqbal**](https://www.linkedin.com/in/iqbal-bhalla-53b74a116/) was a young, energized Post-Doc Ecologist with a deep passion for biodiversity monitoring. His focus on bats and their critical role in agriculture opened my eyes to the invisible interdependencies that keep our food systems functioning. He's now teaching at the University of Saskatchewan, training the next generation of ecologists who'll inherit the challenge of monitoring and protecting what's left.

The three of us came to the problem from different angles, but we shared a common conviction: agriculture sits at the nexus of the biodiversity crisis, and if we could help make farming more compatible with nature, we could create meaningful change at scale.

We each had personal connections to this space. I grew up in an agricultural area - my first job was collecting eggs in the shadow of what was then the biggest chicken coop in the Middle East. Iqbal's research into bats revealed how these often-overlooked creatures provide billions of dollars worth of pest control services to farmers worldwide. And Marianna, whether she fully admits it or not, is a foodie whose career has orbited around making food systems more sustainable and equitable.

## We Shut Down in 2024

Enough time has passed since NatureBound folded in 2024 that I feel ready to document what we tried to build. We ran the experiment, we learned an enormous amount, and ultimately we couldn't make it work within the constraints we faced. I still believe in the idea - deeply - and I want to capture what we were building, both for my own clarity and in the hope that someone (maybe even me, in a different context) will pick up this thread in the future.

Startups fail for a thousand reasons, most of them mundane. Market timing, funding dynamics, team capacity and ability, regulatory headwinds. We hit some combination of all of these. But the underlying problem we identified? That hasn't gone anywhere. If anything, it's gotten more acute.

So this is a product thesis for a company that no longer exists, but for a problem that very much does.

## Why I'm Writing This Now

There's another reason I'm documenting this now, and it's worth being transparent about: I'm joining NatureMetrics, a company I've always thought of as "the eDNA company." I've watched them evolve to offer a much more holistic offering, and they seem to have come to the same conclusions we had at NatureBound. I wanted to get all of this context down on paper _before_ I begin my new role, for two specific reasons.

First, I don't know anything proprietary about NatureMetrics yet. Once I'm inside, these thoughts would become impossible to publish - there would always be the question of whether I'm drawing on internal knowledge or strategy. Writing this now preserves the independence of these observations.

Second, and perhaps more importantly, I'm sure I'm wrong about some of these things. The ideas in this post represent my current understanding, shaped by the NatureBound experience and dozens of customer conversations, but they're still just hypotheses. It will be fascinating to look back in a year or two and see how much I got wrong, and how much companies like NatureMetrics - who've been in this space far longer than I have - got right. This is my stake in the ground, my "before" snapshot.

So take everything that follows with appropriate skepticism. This is what I believed the product opportunity looked like based on what we learned. Reality, as always, is more nuanced.

## The Problem: Biodiversity Loss as an Agricultural Crisis

The loss of biodiversity represents an existential threat to human civilization, and agriculture is both a primary driver of that loss and one of its most vulnerable victims. Modern farming has created a negative feedback loop: intensive practices degrade ecosystems, which reduces the natural services those ecosystems provide to farms (pollination, pest control, soil health), which drives farmers to rely even more heavily on costly chemical inputs, which further degrades ecosystems.

Breaking this cycle requires visibility into what's actually happening at the ecosystem level - and that's where things get complicated.

During our customer discovery process, we kept hearing the same challenge from different angles: **data fragmentation**. The nature tech space is still in its early stages, and the people building these technologies come from wildly different backgrounds - biochemists, geospatial analysts, climatologists, ecologists, soil scientists. Each discipline has its own data formats, collection methodologies, analysis frameworks, and vocabulary.

For a farmer or agronomist trying to understand the biodiversity on their land, this fragmentation is paralyzing. You might have:
- Remote sensing data showing land cover changes
- eDNA surveys revealing which species are present in soil or water samples
- Manual observation records from field visits
- Weather and climate data
- Soil chemistry analysis
- Pesticide and fertilizer application logs
- Crop yield data

Each of these data points is expensive to collect. More importantly, **none of them tells you what you actually need to know in isolation**. The insights that matter - _Is this population of natural predators sufficient to control pests? Are we seeing signs of ecosystem degradation that will impact yields in three years? Which interventions would have the highest ROI for both nature and farm economics?_ - these require interlacing multiple data sources in sophisticated ways.

Agronomists and ecologists who want to provide effective guidance to farmers face an impossible choice: either fork out enormous amounts of money to purchase, produce, and integrate all these data sources themselves, or give incomplete advice based on partial information. For most, the former is economically unsustainable. Their budgets can't support it. So they're stuck making recommendations without the full picture, unable to help farmers optimize for both economic and ecological outcomes.

## Product Thesis

Here's how we framed the opportunity:

**Corporations with agricultural supply chains face increasing pressure to report on their nature-related dependencies and impacts, while simultaneously worrying about the long-term sustainability of their supply chains. They need visibility into biodiversity health within their sourcing regions, but lack the tools to collect, integrate, and act on that information efficiently.**

**We can create a positive feedback loop that aligns corporate reporting requirements with on-the-ground ecological improvement.**

The mechanism works like this:

1. **Corporates fund data collection** because they need it for mandatory nature-related reporting (TNFD, CSRD, etc.) and supply chain risk assessment.

2. **Our platform makes it easy to determine which data to collect and where**, using an intelligent recommendation engine that accounts for crop types, regional ecology, existing data availability, and reporting requirements.

3. **We interlace diverse data sources** - remote sensing, eDNA, field observations, farm management data - into a unified analytical layer that provides a holistic view of biodiversity health.

4. **We map this to standardised impact and dependency metrics** that corporates can use for their reporting obligations, showing both current state and trends over time.

5. **We generate actionable insights for farmers and agronomists** operating within those supply chains, enabling them to make decisions that improve ecological outcomes while also reducing input costs or improving yields.

6. **Demonstrable improvements flow back into the next reporting cycle**, creating a virtuous loop where corporate investment in data collection leads to better on-the-ground practices, which leads to better metrics, which justifies continued investment.

The key insight was that **the person who needs the data (the corporate sustainability team) and the person who can act on it (the farmer) are not the same**, but their interests can be aligned if you build the right connective tissue.

## User Personas

Meet the people we were trying to help:

### Sarah the Spreadsheet Wrangler (Corporate Sustainability Officer)

Sarah works at a major food brand, managing nature-related disclosures for their agricultural supply chains. She's constantly fighting for budget, trying to prove to the CFO that sustainability isn't just a "nice-to-have," and drowning in consultant reports that cost a fortune and tell her almost nothing actionable. When regulators ask for TNFD compliance, she needs real data, not hand-wavy estimates. She's smart, overworked, and acutely aware that her job exists in that awkward space between regulatory necessity and executive skepticism.

**How she'd use NatureBound:**

It's Q4, and Sarah needs to submit her company's first TNFD report in three months. She logs into the platform, selects the five sourcing regions her company depends on (tomatoes in Southern Europe, coffee in Colombia, cocoa in West Africa). The system shows her existing data coverage - mostly sparse - and recommends specific data collection strategies for each region based on crop type and regulatory requirements. She approves the plan, the corporate food buyer coordinates with suppliers, and eDNA surveys plus remote sensing get scheduled. Two months later, she downloads a compliance-ready report showing biodiversity dependencies and impacts, complete with audit trails and year-over-year trends. She presents it to the board. The CFO asks, "Will this actually reduce our supply chain risk?" For the first time, she can say yes and point to specific interventions already underway.

---

### Rajesh the Risk-Mitigator (Corporate Food Buyer)

Rajesh sources raw materials from hundreds of farms across multiple continents. He's seen supply chain disruptions from droughts, floods, and degraded soils that no longer produce viable yields. His bonus depends on keeping costs stable and ensuring reliable supply, but he's also under pressure to hit sustainability targets that his company announced to shareholders. He doesn't have time to become an ecologist - he just needs to know which sourcing regions are at risk and what he can do about it before it hits his quarterly numbers.

**How he'd use NatureBound:**

Rajesh gets an alert from the platform: one of his tomato-sourcing regions in Southern Europe shows declining biodiversity metrics and increasing pesticide dependency. The system flags this as a medium-term supply risk - if current trends continue, yields will likely drop 15-20% within three years. It recommends a pilot program with 10 farms to implement integrated pest management practices, funded as part of the company's sustainable sourcing budget. The cost: €50K. The projected ROI: reduced supply risk, improved sustainability metrics for reporting, and potential premium pricing for regeneratively-grown tomatoes. Rajesh greenlights it. Six months later, those 10 farms show measurable improvements. He expands the program to 50 more farms and uses the early results in his pitch to retain the brand's sustainable sourcing commitments.

---

### António the Farmer (Multi-Generational Farmer on Thin Margins)

António inherited his 200-hectare farm from his father, who inherited it from his father. He cares deeply about the land - it's his legacy - but he's also pragmatic. Pesticide costs have tripled in the past decade. Fertilizer prices are volatile. Drought years are becoming more frequent. He's heard about "regenerative agriculture" and "biodiversity," but he doesn't have €10K to spend on consultants telling him to plant wildflowers. He'll listen if someone can show him how to cut costs or get better prices, but he's been burned before by tech companies selling silver bullets that don't work in real farming conditions.

**How he'd use NatureBound (or rather, how it would help him indirectly):**

António doesn't pay for NatureBound - the corporate buyer does. But his agronomist shows up one day with something new: a detailed analysis of his fields showing that he has low predator-to-pest ratios. The recommendation is specific: plant dill and fennel along his field margins, and consider releasing ladybugs next season. The cost is minimal, and the corporate buyer is subsidizing it as part of a sustainable sourcing program. António is skeptical but figures he has nothing to lose. The next season, his aphid problems are noticeably better, and he cuts his pesticide costs by 30%. The agronomist shows him the biodiversity monitoring data proving the improvement. António is still skeptical of fancy tech, but he trusts results he can see in his bank account. He signs up for the next phase of the program.

---

### Amara the Ecosystem Whisperer (The Agronomist Who Wants to Be Cutting-Edge)

Amara is an independent agronomist advising 30 farms across her region. She's passionate about her work and prides herself on staying ahead of trends. She knows integrated pest management is the future, and her farmer clients are starting to ask about biodiversity and regenerative practices. But she doesn't have the tools or expertise to offer sophisticated ecological advice - she can recommend crop rotations and fertilizer schedules, but she can't interpret eDNA results or model predator-prey dynamics. Her competitors at larger consultancies are starting to offer these services, and she's worried about losing clients.

**How she'd use NatureBound:**

Amara subscribes to the platform's agronomist tier. When she visits António's farm, she pulls up his biodiversity profile - eDNA results, remote sensing analysis, integrated with his farming data. The system highlights the aphid-ladybug imbalance and suggests the intervention. Amara knows crop rotations and soil health - that's her expertise - but now she can connect those insights to ecosystem dynamics she couldn't measure before. She presents this to António with confidence: her agronomic judgment backed by biodiversity data she couldn't have generated herself. She rolls out similar insights across her client base, positioning herself as the "AI-enabled agronomist" offering cutting-edge advice that her competitors can't match. Her client retention goes up. She starts winning new business from farmers who've heard she combines deep agronomic knowledge with ecosystem-level insights. She becomes known in her region as the agronomist who bridges traditional practice with biodiversity science.

---

## How These Personas Connect: The Aphid and Ladybug Story

Let me give you a concrete example of how our platform would create value across all these personas simultaneously.

Imagine a corporate food buyer sources tomatoes from farms in Southern Europe. Their sustainability officer needs to report on biodiversity dependencies and impacts. Meanwhile, the farmers are spending significant amounts on pesticides to control aphids, which are decimating their crops.

**The traditional approach:** The corporate hires a consultant to do a one-time biodiversity assessment. The report notes that there's a "moderate diversity of beneficial insects" but doesn't connect this to anything actionable. The farmers keep spraying pesticides. The sustainability report checks a box. Nothing changes.

**The NatureBound approach:**

1. Our platform integrates with the farmers' existing data - crop types, planting locations, pesticide application logs, costs.

2. We recommend a targeted data collection strategy: an eDNA survey of the fields and surrounding areas, combined with remote sensing analysis of landscape features (hedgerows, flower margins, etc.).

3. The corporate pays for this data collection as part of their biodiversity monitoring program.

4. Our platform analyses the results and identifies a critical insight: **there's a low relative abundance of predators to pests**. Specifically, the fields lack sufficient populations of aphid predators like ladybugs (ladybirds).

5. We generate specific recommendations:
   - **For the agronomist:** Plant yarrow, dill, and fennel along field margins to attract and support ladybug populations. Consider purchasing and releasing ladybugs as a short-term intervention while natural populations establish.
   - **For the farmer:** This intervention will reduce reliance on aphid-specific pesticides, cutting input costs by an estimated X euros per hectare while maintaining or improving yields. Timeline to impact: 6-12 months.
   - **For the corporate:** This represents a shift toward Integrated Pest Management (IPM) practices, which can be reported as progress toward regenerative agriculture commitments. Projected reduction in chemical dependency: Y%.

6. The farmer implements the recommendations (funded or incentivized by the corporate as part of their sustainable sourcing program).

7. Next season, follow-up monitoring shows:
   - Ladybug populations have increased
   - Aphid damage is controlled naturally
   - Pesticide costs have decreased
   - The biodiversity metrics in the corporate's report show measurable improvement

This is the positive feedback loop in action. The corporate gets better metrics and demonstrable progress. The farmer reduces costs and improves soil health. The agronomist provides differentiated, data-driven advice. And the ecosystem benefits from reduced chemical loading.

---

## Why This Matters

The example above - aphids and ladybugs - is straightforward because it's a well-understood relationship. A single ladybug can eat 50+ aphids per day. Their larvae are even more voracious. This is textbook biological pest control, and farmers have known about it for generations.

But most ecological relationships are far more complex and context-dependent. The role of bats in controlling crop pests varies by region, crop type, surrounding landscape, and even time of year. The interaction between soil microbiome health and plant resilience to drought involves thousands of species and chemical pathways. The impact of hedgerow placement on pollinator abundance depends on flower timing, connectivity to other habitats, and pesticide drift patterns.

**These insights require deep familiarity with multiple data sources and the ability to collect them cost-effectively.** No individual agronomist can be expected to master soil biochemistry, geospatial analysis, eDNA interpretation, and crop science. But a platform that interlaces these data sources and applies specialised models can surface these insights at scale.

## Turning Users Into Superheroes

This was the part that excited me most: we weren't just building a data platform, we were building a capability multiplier that would turn our users into heroes in their domains.

Imagine Amara walking into a farmer's field and, within minutes, connecting her deep agronomic expertise to ecosystem-level data that would normally require a team of specialists to collect and analyse. She'd become the agronomist that farmers call first, the one who "just gets it" in ways her competitors can't match. Her reputation would spread - not because the platform replaced her expertise, but because it amplified what she already knew, letting her see patterns and connections that were always there but previously invisible.

Or Sarah presenting to her board with a story that actually lands: "Last year, we invested €500K in biodiversity monitoring across our tomato supply chain. We identified three high-risk regions. We intervened with targeted programs. This year, those regions show 25% improvement in ecosystem health metrics, pesticide use is down 18%, and we've reduced our supply chain risk by a quantifiable margin. Here's the data, here's the trajectory, here are the farmers who can testify to the results." The CFO leans back, impressed. Sarah just became the sustainability officer who delivers business outcomes, not just compliance paperwork.

Rajesh stops being the buyer who reacts to supply chain crises and becomes the strategist who prevents them. He spots the warning signs two years before his competitors do. He invests early in farmer support programs that look like altruism but are actually brilliant risk mitigation. His CEO presents him as an example of "how we think long-term about supply chain resilience" in the next earnings call.

Even António - skeptical, pragmatic António - becomes the farmer who "does biodiversity right." He starts getting inquiries from premium brands willing to pay 15% more for tomatoes grown with demonstrable regenerative practices. He's invited to speak at agricultural conferences. His kids, who weren't sure they wanted to take over the farm, start seeing it as a forward-thinking operation worth inheriting.

The platform wasn't just about data integration. It was about giving already-capable people superpowers in their daily work - letting the skilled agronomist punch above their weight, helping the strategic CSO deliver measurable impact, enabling the savvy buyer to act on foresight rather than hindsight, and making the pragmatic farmer prosperous. It was about creating a feedback loop where doing the right thing for nature also made you better at your job, more respected by your peers, and more successful in your career.

That was the vision: make the invisible visible, make the complex actionable, and empower capable people to become the heroes their ecosystems desperately need.

---

_More to come in Part 2, where I'll explore the product antitheses - the reasons this thesis might be wrong, and what we learned about its validity through our attempts to build it._
