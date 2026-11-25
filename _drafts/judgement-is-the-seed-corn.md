---
layout: post
title: "Judgement Is the Seed Corn"
subtitle: "Agents don't need a sustainable pace. The people keeping them safe do."
categories: [Agentic-Extreme-Programming]
tags: [extreme programming, lean, sustainability, Agentic Engineering]
icon: seedling
description: "Agents don't get tired, but the people whose judgement keeps them safe do. XP's idea of sustainability was always about people, and with agents in the loop, the thing a team has to sustain is its judgement: how fast it spends it, and how fast it grows it."
---

<!--
STATUS: first prose draft. Everything marked AUTHOR needs your voice or your experience.
Full research notes: _research/judgement-is-the-seed-corn.md. Short reminders are kept at the bottom of this file, in a comment.
-->

In 1983, a psychologist at University College London named Lisanne Bainbridge published a short paper with a wry title: [*Ironies of Automation*](https://en.wikipedia.org/wiki/Ironies_of_Automation). She'd been studying the people who ran industrial plants (chemical works, power stations, the control rooms where a handful of operators watched over processes that mostly ran themselves), and she'd noticed that the more a system was automated, the stranger the operator's job became.

The designers automated everything they knew how to automate, and left the operator whatever was left: watching, and stepping in when something went wrong. But watching is the one thing people are worst at. Bainbridge cited decades of vigilance research showing that even a highly motivated person can't keep effective attention on a display where very little happens for much more than about half an hour. And stepping in takes skill, which fades when it isn't used. The operator who rarely touches the controls gets worse at touching them, right when the system hands them the hardest problems it has.

<!-- AUTHOR: candidate addition. Hannah Fry's example of self-driving cars handing control back to the driver as they near an emergency they can't handle: control passes from the automation to the person at the exact moment they're least ready for it. A modern, everyday version of Bainbridge's point. Source to confirm (probably Hello World, 2018); see the research file. -->

Then came the irony that has stayed with me. The automated plants of her day were being supervised by people who'd spent years running things by hand. {% include footnotes/footnote_link.html content='They were riding on skills the next generation of operators would never have the chance to learn.' count=1 %} The automation worked because of the people it was quietly making obsolete.

Forty years later, that paper reads like it was written about us.

## The second week of overtime

In [Mind the Plumbing]({% post_url 2026-11-23-mind-the-plumbing %}) I said I'd written about rebalancing in favour of sustainability before. I'd had this post in my head rather than on the page, so consider this me paying that debt.

When people hear "sustainability" in XP, most think of the old rule from the first edition of *Extreme Programming Explained*: the **40-hour week**. You could work one week of overtime, but never a second week in a row. The point was never the number. Overtime was treated as a *symptom*: if a team needed it two weeks running, something was wrong with the project, and the extra hours were hiding the problem rather than fixing it.

By the second edition, Beck and Cynthia Andres had renamed the practice **Energized Work**, and the focus moved from the hours to the person doing them. James Shore [puts it well](https://www.jamesshore.com/v2/books/aoad2/energized_work): professionals can do good work under difficult circumstances, but they do their best, most productive work when they're energized and motivated. The [Agile Manifesto](https://agilemanifesto.org/principles.html) says something similar: sponsors, developers and users should be able to maintain a constant pace indefinitely.

Agents, of course, don't have a pace to sustain. They don't get tired, they don't get bored, and they'll happily produce their hundredth pull request of the day with the same enthusiasm as their first. **But the people whose judgement keeps them safe do get tired.** And in an agentic workflow, those people are being asked to review at machine speed.

That's why I think the hundredth diff of the day is the new second week of overtime. Nobody's working longer hours, but they're spending something that runs out within the day just as surely, and, like overtime, it's a symptom. If a team's safety depends on someone reading every line an agent writes, the system isn't safe. It's just tired.

<!-- AUTHOR: a personal story of review fatigue would land well here. The moment you realised you'd approved something you hadn't really read, or watched a team's review quality slide as agent output went up. -->

## Spent and grown

The human in the loop is there to supply one thing the agent lacks: judgement. Knowing what good looks like, when something smells off, which of three plausible answers is actually right for this system and these customers. Every review, every approval, every "does this look right?" spends some of it.

Judgement is also something a team *grows*. It comes from experience, and especially from struggle: the bug you chased for two days, the design you got wrong and had to live with, the pairing session where someone more experienced asked a question you couldn't answer. XP was quietly good at growing it. Pairing spread it across the team while the work got done, and team continuity kept it there.

So here's how I've come to think about sustainability with agents in the loop: **a team has to grow judgement at least as fast as it spends it.**

Agentic flow pushes on both sides of that balance at once:

| | Before agents | With agents, unmanaged |
|---|---|---|
| **Spending** | Decisions arrive at human pace | More decisions, arriving at machine speed |
| **Growing** | Hands-on work and struggle grow judgement as a side effect | Less hands-on work, less struggle, less judgement grown |

Kent Beck has written about [the genie eating the seed corn](https://newsletter.kentbeck.com/p/augmented-coding-and-design): agents pile on features and complexity without ever reducing it, burning through the design options that make the next change possible, until they spin for hours unable to make the next change at all. His remedy is to stop and improve the design, for his sake and the genie's. He's right, and I'm not going to repeat him.

But code isn't the only seed corn. **A team's judgement is seed corn too**, and agents can eat that just as happily.

## How the store runs dry

What worries me is that the two sides don't just move in the wrong direction, they make each other worse.

**A tired reviewer stops learning.** By the hundredth diff, nobody's thinking; they're pattern matching. A rubber stamp spends judgement and grows none. Bainbridge would recognise it immediately: a person watching a process where very little goes wrong, until it does.

**A team that learns less tires faster.** A reviewer who doesn't really understand the code has to work harder to check it, and trusts it less once they have. So the reviews get slower, or shallower, and usually both.

**Juniors get the worst of both.** If a junior engineer's job becomes approving agent output, they're spending judgement they haven't had the chance to grow yet. They'll burn out, or they'll stay junior, and I'm not sure which is worse. That's the next generation of operators Bainbridge was worried about, and [I share the worry]({% post_url 2026-11-23-mind-the-plumbing %}).

It's worth noticing that XP's own most tiring practice didn't have this problem. Pairing is exhausting, and Beck has always said so. But it spreads knowledge as you go, and it meets the human needs XP's *humanity* principle talks about: belonging, accomplishment, growth. Reviewing agent output alone, all day, has all of the effort of pairing and none of the company.

<!-- AUTHOR: is there a junior you've worked with in an agent-heavy team, who learned (or didn't)? Even an anonymised sentence or two would make this real. -->

## Stop spending judgement on what a machine can check

The first half of the answer is the one I made the case for in [Mind the Plumbing]({% post_url 2026-11-23-mind-the-plumbing %}): build the feedback into the system, so people don't have to supply it by hand.

Every one of the confidences in that post moves a check out of someone's head and into the system around the agent. A test suite you trust means you're not reading every line to find out whether something broke. Least privilege means you're not approving every command to make sure the agent can't do something dangerous. Feature flags mean a bad change is a cheap experiment, rather than something a reviewer had to catch. Each one stops a person spending judgement on something a machine can check, and saves it for the decisions only a person can make.

That's the 40-hour week rule applied to agents. When review fatigue shows up, don't ask people to try harder, any more than you'd ask them to work a second week of overtime. **Treat it as a symptom: the system is depending on human attention where it should be depending on feedback.**

And then don't waste what you've saved. Beck makes the point in [*The Bet on Juniors Just Got Better*](https://simonwillison.net/2025/Dec/16/kent-beck/): the time agents free up shouldn't be invested in another feature nobody needs, it should be invested in learning. It's the same idea as XP's *slack*: a buffer built into the plan so a surprise doesn't turn into overtime, and so there's room to learn something. Agents make slack harder to keep, because when every task is cheap to delegate, nothing ever gets dropped. Protect it anyway. That's where the seed corn gets planted.

## The irony we can't automate away

Here's the tension I can't wave away. If we automate away most of the reviewing, we also take away one of the ways engineers have always learned. Reading other people's code, and having yours read, has been part of the apprenticeship for as long as there's been an apprenticeship. Automate it away, and we've made exactly Bainbridge's mistake: the system works because of experienced people, and it's removed the path the next ones would have taken to become experienced.

So "automate the checks" isn't enough on its own. Something has to replace the learning. These are the things I've found work, or that I'm experimenting with:

* **Humans write the tests, agents write the code.** Deciding what the system *should* do is where the judgement lives, so keep a person doing that part, and let the agent do the part that doesn't need it. It's also the cleanest way I know to make sure [no agent marks its own homework]({% post_url 2026-11-23-mind-the-plumbing %}).
* **Pairs supervise agents together.** Two people steering one agent is the closest thing I've found to traditional pairing. [The agent drives]({% post_url 2026-11-08-whose-decision-was-that-anyway %}), both people navigate, and the apprenticeship happens in the decisions rather than the keystrokes. It also brings back the company that reviewing alone lacks.
* **Think out loud with the agent.** Used as a rubber duck that talks back, an agent can make you better at interrogating your own reasoning, rather than replacing it. The difference is whether you're asking it to *decide* or asking it to *argue*.
* **Deliberate practice.** Sometimes the right thing to do is solve the problem yourself, on purpose, knowing the agent could do it faster. Musicians don't stop practising scales because recordings exist.

<!-- AUTHOR: which of these have you actually seen work, and which are still hunches? The post is stronger if it says so plainly, as Mind the Plumbing did with "my route". -->

## My overtime rule

The 1999 rule was blunt, which is what made it work: one week of overtime, never two in a row. Here's my attempt at the agent version:

> **One day of rubber-stamping is a bad day. Two in a row is a broken system.**

If someone on the team has spent a day approving things they didn't really read, that happens. If it happens again the next day, stop asking them to review harder, and fix whatever is making the system depend on their attention.

Some signals that a team is spending judgement faster than it grows it:

* Review comments get shorter as the number of pull requests goes up.
* Fewer people can explain why a recent change works the way it does.
* The same few senior people are approving everything, and the juniors are approving nothing, or the other way round.
* Nobody can remember the last time they solved a hard problem without an agent.
* Retrospectives talk about throughput, and never about what anyone learned.

<!-- AUTHOR: are these the right signals? You'll have better ones from your own team. -->

## Sustaining the people

Bainbridge's paper ends on a line I keep coming back to: the more advanced a control system is, the more crucial the human operator's contribution may become. Automation doesn't remove the need for judgement. It concentrates it into the moments that matter most, and makes it easier to lose in between.

XP always understood that what has to last isn't the code, or the velocity, or the plan. It's the people, and their ability to keep making good decisions, week after week, indefinitely. That hasn't changed. What's changed is how fast we can spend that ability, and how easily we can stop growing it.

So, put simply: **agents don't need a sustainable pace; the people whose judgement keeps them safe do.** Build the feedback into the system so they stop spending judgement on routine checks, and put what you save back into growing it.

Don't let the genie eat the seed corn. Either kind.

{% capture footnotes %}
Bainbridge's point was that the automated systems of the early 1980s were being monitored by former manual operators, riding on skills that later generations couldn't be expected to have.
{% endcapture %}

{% include footnotes/footnote.html notes=footnotes %}

<!--
REMAINING NOTES (delete before publishing)

Verify before publishing:
- Bainbridge (full text: https://gwern.net/doc/sociology/technology/1983-bainbridge.pdf): the vigilance passage ("impossible for even a highly motivated human being to maintain effective visual attention towards a source of information on which very little happens, for more than about half an hour", citing Mackworth 1950) is confirmed via secondary copies. Still check against the paper. Also check the "riding on their skills" line (footnote) and the closing "the more advanced a control system is, so the more crucial may be the contribution of the human operator".
- Bainbridge's affiliation (UCL) and that she studied process-control operators: check before publishing.
- Energized Work: the draft paraphrases Shore rather than quoting Beck. If you want Beck's own wording ("Work only as many hours as you can be productive..."), check XP Explained 2nd ed. A web search did not confirm it.
- Slack: the draft describes it as a buffer plus room to learn. Check the 2nd ed. wording ("minor tasks that can be dropped").
- Humanity needs (belonging, accomplishment, growth): the draft uses three of the five from memory. Check the list.
- Don't attribute the "sustainable pace" rename to Beck or Jeffries; the draft doesn't.

Open questions still for you:
- The opening: Bainbridge is my proposal for "a metaphor of your own" (Beck owns "seed corn"). If you'd rather a personal or different historical story, the "operators of the next generation" thread is what it needs to carry.
- Is judgement really the thing that must last, or is it energy, craft, or the team itself?
- Is "One day of rubber-stamping is a bad day. Two in a row is a broken system." the overtime rule you want?
- Images: banner image, image-desc and social-image are not set yet.

Material not yet used (candidates for later posts):
- The 24-hour agent as overtime by proxy (agents running overnight; the hours aren't the issue, the reason you need them is).
- Mutual benefit and next year's maintainer (does the agent's change benefit whoever changes it later?).
- Beck's "features versus options" and the flat cost-of-change curve (covered by Beck's genie posts, so only referenced here).
- Team continuity as a corollary practice.

Housekeeping:
- After publishing, link this post from the "I've written about rebalancing in favour of sustainability before" line in _posts/2026-11-23-mind-the-plumbing.md.
- The draft's opening of "The second week of overtime" assumes that line will link here; reword if not.

Sources:
- Lisanne Bainbridge, Ironies of Automation (Automatica, 1983). https://en.wikipedia.org/wiki/Ironies_of_Automation
- James Shore, AoAD2: Energized Work. https://www.jamesshore.com/v2/books/aoad2/energized_work
- Bill Wake, Overview of "Extreme Programming Explained, 2/e". https://xp123.com/?p=197
- Kent Beck, The Genie Eats The Seed Corn. https://newsletter.kentbeck.com/p/augmented-coding-and-design
- Kent Beck, Sustainable Augmented Development (YOW! 2025). https://gotopia.tech/sessions/3895/sustainable-augmented-development
- Simon Willison quoting Kent Beck, 2025-12-16. https://simonwillison.net/2025/Dec/16/kent-beck/
- Mike Cohn, Why a sustainable pace is so important to agile teams. https://www.mountaingoatsoftware.com/blog/why-a-sustainable-pace-is-so-important-to-agile-teams
- Agile Manifesto principles. https://agilemanifesto.org/principles.html
-->
