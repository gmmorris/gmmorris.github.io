# Research notes: "Overtime by Proxy"

Scope and outline for a single, tightly scoped post. Not prose. This file lives in `_research/`, which Jekyll does not publish.
Related notes: `_research/judgement-is-the-seed-corn.md` (where the idea started as candidate angle 3) and `_research/growing-judgement.md`.

## Working thesis

> XP's first edition treated overtime as a symptom: the hours weren't the problem, the reason you needed them was. Agents that work through the night are overtime by proxy. They look like free capacity, but they hide the same problem, and the bill still lands on a person: the next morning.

## The idea in four moves

1. **The rule.** First edition XP: one week of overtime is fine, never two in a row. Overtime meant something was wrong with the plan, and the extra hours hid it rather than fixed it. (Energized Work in the second edition moved the focus to the person.)
2. **The proxy.** Agents don't get tired, so running them overnight and at weekends looks like free capacity. Nobody is working late, so the rule doesn't seem to apply.
3. **The symptom is the same.** Why do you need agents running all night? Usually because the plan holds more than the team can absorb. Running agents overnight avoids the scope conversation, just as overtime did. It also eats XP's *slack*: when every nice-to-have can be handed to an agent at 6pm, nothing ever gets dropped.
   - **The counterargument the post must answer:** "Slack is obsolete." Slack existed to leave room for unplanned work. If unplanned work can go to an agent, and you can spawn as many agents as the company can pay for in compute, why set a limit at all?
   - **The answer, which bridges to move 4:** the capacity that slack protected was never really the *typing*. It was the people. Agent capacity scales with compute; human attention doesn't. Every agent you add draws on the same fixed pool of people: to review what it made, to make the decisions it can't, and to unblock it when it gets stuck. Adding capacity anywhere other than the bottleneck doesn't add throughput (Goldratt, Theory of Constraints), and the bottleneck is human. So slack still matters; it has just moved. It now has to protect the people the agents depend on.
   - Also worth checking: in the 2nd edition, slack is partly about **keeping commitments credible** (plan some tasks you can drop, so you can always deliver what you promised). That purpose doesn't go away with agents either. **Verify against the book.**
4. **The bill comes back to a person.** "Overtime by proxy" in two senses: the agent works the hours, and a person pays for them. **This is the move to nail down.**
   - **The ratchet:** once overnight agent work is free, it stops being a bonus and becomes the baseline. Stakeholders plan around it. "The agents will have it done by morning" turns into a commitment someone else made on the team's behalf. (Parkinson's law in reverse: the work expands to fill the capacity.)
   - **The expectation that follows:** if agents are *expected* to work through the night, then people are expected to keep them working. Agents get blocked: a permission prompt, an ambiguous requirement, a failing environment, a decision they can't make. Someone has to unblock them, or the night's capacity is lost, and that loss is now a missed commitment rather than a missed bonus.
   - **So the human ends up on call for the agents.** Checking sessions from the phone at 11pm, unblocking a stuck run before bed, waking up to a notification. It arrives in small, unbilled, unrostered pieces, which makes it easier to ignore than real overtime.
   - **We've been here before:** when software moved to services running 24/7, it created on-call. On-call only became sustainable once it was made explicit: rotations, compensation, limits on how often people get paged, error budgets that slow feature work when reliability slips. 24/7 agents need the same treatment, or they create an on-call rota nobody agreed to.
   - **The morning bill:** what was built overnight lands as a review queue. That's Lean's inventory and overproduction ("Mind the Plumbing"), arriving all at once, while the author (the agent) has no memory of why it did what it did.
   - **Hence the limit:** you set a limit on agent work not because compute is scarce, but because the people the agents depend on are. The limit protects them from becoming the night shift's on-call.

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
- **On-call as precedent:** how the industry made 24/7 on-call sustainable. The Google SRE book's limits (from memory, **verify**: a cap on the share of time spent on operational work, and a target for how many incidents one on-call shift should handle), error budgets, and on-call compensation norms.
- **Theory of Constraints:** Goldratt, *The Goal*. Adding capacity at a non-bottleneck doesn't increase throughput. Find the cleanest wording.
- **Evidence of stakeholder expectations ratcheting:** anything on productivity gains being absorbed into higher expectations rather than shorter hours (e.g. surveys of AI adoption and workload). Optional but would strengthen move 4.
- **Evidence of the human side:** anything on notification-driven after-hours work, "always on" culture, or the right to disconnect (France 2017, Australia 2024) as a parallel.
- **Shift handover research** (if that's the opening): handover as a known risk point in hospitals and process industries.
- **Lean:** overproduction and inventory are already sourced in "Mind the Plumbing"; reuse rather than re-research.

## Open questions for the author

- Is there a personal story: a morning facing a night's worth of agent output, or checking a run from your phone late at night?
- Does the post land on a rule, or on a question for teams ("what is your night shift for?")?
- Is "Overtime by Proxy" the title?
