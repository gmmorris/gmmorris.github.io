---
layout: post
title: "NatureBound: A Product Thesis for Bridging Biodiversity Data and Agricultural Practice"
date: 2026-01-10 12:00:00
categories: [NatureTech]
tags: [product-management, biodiversity, agriculture, startups, climate]
icon: seedling
description: "Reflecting on the product thesis behind NatureBound, a company I co-founded to address fragmented biodiversity data in agriculture - and why I still believe in the idea."
---

I haven't written about this yet, and frankly, I wasn't sure when the right moment would come. But I've been reading Drew Hoskins' _The Product-Minded Engineer_, and his framework for thinking about product thesis and antithesis has given me a lens through which to process what we tried to build - and why it mattered, even though we didn't succeed.

In 2022, I left big tech to focus on climate change and nature. It was a deliberate shift, one I'd been contemplating for years as I watched the compounding effects of ecosystem collapse play out in real-time data and increasingly desperate reports from the scientific community. The decision crystallized when I realized I couldn't keep building tools for better collaboration and productivity while ignoring the existential question: _what are we collaborating toward, and will we have a planet capable of sustaining it?_

## NatureBound and the People Behind It

I co-founded NatureBound with two remarkable people who brought perspectives I could never have developed on my own.

[**Marianna**](https://www.linkedin.com/in/marianna-herold-9a4518/) is an entrepreneur who spent years in the food space, navigating the messy intersection of sustainability, supply chains, and consumer behavior. She understood the business realities of food production in ways I never could from my engineering background - the razor-thin margins, the complexity of global supply chains, the challenge of making "doing the right thing" economically viable.

[**Iqbal**](https://www.linkedin.com/in/iqbal-bhalla-53b74a116/) was a young, energized Post-Doc Ecologist with a deep passion for biodiversity monitoring. His focus on bats and their critical role in agriculture opened my eyes to the invisible interdependencies that keep our food systems functioning. He's now teaching at the University of Saskatchewan, training the next generation of ecologists who'll inherit the challenge of monitoring and protecting what's left.

The three of us came to the problem from different angles, but we shared a common conviction: agriculture sits at the nexus of the biodiversity crisis, and if we could help make farming more compatible with nature, we could create meaningful change at scale.

We each had personal connections to this space. I grew up in an agricultural area - my first job was collecting eggs in the shadow of what was then the biggest chicken coop in the Middle East. Iqbal's research into bats revealed how these often-overlooked creatures provide billions of dollars worth of pest control services to farmers worldwide. And Marianna, whether she fully admits it or not, is a foodie whose career has orbited around making food systems more sustainable and equitable.

## We Shut Down in 2024

I'm writing this now because NatureBound folded in 2024. We ran the experiment, we learned an enormous amount, and ultimately we couldn't make it work within the constraints we faced. I still believe in the idea - deeply - and I want to document what we were building, both for my own clarity and in the hope that someone (maybe even me, in a different context) will pick up this thread in the future.

Startups fail for a thousand reasons, most of them mundane. Market timing, funding dynamics, team capacity, regulatory headwinds. We hit some combination of all of these. But the underlying problem we identified? That hasn't gone anywhere. If anything, it's gotten more acute.

So this is a product thesis for a company that no longer exists, but for a problem that very much does.

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

4. **We map this to standardized impact and dependency metrics** that corporates can use for their reporting obligations, showing both current state and trends over time.

5. **We generate actionable insights for farmers and agronomists** operating within those supply chains, enabling them to make decisions that improve ecological outcomes while also reducing input costs or improving yields.

6. **Demonstrable improvements flow back into the next reporting cycle**, creating a virtuous loop where corporate investment in data collection leads to better on-the-ground practices, which leads to better metrics, which justifies continued investment.

The key insight was that **the person who needs the data (the corporate sustainability team) and the person who can act on it (the farmer) are not the same**, but their interests can be aligned if you build the right connective tissue.

## User Personas

Let me break down the key personas we identified, using the lens of a product brief:

### Persona 1: Corporate Sustainability Officer

**Context:** Employed by a food brand or retailer with complex agricultural supply chains spanning multiple geographies. Responsible for nature-related disclosures under emerging regulatory frameworks (TNFD, CSRD, SEC climate rules).

**Jobs to be Done:**
- Understand the company's dependencies on ecosystem services across sourcing regions
- Quantify the company's impact on biodiversity within its value chain
- Report this information in standardized formats that satisfy regulators and investors
- Demonstrate year-over-year improvement in key metrics
- Identify supply chain risks related to ecosystem degradation

**Pain Points:**
- Lack of standardized methodologies for measuring biodiversity dependencies and impacts
- Data availability is sparse and inconsistent across different sourcing regions
- Existing consultants are expensive and produce one-off reports rather than continuous monitoring
- No clear connection between reporting metrics and actionable improvements
- Difficulty translating ecological concepts into business-relevant risk assessments

**Success Metrics:**
- Time to produce a compliant nature-related disclosure
- Confidence level in reported metrics
- Ability to show improvement trends
- Cost per sourcing region assessed

**What They're Willing to Pay For:** A system that automates the translation of field-level ecological data into boardroom-ready reports, with clear audit trails and alignment to regulatory requirements.

---

### Persona 2: Corporate Food Buyer

**Context:** Responsible for procurement relationships with farmers and cooperatives that supply raw materials. Concerned with both short-term availability and long-term sustainability of sourcing regions.

**Jobs to be Done:**
- Ensure reliable supply of agricultural products at predictable prices
- Identify sourcing regions at risk of degradation or productivity decline
- Meet corporate commitments around sustainable sourcing
- Support suppliers in adopting practices that improve resilience
- Demonstrate to customers that products come from responsibly managed lands

**Pain Points:**
- Limited visibility into ecological health of sourcing regions
- Difficulty distinguishing between short-term weather impacts and long-term degradation trends
- Pressure to meet sustainability commitments without tools to measure progress
- Suppliers don't have data to demonstrate their regenerative practices
- No way to prioritize which suppliers or regions need intervention first

**Success Metrics:**
- Supply chain risk scores by region
- Percentage of sourcing from verified sustainable/regenerative farms
- Supplier engagement with sustainability programs
- Customer perception of brand's environmental commitments

**What They're Willing to Pay For:** A biodiversity baseline and monitoring system that integrates with existing supplier management workflows, provides early warning of ecosystem risks, and generates credible sustainability credentials.

---

### Persona 3: Farmer

**Context:** Manages cropland or livestock operations, often as part of a multi-generational family business. Faces pressure from multiple directions: input costs, climate volatility, market price fluctuations, regulatory requirements.

**Jobs to be Done:**
- Maintain or improve yields while managing costs
- Reduce expensive chemical inputs (pesticides, fertilizers) where possible
- Protect the long-term health and productivity of their land
- Access premium markets or sustainability incentives that reward regenerative practices
- Demonstrate to buyers/certifiers that they're farming responsibly

**Pain Points:**
- Chemical inputs are expensive and the costs keep rising
- Don't have budget to pay for ecological monitoring or advisory services
- Want to do right by the land but don't know which practices will actually work in their specific context
- Sustainability certifications are costly and time-consuming
- Skeptical of "experts" who don't understand the economic realities of farming

**Success Metrics:**
- Net income per hectare
- Input cost reductions
- Soil health trends
- Access to premium pricing or sustainability incentives
- Resilience to weather variability

**What They're Willing to Pay For:** Realistically? **Nothing directly.** Farmers operate on thin margins and are understandably skeptical of paying for services that don't have a clear, immediate ROI. However, they're very willing to engage with programs funded by others if those programs provide tangible value.

---

### Persona 4: Agronomist

**Context:** Provides advisory services to farmers, either as an independent consultant, as part of a cooperative, or employed by an input supplier. Caught between wanting to provide cutting-edge advice and being limited by available data and analysis tools.

**Jobs to be Done:**
- Help farmers optimize yields and profitability
- Recommend interventions (inputs, practices, timing) based on field conditions
- Stay current with emerging practices like regenerative agriculture and IPM
- Differentiate their services from competitors
- Build long-term trust relationships with farmer clients

**Pain Points:**
- Most recommendations are based on generic models rather than field-specific conditions
- Don't have access to ecological data that would enable more sophisticated IPM strategies
- Farmers are skeptical of recommendations that don't account for their specific context
- Emerging practices like biodiversity monitoring are interesting but require expertise they don't have
- Competitors with better tools and data are gaining market share

**Success Metrics:**
- Client retention and satisfaction
- Demonstrable impact on client outcomes (yields, costs, sustainability metrics)
- Time spent per client engagement
- Ability to service more clients without sacrificing quality

**What They're Willing to Pay For:** Tools that make them more effective and efficient, especially if those tools provide insights they can't get elsewhere. They're the "AI-enabled Agronomist" of the future - and they know it.

---

## How These Personas Connect: The Aphid and Ladybug Story

Let me give you a concrete example of how our platform would create value across all these personas simultaneously.

Imagine a corporate food buyer sources tomatoes from farms in Southern Europe. Their sustainability officer needs to report on biodiversity dependencies and impacts. Meanwhile, the farmers are spending significant amounts on pesticides to control aphids, which are decimating their crops.

**The traditional approach:** The corporate hires a consultant to do a one-time biodiversity assessment. The report notes that there's a "moderate diversity of beneficial insects" but doesn't connect this to anything actionable. The farmers keep spraying pesticides. The sustainability report checks a box. Nothing changes.

**The NatureBound approach:**

1. Our platform integrates with the farmers' existing data - crop types, planting locations, pesticide application logs, costs.

2. We recommend a targeted data collection strategy: an eDNA survey of the fields and surrounding areas, combined with remote sensing analysis of landscape features (hedgerows, flower margins, etc.).

3. The corporate pays for this data collection as part of their biodiversity monitoring program.

4. Our platform analyzes the results and identifies a critical insight: **there's a low relative abundance of predators to pests**. Specifically, the fields lack sufficient populations of aphid predators like ladybugs (ladybirds).

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

**These insights require deep familiarity with multiple data sources and the ability to collect them cost-effectively.** No individual agronomist can be expected to master soil biochemistry, geospatial analysis, eDNA interpretation, and crop science. But a platform that interlaces these data sources and applies specialized models can surface these insights at scale.

That was the vision: make the invisible visible, and make the complex actionable.

---

_More to come in Part 2, where I'll explore the product antitheses - the reasons this thesis might be wrong, and what we learned about its validity through our attempts to build it._
