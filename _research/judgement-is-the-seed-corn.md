# Research notes: "Judgement Is the Seed Corn"

Research notes and working thesis for the post drafted in `_drafts/judgement-is-the-seed-corn.md`.
This is not prose for publication. It lives in `_research/`, which Jekyll does not publish.

## Why this post exists

"Mind the Plumbing" (2026-11-23) says: *"I've written about rebalancing in favour of sustainability before."*

That claim does not hold yet. The nearest earlier post is "Turning Spaghetti into Lasagne" (2015-08-29). It covers the move from "fast and messy" to "fast and sustainable" code at a company that had found its business model. That is about technical debt. It is not about what XP means by sustainability.

This post fills that gap. Then the line in "Mind the Plumbing" can link to it.

Other sustainability mentions in the blog are unrelated: climate impact of tech (2019-05-08), a memory leak (2019-02-13), and the NatureBound posts (2026-01).

## Research: what XP actually says about sustainability

XP treats sustainability as more than "don't work late". It appears in five places.

### 1. Pace: from "40-hour week" to "Energized Work"

- **First edition (1999):** the practice was "40-hour week". The rule: you can work one week of overtime, but never a second week in a row. Overtime is a symptom of a serious problem on the project. Extra hours hide the problem. They do not fix it.
- **Second edition (2004, with Cynthia Andres):** renamed to **Energized Work**. Bill Wake's review calls it "a reinterpretation of '40-hour week' and 'sustainable pace'".
  - Wording from memory, **verify against the book before quoting**: "Work only as many hours as you can be productive and only as many hours as you can sustain."
  - The focus moves from the number of hours to the state of the person who does the work.
- **James Shore (AoAD2):** "We work at a pace that allows us to do our best, most productive work indefinitely." Also: "professionals can do good work under difficult circumstances, [but] they do their best, most productive work when they're energized and motivated."
- **Agile Manifesto, principle 8** (Beck signed it): "The sponsors, developers, and users should be able to maintain a constant pace indefinitely."
- Who renamed "40-hour week" to "sustainable pace" is disputed in secondary sources (Beck or Ron Jeffries). Do not attribute it.

### 2. Slack

- A corollary practice in the second edition.
- From memory, **verify**: put some minor tasks in every plan that you can drop if you fall behind.
- Some summaries also describe slack as time for learning and experiments.
- It is a buffer built into the system, so a surprise does not turn into overtime.

### 3. The code: keep the cost of change flat

- The economic case in the first edition: a flat cost-of-change curve, not an exponential one.
- Simple design, refactoring, TDD and incremental design keep change cheap for the life of the system.
- Second edition: only code and tests are permanent artifacts. Everything else must justify itself.

### 4. Economics and options

- "Economics" is an XP principle.
- Beck later developed it into **features versus options** (Tidy First?, Empirical Software Design).
  - A feature adds behaviour now. It can degrade the design.
  - An option makes the next change cheaper: less coupling, more cohesion.
- A sustainable system keeps a stock of options.

### 5. People and teams

- **Respect:** added as the fifth value in the second edition (with communication, simplicity, feedback, courage).
- **Humanity:** a principle. People develop software, and they have human needs: basic safety, accomplishment, belonging, growth, intimacy (list from memory, **verify**).
- **Mutual benefit:** a principle. Beck calls it the most important and the hardest to keep. Every activity should benefit everyone involved, **including the future maintainer**.
  - Automated tests pass: they help the author now and the maintainer later.
  - Large internal documentation fails: it costs now and rarely helps later.
- **Team continuity:** a corollary practice. Keep effective teams together.
- **Pair programming:** spreads knowledge as you work. Beck admits it is tiring and says to limit it.

## What Beck has already said about agents

Beck has already covered the code side of this. The post must not repeat it. It must go further.

- **"The Genie Eats The Seed Corn"** (newsletter, 2025-05-03)
  - "Farmers in olden times had a saying, 'Don't eat the seed corn.' ... My coding genie, unfortunately, doesn't know this saying."
  - "More features introduces more complexity" and "More complexity slows development of more features."
  - End state: "We are out of options. The genie spins for hours without being able to correctly implement the next feature."
  - "One of the not-so-magical things about today's genies is their lack of taste."
  - "The genie seems to assume that its planetary-sized brain is capable of handling any amount of complexity, so it needn't ever reduce complexity. It's right until it isn't."
  - Remedy: "Manually improving the design reduces complexity, for me & the genie, & enables developing more features."
- **"Sustainable Augmented Development"** (YOW! Melbourne 2025)
  - "Genies are great at cranking out features. Unfortunately they don't clean the kitchen as they cook. Progress slows then stops as yesterday's expedient decision becomes today's roadblock."
  - Proposed fixes: "Periodic pauses in feature development to improve structure and thus increase optionality" and "Development in small steps validated by automated tests."
- **"The Bet On Juniors Just Got Better"** (newsletter, 2025-12, via Simon Willison)
  - "The time freed this way isn't invested in another unprofitable feature, though, it's invested in learning."
  - "the genie, used well, accelerates learning."

**Gap:** "agents run up technical debt" is the angle Beck has covered. The human side of XP sustainability (Energized Work, Slack, Humanity, Team Continuity) is much less covered for agents.

## Ironies of automation: control handed back at the worst moment

The draft's opening uses this thread. Collected here with sources.

- **Lisanne Bainbridge, *Ironies of Automation* (Automatica, 1983).**
  - Designers automate what they can and leave the operator the rest: monitoring, and taking over when something goes wrong.
  - Vigilance: citing Mackworth (1950), "it is impossible for even a highly motivated human being to maintain effective visual attention towards a source of information on which very little happens, for more than about half an hour." Confirmed via secondary copies. **Verify against the paper.**
  - Skills fade when not used, so the operator is worst at stepping in exactly when the system needs them.
  - From memory, **verify**: today's automated systems are monitored by former manual operators, "riding on their skills", which later generations cannot be expected to have.
  - From memory, **verify**: "the more advanced a control system is, so the more crucial may be the contribution of the human operator."
  - Full text: <https://gwern.net/doc/sociology/technology/1983-bainbridge.pdf>
- **Hannah Fry: self-driving cars hand control back to the driver when the car nears an emergency and doesn't know what to do.**
  - The handover happens at the moment the human is least prepared and the situation is hardest: they've been passengers, not drivers, and now they have seconds.
  - The clearest everyday example of the automation-to-operator handover going wrong. It makes Bainbridge concrete for readers who've never seen a control room.
  - Agent parallel: the agent handles the routine work, then hands the human the gnarly incident, the ambiguous requirement or the failing migration, cold, with no context built up and their judgement already spent on the day's rubber stamps.
  - **Find the source before using it:** probably *Hello World: How to Be Human in the Age of the Machine* (2018), the chapter on cars, which (from memory) also draws on Bainbridge. Could also be one of her talks or lectures. Get the exact wording and any examples she cites.

## Candidate angles (the full list)

The angles we considered. Numbers 1 and 5 are the chosen direction. Keep the others as material or for later posts.

1. **Agents don't get tired, but their supervisors do.** Energized Work was about the human. Now the human reviews at machine speed. The hundredth diff of the day is the new second week of overtime, and it is a symptom in the same way. This extends the line in "Mind the Plumbing": "by the hundredth request of the day, nobody is really reading them."
2. **Agents eat the slack.** Slack works because some tasks can be dropped. When every task is cheap to delegate, nothing is dropped, and the buffer disappears. Inverse: use slack to point agents at cleaning the kitchen.
3. **The 24-hour agent as overtime by proxy.** Agents that run through the night look like free capacity. The 1999 rule says the hours are not the issue. The reason you need them is. What is the agent equivalent of "never two weeks in a row"?
4. **Mutual benefit and next year's maintainer.** Does the agent's change benefit whoever must change it later? A sharper test than "is the code clean?"
5. **People are what must last.** Team continuity, apprenticeship through pairing, and how the next generation learns. "Mind the Plumbing" already raises the worry about how the next generation learns.

## The chosen direction: where 1 and 5 overlap

**Both are about judgement: how a team builds it and how it spends it.**

- **Angle 1 is about spending it.** The human in the loop is there to supply judgement. Every review, approval and "does this look right?" spends it. Energized Work recognised that this capacity runs out within a day.
- **Angle 5 is about building it.** Experience, struggle, pairing and apprenticeship grow judgement in a person and spread it across a team. Team continuity keeps it in the team.

### Sustainability as a budget

Sustainability is a balance: the team must build judgement at least as fast as it spends it.

Agentic flow pushes on both sides at once:

| | Before agents | With agents, unmanaged |
|---|---|---|
| **Spend** | Decisions arrive at human pace | More decisions, at machine speed |
| **Build** | Hands-on work and struggle build judgement as a side effect | Less hands-on work, less struggle, less judgement built |

Beck applied "seed corn" to code options. The team's judgement is seed corn too.

### How each one makes the other worse

- **A tired reviewer stops learning.** By the hundredth diff, you match patterns. You do not think. A rubber stamp spends judgement and builds none.
- **A team that learns less tires faster.** A reviewer who does not understand the code works harder to check it, and trusts it less.
- **Juniors get the worst of both.** If their job becomes approving agent output, they burn out and stay junior.
- **XP pairing already handled both.** Pairing is tiring, but it spreads knowledge while you work, and it meets the Humanity needs (belonging, growth). Reviewing agent output alone has the effort of pairing and none of the social side.

### Tie back to "Mind the Plumbing"

- The 1999 rule treated overtime as a symptom. In the same way, review fatigue shows that the system depends on human attention where it should depend on feedback built into the system.
- The confidences in "Mind the Plumbing" move the checks into the system ("the more feedback is built into the system around it, the more of its actions I can trust it to take on its own").
- That frees human attention. Beck's advice applies: invest the freed time in learning, not in another feature.

### Working thesis

> Agents don't need a sustainable pace; the people whose judgement keeps them safe do. Build feedback into the system so people stop spending judgement on routine checks, and put what you save back into growing it.

### The tension the post must face

If you automate the reviews away, you also remove one of the ways juniors learn. Reading other people's code has always been part of the apprenticeship.

So the post cannot only say "automate the checks". It must say what replaces that learning. Candidates:

- Pairing with an agent while you think out loud (ties to the "rubber duck that talks back" in "Mind the Plumbing").
- Deliberate practice.
- Humans write the tests and agents write the code. This keeps the human doing the part that needs judgement. It also matches "no agent marks its own homework" in "Mind the Plumbing".
- Human pairs supervise agents together, so the social and apprenticeship side survives.

## Open questions for the author

- Is judgement the thing that must last? Or is it energy, craft, or the team itself?
- What do I believe about sustainability that XP does not say?
- What is the opening metaphor? "Mind the Plumbing" used the Great Stink. "Seed corn" is Beck's. Find one of my own.
- What are the signals that a team spends more judgement than it builds? (Compare the "signal" lines in "Mind the Plumbing".)
- What is my agent version of the overtime rule?
- Do I have a personal story of review fatigue, or of a junior who learned (or did not learn) in an agent-heavy team?

## Housekeeping

- After publishing, link this post from the "I've written about rebalancing in favour of sustainability before" line in `_posts/2026-11-23-mind-the-plumbing.md`. Until then, that line points at nothing.
- Verify every "from memory" quote against *Extreme Programming Explained* (2nd ed.) before publishing.

## Sources

- Lisanne Bainbridge, Ironies of Automation (1983). <https://en.wikipedia.org/wiki/Ironies_of_Automation>
- Hannah Fry, Hello World (2018). **Source to confirm** for the self-driving handover example.
- James Shore, AoAD2: Energized Work. <https://www.jamesshore.com/v2/books/aoad2/energized_work>
- Bill Wake, Overview of "Extreme Programming Explained, 2/e". <https://xp123.com/?p=197>
- Kent Beck, The Genie Eats The Seed Corn. <https://newsletter.kentbeck.com/p/augmented-coding-and-design>
- Kent Beck, Sustainable Augmented Development (YOW! 2025). <https://gotopia.tech/sessions/3895/sustainable-augmented-development>
- Simon Willison quoting Kent Beck, 2025-12-16. <https://simonwillison.net/2025/Dec/16/kent-beck/>
- Mike Cohn, Why a sustainable pace is so important to agile teams. <https://www.mountaingoatsoftware.com/blog/why-a-sustainable-pace-is-so-important-to-agile-teams>
- Agile Manifesto principles. <https://agilemanifesto.org/principles.html>
