---
layout: post
title:  "Experiments As An Entity"
date: 2018-10-22 10:00:00 +0100
tags: trust continuous-improvement team-building
icon: seedling
description: "When team members fear change, elevate experiments to story card level"

image-desc: "Gifts To The Gods"
image: "/images/banners/teotihuacan.png"
image-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14768520815"
---



As I mentioned in a past post, one of the problems my team was strugling to solve was a tendandcy towards _debilitating concensus_. We would sometimes find ourselves debating an issues ad nauseam, finding it very hard to get to a point where we converge on a course of action.

An interesting aspect of this issue was that it didn't affect our substantial decisions, but rather our ancillary ones. For example, choosing a caching strategy for our auction result took an single meeting, but generating buy-in for a the use of a Functional Programming coding style took months of back-and-forth debate. Even though this was only true for some of our decisions, this was disruptive enough that we felt it was affecting our ability to deliver value to the company.

<small>This post is part of the series [The secret sauce to an effective team]({% post_url 2018-07-28-the-secret-sauce-to-an-effective-team %}) which describes the steps taken within my team at Unruly in order to facilitate the fostering of _psychological safety_ amongst members of the team.</small>

## Why Was It So Hard To Gain Concensus?

Consensus decision making is often thought of as a unanimous vote by the team for a single first choice. We always recognised that generating enough buy-in for such a vote on every single decision is impossible, but the team did seem to tend towards the difficulty of finding a compromise that all members felt they could support, even if it wasn't their first choice.

The main thing holding us back, in my opinion, was a lack of _constructive conflict_ in the team. This changed dramatically thanks to our [Feedback & Cake sessions]({% post_url 2018-08-04-feedback-and-cake %}), [Getting better at X sessions]({% post_url 2018-08-26-getting-better-at %}) and our adoption of the [Occupy hand signals]({% post_url 2018-09-29-occupy-hand-signals %}) which made it easier to conduct constructive debates; but even with all those changes, we would still sometimes find ourselves going in circles when trying to decide on a technical or organisational course of action.

As the team became more comfortable with conflict, we began to identify a pattern in these prolonged debates. In many cases, we would find one or two developers, different ones every time, who would block the proposed compromise. In most cases, this block would be expressed as _a concern_ rather than _an objection_ and we realisd this concern revealed an underlying lack of trust.

Specifically, the lack of trust could be described in the following manner: _developers couldn't trust their teammates to revisit a decision in the case where they might have changed their mind at a later point in time_.


## Elevating Experiments

Addressing this fear was actaully far easier, and more effective, than I would have expected.

We retired the word _decision_ and replaced it with the word _experiment_.

An _experiment_ differs from a decision in several ways:
1. **Experiments have a specific mandate.** We always define the goal of the experiment which clarifies what it is trying to achieve.
2. **Experiments are timeboxed.** We always assign an expiration date for the experiment after which we revisit the method defined by the experiment and unless consensus has been achieved, we revert back to our previous method or adopt a new experiment.
3. **Experiments have owners**. Unlike _working agreements_, which are decisions the team has commited to following as a group, _experiments_ are owned by an individual in the team who is responsible nudging the team whenever the experiment is forgotten and schedules the follow up when anexperiment expires.
4. **Experiments are elevated**. Again, unlike _working agreements_, we place our _experiment cards_ as an **In Progress** item on our _Agile Board_ <i class="fas fa-asterisk"></i>. Along side our _User Stories_ you might spot an _Experiment_ card and that card will stay in the column until its expiration at which point it moves to **Review**.

By placing our **Experiment** cards along side our _User Stories_ we have elevated these experiments from a mere momentary decisions to an on-going evolving process. Their constant visibility demands our full attention, and the transitory nature of story cards is projected onto the _experiment_, reducing the concern that developers might have of decisions being set-in-stone and unchangable.

<small><i class="fas fa-asterisk"></i> The _Agile Board_ is where the team maintains the lifecycle of our *User Story* cards, *Technical Development* cards and *Research* cards. These cards are moved, like on a Kanban Board, through this lifecycle going from _Backlog_ to _In Progress_ to _Review_ and finally to _Done_.</small>


## The Slow Decline Of Experiment Cards

It wasn't even six months after introducing _experiment cards_ that I noticed two changes taking place in parallel.

The first was a slow decline in _expriments_. Less experiment cards were appearing on the board.

The second was a rise in off the cuff suggestions that the team _"experiment by doing X"_ to which people would simply nod in agreement and accept the suggestion without arguing. The team seemed to have not only become more comfortable trying ideas that their instinct labeled as _possible_, but also comfortable with these ideas being applied without the formality of an _experiment card_. To me this signaled a great improvment at trust within the team.

All in all I feel the _experiment cards_ proved to be a very effective and easy to implement tool which I intend on utilising in the future even when there are no underlying trust issues.
