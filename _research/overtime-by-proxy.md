# Research notes: "Overtime by Proxy"

Scope and outline for a single, tightly scoped post. Not prose. This file lives in `_research/`, which Jekyll does not publish.
Related notes: `_research/judgement-is-the-seed-corn.md` (where the idea started as candidate angle 3) and `_research/growing-judgement.md`.

## Working thesis

> XP's first edition treated overtime as a symptom: the hours weren't the problem, the reason you needed them was. Agents that work through the night are overtime by proxy. They look like free capacity, but they hide the same problem, and the bill still lands on a person: the next morning.

## The idea in four moves

1. **The rule.** First edition XP: one week of overtime is fine, never two in a row. Overtime meant something was wrong with the plan, and the extra hours hid it rather than fixed it. (Energized Work in the second edition moved the focus to the person.)
2. **The proxy.** Agents don't get tired, so running them overnight and at weekends looks like free capacity. Nobody is working late, so the rule doesn't seem to apply.
3. **The symptom is the same.** Why do you need agents running all night? Usually because the plan holds more than the team can absorb. Running agents overnight avoids the scope conversation, just as overtime did. It also eats XP's *slack*: when every nice-to-have can be handed to an agent at 6pm, nothing ever gets dropped.
4. **The bill comes back to a person.** "Overtime by proxy" in two senses: the agent works the hours, and a person pays for them.
   - **In the morning:** what was built overnight lands as a review queue. That's Lean's inventory and overproduction ("Mind the Plumbing"), arriving all at once, while the author (the agent) has no memory of why it did what it did.
   - **In the evening:** people checking on agent sessions from their phone at 11pm, unblocking a stuck run before bed. The human's overtime comes back in small, unbilled pieces.

## The nuance that keeps it honest

"Mind the Plumbing" *endorses* overnight agent work: characterisation tests that "AI can write while you sleep", and agents in cloud sandboxes experimenting while engineers do something else. The post has to square that, not contradict it.

The distinction:

- **Night-shift work that leaves less for the morning:** characterisation tests proved by mutation testing, investigations, throwaway prototypes, options to choose between, anything the system can check without a person. The feedback is built in, and you can throw the output away.
- **Night-shift work that leaves more for the morning:** features waiting for review, big diffs, anything that needs a person's judgement before it's worth anything.

Candidate line: **"Good night-shift work leaves less for the morning, not more."**

## Candidate overtime rule (the agent version of "never two weeks in a row")

Options to choose from:

- "Agents can work the night shift. Nobody should have to clean up after it in the morning."
- "If your agents need to work through the night two nights in a row to keep up, the plan is wrong."
- "Let agents work overnight on anything you'd happily throw away in the morning."

## Proposed outline

1. **Opening:** an image of its own. Ideas to explore: night shifts and handovers (hospitals, factories, where the handover is the dangerous moment); or a personal moment checking an agent from your phone late at night. **AUTHOR: do you have one?**
2. **The 40-hour week:** what the rule actually said, and why it was about symptoms.
3. **Free capacity:** why overnight agents feel exempt.
4. **Same symptom:** the scope conversation you're avoiding, and the slack you're eating.
5. **Who pays:** the morning queue and the evening phone check.
6. **The good night shift:** the distinction above, tied back to "Mind the Plumbing".
7. **My rule:** one line.

Target: short. Maybe 1,000 to 1,400 words, about half the length of "Mind the Plumbing".

## Deliberately out of scope

- Judgement as seed corn, juniors, apprenticeship: `_research/growing-judgement.md` and later posts.
- The third kind of judgement (the product's interpreter).
- Beck's code-side seed corn (features versus options).
- Review fatigue in general. Mention the morning queue, but don't turn it into the "hundredth diff" argument, which belongs in the seed-corn post.

## Research to do

- **Verify the 1999 rule** against *Extreme Programming Explained*, 1st edition: the exact wording of "40-hour week" and "never a second week of overtime".
- **Verify slack** against the 2nd edition (minor tasks that can be dropped).
- **Evidence of the "agents work while you sleep" pitch:** vendor marketing and engineering blogs that sell 24/7 agents or background agents as free capacity. A couple of real examples would make the post concrete.
- **Evidence of the human side:** anything on notification-driven after-hours work, "always on" culture, or the right to disconnect (France 2017, Australia 2024) as a parallel.
- **Shift handover research** (if that's the opening): handover as a known risk point in hospitals and process industries.
- **Lean:** overproduction and inventory are already sourced in "Mind the Plumbing"; reuse rather than re-research.

## Open questions for the author

- Is there a personal story: a morning facing a night's worth of agent output, or checking a run from your phone late at night?
- Does the post land on a rule, or on a question for teams ("what is your night shift for?")?
- Is "Overtime by Proxy" the title?
