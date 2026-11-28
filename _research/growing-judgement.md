# Research notes: protecting and growing judgement in the age of AI

Research notes, not prose. This file lives in `_research/`, which Jekyll does not publish.
It widens the research behind `_research/judgement-is-the-seed-corn.md`: that file covers *spending* judgement (fatigue, sustainable pace), and this one covers *what kinds of judgement exist, how each is grown, and whether agents cut off the supply.*

## The question

A common view: "what's left for engineers is judgement." The conversation mostly means **technical** judgement. That's real, but it's only one of three kinds, and the third one is the one I'm most worried about.

> Are we losing the judgement that comes from being close to the code, now that engineers aren't as close to it as they were before coding agents? And what does that mean, in practice, for what leaders need to do?

## Three kinds of judgement

### 1. Technical judgement

- Architecture, trade-offs, reliability, long-term maintainability. Knowing when something smells off.
- This is the kind everyone talks about, and the kind Beck's genie posts are about.

### 2. Product judgement (taste)

- Knowing what's worth building, what good looks like to a user, what to leave out.
- Overlaps heavily with product managers. That overlap isn't new (see "the product engineer isn't new" below).

### 3. The third kind: the product's interpreter (working name)

Needs a name. Candidates: *stewardship*, *translation*, *product-in-context*, *the product's interpreter*.

- The judgement at the overlap between **the state of the product** (how it actually works, today, including its quirks), **the domain**, and **the problem a specific customer is trying to solve**.
- Much of what engineering leaders actually do is steward the product through the company: making sure someone can answer the questions that come in from commercial and operations teams. *How does it work? Why does it do that? Can it do X for this customer?*
- The answers shape **what the company can promise customers**. A wrong answer becomes a broken promise, a lost deal or a bad contract.
- In B2B, each customer operates in a slightly different context. Someone has to translate what the product does, and how it does it, into each customer's problem.
- This has been a large, mostly invisible part of the software engineer's job.

**Why it's different from the other two:**

- It's mostly **tacit**: it lives in people, not in the code or the docs.
- It's built as a **side effect**: of writing the code, debugging it at 2am, and being the person who got asked.
- It's **organisational**: it matters most outside engineering, so engineering metrics don't see it.
- "Mind the Plumbing" already covers part of this in the "We all know why it works this way" confidence: agents can tell you what the code *appears* to do, but the *why* often isn't in the code. It's in the shape and origin of the data, side effects and history nobody wrote down.

## Theory: why this judgement can't simply be written down

### Peter Naur, *Programming as Theory Building* (1985)

- Programming is building a *theory* of how the program relates to the world it serves. The theory lives in the programmers' heads.
- The theory is what lets someone **explain, justify and answer questions** about the program, which is exactly the third kind of judgement.
- Naur argues the theory **can't, in principle, be fully captured in documentation**.
- **Program death:** a program dies when the team holding its theory dissolves, even though it can keep running. It shows when requests for change can no longer be answered intelligently.
- Reviving a program means rebuilding the theory, which needs people who hold it, not just the docs.
- **The question for agents:** if the agent writes the code, who builds the theory? Is a codebase that no human wrote ever "alive" in Naur's sense?
- Source is via secondary summaries; **check exact wording against the paper** before quoting. Reprinted in *Computing: A Human Activity* (1992).

### Margaret-Anne Storey: technical, cognitive and intent debt (2026)

- Coined "cognitive debt" in late 2025; the paper *From Technical Debt to Cognitive and Intent Debt* (arXiv 2603.22106, March 2026) proposes a **triple debt model**:
  - **Technical debt:** in the code.
  - **Cognitive debt:** in the people. The erosion of *shared* understanding across a team, not one person's knowledge.
  - **Intent debt:** in the externalised knowledge. Missing rationale that humans and AI both need.
- From her blog: the two are separate. A team can have low cognitive debt and high intent debt, because intent often lives in conversations and shared experience, not documents.
- Useful framing for the third kind of judgement: it's cognitive debt that shows up *outside* engineering, when Sales asks a question nobody can answer.
- Follow-up: *Cognitive Tours: Making Understanding a Deliverable in AI-Assisted Development* (arXiv 2611.08456), a tool to repair cognitive and intent debt. **Read this**, it may be a concrete practice.

### Addy Osmani, "comprehension debt" (March 2026)

- The gap between the code a team can produce with AI and what it actually understands.
- O'Reilly's point: technical debt announces itself through friction; comprehension debt produces **false confidence**, because the codebase looks clean. Velocity, DORA and coverage can all stay green while understanding erodes.
- That's the key risk for the third kind: you find out it's gone when someone in Sales asks.

### Lisanne Bainbridge, *Ironies of Automation* (1983)

- Covered in the seed-corn research file. The relevant irony here: the automated systems were run by people whose skills came from the manual era, and later generations wouldn't have them.
- Hannah Fry's self-driving handover example belongs here too: control comes back to the human at the worst moment. The Sales question about an edge case for a key customer is that moment.

## Evidence: is it actually being lost?

Ordered roughly by strength. All of it is early.

- **Anthropic, *How AI assistance impacts the formation of coding skills* (RCT, January 2026).**
  - 52 engineers learning Trio (a Python async library). The AI group scored 50% on a comprehension quiz, against 67% for the group that coded by hand: a 17 percentage-point gap.
  - The time saving was small and not statistically significant.
  - The biggest gap was on **debugging** questions.
  - **How people used AI mattered most.** Heavy delegation and iterative AI debugging scored under 40%. People who asked follow-up and conceptual questions scored higher.
  - Limits: small sample, one hour of learning, one library, immediate comprehension only.
  - **Why it matters:** it suggests the loss isn't inevitable. It depends on the *mode* of use. That's something leaders can shape.
- **Lee et al., *The Impact of Generative AI on Critical Thinking* (Microsoft Research and CMU, CHI 2025).**
  - Survey of 319 knowledge workers, 936 examples.
  - Higher confidence in AI is associated with **less** critical thinking; higher self-confidence with **more** (at a higher perceived cost).
  - AI shifts critical thinking towards verifying, integrating and *stewarding* tasks.
  - On routine, low-stakes work under time pressure, people report less critical thinking with AI.
  - Self-reported, so it's about perception, not measured skill.
- **Matt Beane, robotic surgery and "shadow learning" (ASQ 2019) and *The Skill Code* (2024).**
  - Robotic surgery let one expert operate alone, so residents got **10 to 20 times less practice**.
  - The residents who succeeded did it through "shadow learning": norm-bending, out-of-sight practice. Beane estimates at most one in five at top institutions were succeeding.
  - *The Skill Code*: skill is built through **challenge** (working near the edge of your ability), **complexity** (understanding the whole work system) and **connection** (trust and respect between expert and novice).
  - His warning: technology placed between seniors and juniors cuts the juniors out, because novices are slower and make more mistakes.
  - He doesn't argue for retreat: technology can be part of the solution (digital apprenticeships).
  - **Complexity** maps closely to the third kind of judgement: understanding the whole system the work sits in, including the customer.
- **Lave and Wenger, legitimate peripheral participation (1991).**
  - Newcomers learn by doing real but peripheral work, and moving towards the centre.
  - Recent papers argue AI absorbs exactly that peripheral work: bug fixes, simple tests, well-specified features. One cites a 25% drop in entry-level postings at the 15 largest US tech firms, 2023 to 2024 (arXiv 2602.00496; not yet peer reviewed as far as I can tell).
  - Beck has his own reading: LPP as a way to learn a new language by pairing with an AI. More optimistic. Worth reading his summary (kentbeck.com).
- **Endoscopist deskilling (Budzyń et al., *Lancet Gastroenterology & Hepatology*, 2025).**
  - Adenoma detection in non-AI colonoscopies fell from 28.4% to 22.4% after doctors got used to AI assistance.
  - **Contested:** observational, 19 endoscopists, population differences, authors with ties to the device maker. Use only as a "this is being noticed outside software" example, and say it's contested.

**What the evidence doesn't cover:** none of it measures the third kind of judgement directly. It's about technical comprehension and critical thinking. The link to "can anyone answer Sales' question?" is my inference. **That gap may be the most useful thing the post can point out.**

## The counterpoint: the product engineer isn't new

Andrea Laforgia (Head of Engineering at Otera), LinkedIn post, November 2026:

- There's an idea that AI has broken down the barriers between professions: engineers must become "product engineers", PMs can build, designers can generate front ends, everyone becomes a bit of everything.
- He argues that misreads the problem. **There were never supposed to be handovers**, and the product engineer is what a software engineer should always have been.
- Takeuchi and Nonaka, *The New New Product Development Game* (HBR, 1986): the relay race, where each specialist passes the baton, should give way to rugby, where one cross-functional team moves the ball together. Scrum took its name from this paper.
- Agile Manifesto principle: "Business people and developers must work together daily throughout the project." Daily, not at a handover.
- The gap between product and engineering is one **we created ourselves** by turning collaboration into handovers. AI hasn't closed it.
- AI doesn't turn everyone into a bit of everything either. An engineer's value is still judgement about architecture, trade-offs, reliability and maintainability. A PM's is judgement about customers, priorities and strategy. AI can't replace people with different expertise working together, continuously, on the same problem.

**How it relates to my question:**

- It supports the idea that judgement is the core of each role, and that the roles stay distinct.
- But it treats engineering judgement as *technical*. The third kind sits in the overlap he describes: engineers and business people working together daily is where the interpreter judgement was built.
- Possible synthesis: **the third kind of judgement was always built in the rugby scrum, not in the code.** Being close to the code gave engineers the *how*; being close to the business gave them the *so what*. Agents threaten the first. Handovers already threatened the second.
- Open question: is closeness to the code actually needed for the third kind, or was it just the route most engineers happened to take?

## A market signal: the forward deployed engineer

- Forward deployed engineers (FDEs) are engineers embedded with a customer, mapping their data and workflows and making the product work in their context. "Part engineer, part consultant, part product translator."
- Credited to Palantir. Rapid growth in 2025: Indeed postings up over 800% from January to September 2025 (via eWeek). OpenAI, Anthropic and Cohere expanding FDE teams (via FT); Salesforce committing to 1,000.
- AI labs' rationale: adoption depends on deployment, not just model quality.
- **Why it matters:** as code gets cheaper, the market is paying a premium for exactly the third kind of judgement. Worth noting the irony: companies are hiring it as a specialist role at the same moment it may be eroding as a side effect of ordinary engineering.
- Sources are mostly vendor blogs, recruiters and trade press. Use the hiring figures with care.

## What it might mean for leaders (hypotheses, not answers)

Organised by Beane's three Cs, plus the third-kind specifics. Mark which ones I've actually seen work.

### Make understanding a deliverable

- If the agent writes the code, **the theory (Naur) has to be built on purpose**. It no longer comes free with writing the code.
- Story reviews before work starts and after it ships ("Mind the Plumbing" route). Could the person who steered the agent explain the change to someone in Sales?
- Storey's *Cognitive Tours* as a possible practice. **Read it.**
- ADRs and captured intent for intent debt, so the *why* is available to people and agents.

### Use the mode of AI that builds understanding

- The Anthropic RCT says conceptual questioning preserved understanding; delegation didn't.
- Make "ask the agent to explain, then explain it back" the norm, not "ask the agent to do it".
- Humans write the acceptance tests, in the domain's language (ubiquitous language). That keeps the human doing the part that needs domain judgement.

### Keep juniors connected (Beane's connection)

- Pairs supervising agents together, so the expert–novice bond survives.
- Don't let the agent become the thing between seniors and juniors.

### Give people the whole system (Beane's complexity)

- **Rotate engineers through the places the third kind of judgement is exercised:** support escalations, customer calls, sales engineering, onboarding of a new customer, incident reviews with ops.
- Have engineers answer the commercial and ops questions directly, rather than routing them through a lead. Leaders currently absorb these questions, which concentrates the judgement in the leader.
- Use the time agents save for this (Beck: invest freed time in learning). That's the slack.

### Keep the theory in the team (Naur's program death)

- Team continuity (XP corollary practice). Reorgs and churn kill programs.
- Be wary of agent-written systems nobody on the current team has built a theory of. Know which parts of the product are "dead" in Naur's sense.

### Measure what metrics miss

- How long does it take to answer a question from Sales or ops? How many people can answer it?
- How often does an answer have to go via "let me check with the agent" or "let me check with X"?
- Have any customer promises been broken because of a wrong answer about how the product works?
- Which parts of the system can only one person explain?

## Open questions for the author

- What's the name for the third kind of judgement?
- Is closeness to the code actually necessary for it, or was it only the usual route?
- Do I have a story? A question from Sales or a customer that nobody could answer, or that only one person could. Or an engineer who stopped being able to answer because they hadn't written the code.
- Is this one post or two? "Seed corn" is about spending and growing judgement in general. This could be its own post on the third kind.
- Where does this sit with Laforgia's argument? Agree and extend, or push back on "engineering judgement = technical judgement"?
- Can agents help *build* the third kind? An agent that can trace a customer's question through the code and data could be a tool for learning, if used conceptually rather than as an oracle.

## Sources

- Anthropic, How AI assistance impacts the formation of coding skills (January 2026). <https://www.anthropic.com/research/AI-assistance-coding-skills>; paper: <https://www.arxiv.org/pdf/2601.20245>; coverage: <https://www.infoq.com/news/2026/02/ai-coding-skill-formation>
- Lee et al., The Impact of Generative AI on Critical Thinking (CHI 2025). <https://advait.org/files/lee_2025_ai_critical_thinking_survey.pdf>
- Peter Naur, Programming as Theory Building (1985). <https://gist.github.com/onlurking/fc5c81d18cfce9ff81bc968a7f342fb1>; summary: <https://xrrocha.github.io/solo-dev-musings/001-naur-documentation-pessimism/en/naur-paper-en.html>
- Margaret-Anne Storey, From Technical Debt to Cognitive and Intent Debt (2026). <https://arxiv.org/abs/2603.22106>; blog: <https://margaretstorey.com/blog/2026/02/09/cognitive-debt/>, <https://margaretstorey.com/blog/2026/06/09/missing-stop-sign/>
- Margaret-Anne Storey, Cognitive Tours. <https://arxiv.org/pdf/2611.08456>
- Addy Osmani, Comprehension debt. <https://addyosmani.com/blog/comprehension-debt/>; O'Reilly: <https://www.oreilly.com/radar/comprehension-debt-the-hidden-cost-of-ai-generated-code/>
- Matt Beane, Shadow learning (UCSB summary). <https://www.engineering.ucsb.edu/news/shining-light-shadow-learning>; STAT: <https://www.statnews.com/2018/01/10/robotic-surgery-doctors-practice/>
- Matt Beane, The Skill Code (2024). <https://ide.mit.edu/publication/the-skill-code-how-to-save-human-ability-in-an-age-of-intelligent-machines/>; McKinsey interview: <https://www.mckinsey.com/featured-insights/mckinsey-on-books/author-talks-how-to-make-skill-development-count-in-the-digital-age>
- Kent Beck, Legitimate Peripheral Participation. <https://www.kentbeck.com/summaries/legitimate-peripheral-participation/>
- GenAI and the junior-to-senior pathway (arXiv 2602.00496). <https://arxiv.org/pdf/2602.00496>
- WEF, As AI reshapes entry-level software jobs, where will senior developers come from? <https://www.weforum.org/stories/artificial-intelligence/as-ai-reshapes-entry-level-software-jobs-where-will-senior-developers-come-from/>
- Budzyń et al., Endoscopist deskilling after exposure to AI (Lancet Gastroenterol Hepatol, 2025). <https://wrap.warwick.ac.uk/id/eprint/191005>; critique: <https://gi.org/journals-publications/ebgi/zhou_sep2025/>
- Forward deployed engineers: <https://www.eweek.com/news/openai-anthropic-cohere-ai-hiring/>, <https://newsletter.pragmaticengineer.com/p/forward-deployed-engineers>
- Andrea Laforgia, LinkedIn post on "product engineers" (November 2026). Screenshot shared by the author; **get the post URL**.
- Takeuchi and Nonaka, The New New Product Development Game (HBR, 1986). <https://hbr.org/1986/01/the-new-new-product-development-game>
- Agile Manifesto principles. <https://agilemanifesto.org/principles.html>
