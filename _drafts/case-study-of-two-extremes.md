---
layout: post
title:  "A Case Study of Two Extremes"
date: 2022-3-10 00:00:00
categories: [Organisational-Patterns]
tags: []
icon: seedling
description: ""
image-desc: "Women of Faial"
image: "/images/banners/women_of_faial.png"
image-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14596746138"
---

{%- capture night_as_primary_url -%}
  {% post_url 2019-02-13-a-night-as-primary-at-unruly %}
{%- endcapture -%}

{%- capture secret_sauce_to_an_effective_team_url -%}
  {% post_url 2018-07-28-the-secret-sauce-to-an-effective-team %}
{%- endcapture -%}

{%- capture remote_isnt_distributed -%}
  {% post_url 2022-02-20-remote-isnt-distributed %}
{%- endcapture -%}

{%- capture intentionally_asynchronous -%}
  {% post_url 2022-02-21-intentionally-asynchronous %}
{%- endcapture -%}

This essay has been sitting in my drafts for almost two years. Ultimately, it wasn't some new found clarity that got me to finish this narrative, but rather {% include footnotes/footnote_link.html content="a twitter flame war" count=1 %}. I keep telling my girlfriend Twitter will comes in handy one day.

When I [joined Unruly in 2016]({{ secret_sauce_to_an_effective_team_url }}#achievement-unlocked) I did so intentionally out of interest in learning how a successful [_Extreme Programming_](http://www.extremeprogramming.org/) (XP) engineering team operates. I had learned about XP over a decade prior, when an instructor at my coding bootcamp introduced us to the various forms of agile methodologies that existed at the time by describing XP as _"hippies, unicorns and puppy dogs"_. His impression of XP, which I believe was formed having never seen an actual XP team, was that of a noisy group of engineers lazilly hanging out trying to wrestle an engineering problem into submission by chatting about it instead of actually working. Unsuprisingly this impression couldn't have been further from the truth, though for the record, his description doesn't sound like a particulalry bad way to spend a day if you ask me.

When I subsequently left Unruly to join Elastic, I did so with a similar intention - I wanted to learn how [a successful remote engineering team operates]({{ remote_isnt_distributed }}). I approached this change cautiously, aware that I might have to temporarily leave my new found XP practices behind. Almost three years later, I find myself doubting whether I will ever see synchronous practices such as _pair programming_ ever adopted by a distributed company like Elastic.

In hindsight I severly underestimated how wide the gap between these two _organisational patterns_ would be.
In fact, with regards to Unruly's _Localised XP team_, and Elastics _Globally Distributed team_, I'd go as far as to describe  them as _diametrically opposed_, lets discuss why.

# Patterns

## An Abstract on Organisational Patterns

When humans band together in pursuit of some kind of shared goal they enjoy an endless range of _organisational patterns_ to coalesce around. 
These _patterns_ are designed to encourage certain dynamics between the group of humans, with the intention of achieving said goal. These dynamics are formed by injecting a set of _expectations_ into the group, and enforcing the adherence to these. Sometimes these expecations are very loose, such as an expectation to communicate with your manager on a regualr basis, and other times they are strict, such as the requirment to be in a certain place at a certain time every day.

As a result each pattern, and the dynamics it creates, come with their own set of subjective attributes. I find members of the group typically learn to associate these attributes directly with the chosen pattern, classifying them as the inherent _advantages_, _disadvantages_, _limitations_, or even _opportunities_ of the pattern. This tendency inevitably influences your organisation's culture, and I find that the further away a pattern is from the norm, the higher the likelihood that the act of choosing a certain pattern will enourage dogmatic preferences amongst its practitioners.

The point to the abstract description is that your chosen organisational pattern will often dictate, or at least influences, the organisation's culture, so choose wisely.

In this essaye we'll delve into an analysis of two such _organisational patterns_ as applied by two different _organisations_ with a measurable degree of success. I'll do my best to express how these _organisations_ succeeded at making these _patterns_ work for them, and what you might want to take into account if you choose to apply one of these patterns in your own company.

### Pattern Terms as I Use Them

I'm using the term _organisational patterns_ as a sort of umbrella term to describe the norms an organisation chooses to enforce internally around methods of communication, collaboration, and boundery setting (or lack there of). Specifically, in the context of engineering organisations, such a _pattern_ likely describes how the company plans, executes, and operates its products, covering key aspects such as the development methodology, the process of commercial decision making, and the means of communication employed by the different departments.

You might be familiar with a related term, _organisational governance_, which traditionally means the rules and processes by which an organisation is directed and controlled. It might help to think of the _patterns_ I'm referring to as the _generalisation_ of a certain ogranisation's chosen _governance_ in such a manner that you can then take it and apply it to other organizations.

When a company adopts a pattern they are in fact adopting a set of _organisational governance_ rules, and it is up to them to decide how strict, or loose, they are about enforcing these rules. As different patterns tackle different challenges, a company can adopt several patterns concurrently, {% include footnotes/footnote_link.html content="assuming the rules do not contradict each other" count=2 %}. For example, a company might choose to adopt the _Globaly Distributed Team_ pattern to tackle their communication and engineering practices, while also adopting the [_Spotify Model_](https://www.atlassian.com/agile/agile-at-scale/spotify) to tackle the challenges of _aligned autonomy_ across teams.

I use these terms in my own unique way, so I want to clarify what I mean when I use them.

Much could be said about how _organisational patterns_ are born, adopted, rejected and retired, but instead I think it's more interesting to discuss how, having chosen to adopt a _pattern_, I believe an organisation should _think_ about the choice they have made. We'll approach this by looking at how _Unruly_ and _Elastic_ have chosen to adopt two such patterns, calling out the dynamics that these choices have generated, and how these two companies chose to address these dynamics. As both of the companies have chosen 

## Two Extremes

Focusing in on the more radical options on the menu of _organisational patterns_, you would be hard-pressed to find two patterns more diametrically opposed than the _Localised Extreme Programming team_, where co-llocated collaboration is demanded, and the _Globally Distributed team_ where [physical and temporal freedom, and asynchronous communication are paramount]({{ intentionally_asynchronous }}). I can think of about a dozen different axis by which you could compare different patterns, but if we narrow our view to two aspects, the _synchronisation_ and the _collocation_ of a team, you can clearly see how these two _patterns_ represent seemingly contradictory paradigms with regards to teamwork.

{% include posts/chart-two-extremes.html %}

A _Localised Extreme Programming team_ practices the [_Extreme Programming_](http://www.extremeprogramming.org/) (XP) agile methodology by co-locating all of the individuals involved in building a product. The software developers, product owners, managers, sales, marketing, bunsiness development, and, ideally, customer, are all based in the same physical working environment. They all participate in regular face-to-face meeting which facilitate their communication, prioritisation, and learning activities, and they do so by enforcing expectation around their colleagues' physical location and working hours. Team alignment is mostly achieved through synchronous means, such as [physical boards]({{ night_as_primary_url }}#red-cards-across-the-board), daily stand-up meetings and hand written story cards. To be clear, I am not suggesting all XP teams {% include footnotes/footnote_link.html content="operate in this manner" count=3 %}, but rather that an organisation operating in this manner is the _pattern_ under discussion.

On the other hand, a _Globally Distributed team_ approaches the process of product building by aligning individuals through asynchronous communication, such that they can each collaborate at the time and physical location of their choosing. This approach relies on individuals adhering to a set of communication principales aimed at striking the right balance between effective collaboration and the need to scale the distributed nature of the team. Aligning the different individuals through prioritisation, development and operations practices, all happen asynchronously using distributed tools and non-ephemeral communication. Achieving balance is only possible when every step of the team's collaborative process, whether it's prioritisation, the development process, operationally supporting the product and its customers, must all handle the asynchronous nature of the team's communication.

# Diametrically Opposed
Measured by the aspects of _synchronisation_ and _collocation_ it's easy to see how these two patterns differ, but why would I refer to them as _diametrically opposed_? That term would suggest not only that they differ, but that they are actively opposed to each other. You might wonder, is that not an exageration?

Throughout my research for this essay I discussed this topic with practitioners of both patterns across several different organisations. Interestingly, I encountered a repeating _oditty_ where describing the practices involved in any one of these patterns to practitioners of the other would often result in what I can only describe as _vehement disaproval_ or dislike.
I describe this as an _oditty_ as these responses seemed out of character for the folks in question. When asking these very same people to consider other, often equally uncommon, patterns then they would almost exclusively respond with curiosity, and even a hunger for knowledge, in search of new ways to tweak and improve their own way of working. They seemed to thrive on new ideas and perspectives, but these two _patterns_ seemed to produce a deeply ingrained aversion to each other amongst their practitioners.

One such practitioner, an engineer on a _Localised XP team_ seemed very open to trying new ways of working, stating:
{% include quote.html content="We should regularly reflect on our values and our practices to ensure they’re appropriate to our changing context." %}

Yet when discussing the practices adopted by a _Globally Distributed team_ they exclaimed in disgust:
{% include quote.html content="it's a threat to my sense of self to do things so differently!" %}

I don't say this to suggest an internal contradiction, but rather to express that no matter how open these practiotioners are to reevaluating their current _organisational governance_, I would consistently find that these two _patterns_ present as so inherently contradictory that it would be challenging to find practitioners who would not express a clear preference for one and a rejection of the other.

This led me to the realization that the choice of an _organisation pattern_ doesn't solely influence how an organisation operates on the day to day. But additionally, that the application of a certain _pattern_ can have a deep influence on the experience that members of the organisation have while operating it, and the further away from the mainstream a _pattern_ is, the deeper this influence. This _influence_ dictates the _organisational culture_ that evolves in the organisation and that _culture_ in turn dictates, or at the very least influences, the talent pool that an organisation can gain access to.

# An Imbalanced System
If you think of an organisation as a system, then we can actually describe the _influence_ of a chosen _organisational pattern_ as a variety of _forces_ that create feedback loops inside of that system.

Specifically, if we take the case of our _Localised XP team_, practices such as _pair programming_ encourage constant communication between the team members. This feedback loop, purposfully intended to _dial up_ the feedback loop between the different team members, is introduced into the system to improve on the more traditional work environment where direct communication is often discouraged outside of perscribed _interuption points_ (such as the lunch break, team meetings and agile ceremonies such as Stand Up).

Introducing this _force_ influences far more than just how team members communicate about the work at hand. In an environment where teammates are encouraged, and arguably expected, to pair throughout the entire day, you find that these teammates are communicating far more, not only when compared to a traditional workplace, but even when compared to what they would consider the norm in their personal lives.

Furthermore, dialing up the communication in a team inevitably exacerbates inter-personal conflict, such as those created imbalanced power dynamics between individuals, a problem eloquently described by [Sarah Mei](https://twitter.com/sarahmei/status/990968833547497472) on a number of occasions.

This point is important, because it means that the _pattern_ itself, as chosen and implemented by the organisation itself, could be described as producing an _imbalanced system_. But, talking about _balance_ doesn't mean much without answering a fundamental question: _imbalanced_ relatively to _what_?

Does hiring a team of individuals who tend to _over communicate_ in their personal lives correct this imbalance? How about a team with a lesser degree of imbalanced power dynamics?

Arguably, this is how many organisations have gone about addressing these imbalances, whether explicitly or implicitly. If you have ever walked into a job interview at a _XP team_ just to find yourself staring at, seemingly, the same _white dude_ over and over again throughout the interview process, then you will likely know what I'm talking about. To be **absolutely clear**, I am not suggesting this problem is unique to _XP teams_, but my anecdotal experience suggests the power dynamics in paired environments often exacerbates this problem.

A failure to recognise this imbalanced system and address it through corrective feedback loops, will usually lead to a homogenous team, where _culture fit_ and other biases are baked into how the organisation operates, not out of mallice but soley out of the _organisational pattern's_ survival instinct. Unless the team filters out new _forces_ that could ineract badly with the _forces_ already introduced into the system by the _organisational pattern_, an organisation could easily collapse into _chaos_, and keeping that from happening becomes their priority, whether they're aware of it or not. 

# Mainstream Unbalanced
Taking stock of the problems we have discussed, we have recognised that practitioners of the two _patterns_ we have mentioned see each other as _extremes_ in relation to themselves. Additionally, we have observed that a chosen _pattern_ can create an _imbalanced system_ which has consequences for an _organisation_ practicing it.

But how do these problems relate to one another? Is there a relationship between these?
I believe so, as I think they are one and the same.

In my research I found that practitioners of both of these patterns would consistantly express the following feelings about their _organisation_:
1. Their chosen _pattern_ is _unique_ to them, or at least _uncommon_, and is definitely removed from the mainstream.
2. They have recognised the flaws in their chosen _pattern_ and have worked to address them.
3. They believe that the uniqueness of their _pattern_ and the steps thay have actively taken to address the _pattern's_ drawbacks, have made a considerable contribution to their perceived success.

Digging deeper I wanted to understand what I could learn about their perceived uniquness and how they chose to address the drawbacks. I persisted down this path to better understand their chosen _patterns_, but once I emerged from the other side, I came to the conclusion that there is a universal lesson to be learned from these two sucessful _patterns_.

Next lets look at some of the lessons we can learn from first hand experience addressing the imbalances introduces by these _patterns_, after which we will take a step back to gain a broader view and talk about these lessons from a _systems thinking_ perspective.

# Addressing the Imbalances
I don't believe that there exists a universal secret to forming successful teams, as we would have found it by now. Nor do I believe that given a specific _organisational pattern_ there exists a secret which, when followed by all teams, will lead to success either. If we keep in mind that every team is unique and that, [as we have discussed before]({{ secret_sauce_to_an_effective_team_url }}#achievement-unlocked), even the addition of one new person to a team results in the formation of a _unique new team_, I don't believe you will ever find a single seceret which you can apply uniformally to achieve success.

With that in mind, given the opportunity to ask a team what _their secret_ to applying a certain _pattern_ successfully actually _is_, can produce valuable lessons for other teams interested in addopting the _pattern_. This is said with the assumption that each team will have to do the leg work on their own to achieve buy-in, adoption and unltimately adaptation as needed.

## Unbalanced by Extreme Programming
Taking a closer look at the _Localised Extreme Programming patern_, I found quite a few teams who self-identify as high performing and consider their application of the _pattern_ as contributing to their relative success. 

As mentioned earlier, there are aspects to _Extreme Programming_ that introduce an imbalance into the _"system"_. Specifically, XP encourage more interpersonal tension between teammates than you might expect to experience in a more traditional work environment. To better understand the force behind this imbalance I think it will help to gain a basic understanding of XP, and though I feel like this might be out of scope for this article, I will try to convey my perception of it.

A former manager of mine, [Steve Hayes](https://www.youtube.com/watch?v=pvbw8dWVwR0), once told me that when [Kent Beck](https://www.kentbeck.com/) first named _Extreme Programming_ he was trying to be divisive and force the conversation about it. I found that ironic at the time, as when I was first introduced to XP it was presented to me as _"hippies, unicorns and puppy dogs"_ by an instructor at my programming bootcamp back in 2002.
In hindsight I think that instructor's perspective on XP was influenced by how an _XP engineering department_ can appear from the outside. Instead of the stereotypical room of headphone-clad engineers silently solving complex engineering problems, the engineering department of an XP team looks like a group of friends chatting away about their problems trying to talk them into submission.

It isn't unusual for teams who practice pair programming to spend 8 hours a day _talking_. In fact, it's encouraged. All work is performed in _pairs_, or on some teams in [_mobs_](https://www.youtube.com/watch?v=SHOVVnRB4h0) (where more than three people or more are invovled), be it writing code, making design changes or writing marketing strategy, everything is _paired on_. XP consists of many practices other than pairing, such as Test Driven Development, Continuous Integration and Delivery, all of whom represent the most _extreme_ approach to a certain software engineering practice. If you talk to its practitioners you'll find that, to them, this is precisely _Extreme Programming_'s selling point- that it enforces the most extreme version of practices that, they belive, enable them to produce their best possible work.

But the problem with all extremes is that, by their very nature, they defy the status-quo and for many people this introduces understandable challenges.

We touched on these challenges when we disucssed our [_Feedback & Cake_]({% post_url 2018-08-04-feedback-and-cake %}) and [_Pairing checklist_]({% post_url 2018-08-11-pairing-checklist %}) practices, but the bottom line is this: pairing is emotionally taxing, exasperates both intrinsic and extrinsic _power dynamics_ and enforces strict working hours and cohabitation.

These challenges are the {% include footnotes/footnote_link.html content="primary source of tension" count=4 %} inherent to _Localised Extreme Programming teams_, and based on my observations of teams practicing XP, addressing them appears to be a prerequisite to becoming a high performing XP team.

The daunting thing is, though, that addressing these challenges is hard. Emotions are a difficult things to address, and it requires attention to and investment into things that aren't always highest on a team's list of priorities. That said, when I led a _Localised Extreme Programming_ team we decided that prioritising these priotising these things was worth it and we came up with a [list of practices]({{ secret_sauce_to_an_effective_team_url }}) that we felt worked for us.

Discussing these challenges with teams from other organizations, I found a repeating patern where teams actively took measures to address these tensions by either reducing the scope of XP practices (for example, by introducing a mix of both paired and non-paired work) or by investing in creating _positive_ interpersonal conflict in order to better equip the teamates in handling the negative conflict.

My main takeaway was that in order to address the imbalance introuced by the _Localised XP team pattern_, active steps had to be taken to improve psychological safety and encourage positive conflict.

## Unbalanced by Distribution
Interestingly I've found it harder to find practitioners of the _Globally Distributed team_ who feel as strongly about attributing their distribution to their success as I had found when looking at _Localised XP teams_. There appears to be a stronger sense of _compromise_ amongst it's practitioners, where they acknowledge an inherent disadvantage in distribution, which they accept in exchange for the multitude of advantages inherent to remote work.

One striking exception I have found to this rule has been amongst the practitioners at Elastic, where I am now employed. This is no coincidence. I began researching this topic while as a team lead at Unruly, when I had been trying to introduce distributed work into my team and failed miserably. Discovering Elastic and how it operates was one of the key drivers of my continued interest in _organisational patterns_, and I subsequently joined to team to better understand how they make it work.

Elastic has operated as a _Globally Distributed team_ from its inception, with three of its co-founders finding each other remotely and founding their company across three different countries and time zones. Today the company numbers almost 2,000 individuals, including an engineering department of well over half of that workforce, spanning several dozen different countries. As a rule, their _organisational governance_ dictates that any role which _can_ be globally distibuted, should be, as it enabled the company to maximise its diversity and its ability to hire the best person for the job, no matter their location. 

As utopian as this vision might seem on paper though, this _pattern_ introduces a wide range of imbalances into the _system_, primarily the deficit in communication that teammates might experience when compared to a more traditional work environment. As teams are distributed, teammates are likely to find themselves reliant on colleagues with whom they share little to no overlapping work hours.

This distinction is the main source of tension which exists in _Globally Distributed team_ and is far less significant in a team which is merelly _remote_, where time zones will often somewhat overlap and synchronous communication is far easier.

How then does a _Globally Distributed team_ address the tension causing the imbalance in the system? An _Intentionally Asynchronous_ culture, where asychronous communication is not only encouraged, it's enforced.

### Asynchronous over Synchronous, Permanent over Ephemeral
Despite the industry's flourishing love afair with ephemeral, and mostly synchronous communication, such as Slack and Zoom, there's an inherent disadvantage to these forms of communication: they are lossy and rely on the recepient's availability either immediately (in video chat) or in the near future (instant messaging).

There is an inherent flaw in the assumption that the teammates who aren't present on Slack for the detailed conversation about technical implementation, competitive strategy, or quota attainment, will _catch up when they wake up_. This assumption is neither reliable, scalable or feasible in an organisation any larger than a handful of individuals.

There's an idea I heard voiced in Elastic that _"meeting are a bug, not a feature"_. This idea has informed the organisation's bias towards asynchronous communication wherever possible, which they say has enabled them to scale their distributed teams by several factors. Even though you will see teams in the organisation communicate using synchronous means on occasion, these meetings are predominantly used to _speed up_ the activity of updating an _asynchronous non-ephemeral_ mode of communication.

This is achieved by enforcing a culture where **decisions made on an ephemeral channels don’t count unless documented on a permanent channel**.
What this means is that although tools such as video calls and instant messaging are treated as indispensible to streamlining the organisation's communication, they are treated as impermanent and any decision made through them, must be documented by other means. To that end, a _Globally Distributed team_ has to elect a handful of tools which the team agrees upon as the _source of truth_. If the decision is documented in one of these tools, then hey count, otherwise, they might as well not have been made.

This might seem drastic, but the impact is highly effective.
In the case of Elastic, the company relies on email, Github and Google Docs as their _source of truth_, each of these covering a different segment of the company's archived knowledge. Synchronous tools of communication are useful, but unless they can be archived in one of these tools, their output is treated as _forgotten information that cannot be relied on_.

I expanded on this topic ealier this year on an interview for [The Sustain podcast](https://podcast.sustainoss.org/20) where we discussed this very subject in the context of sustainable Open Source development.

### Rebalancing through Generational Knowledge

You might be wondering if placing limitations on communication is the distributed equivalent to "only hiring over communicators" in the sense we discussed regarding the drawbacks to Extreme Programming. Does limitting decision making to non-ephemeral means of communication constitute capitulating to the drawbacks of a _Globally Distributed team_? 

One of my key takeaways from my time at Elastic has been that whererver my career takes me going forward I will be addopting this mode of communication. In my opinion, this approach addresses one of the few challenges I have identified at every other organisation I have worked for: the loss of generational knowledge over time.

Asynchronous and non-ephemeral comunication doesn't only mean _I write it today, you read it tomorrow_, it also means _...you can still read it next year_. How often have you wondered _why_ a decision was made years ago and had to go looking for an _old timer_ who was in the organisation at the time? This is far less of an issue when all deicisions every made in the organisation are well documented _by design_, because it was a basic requirment for the decision every being made.

Imagine being able to go from a single line of code to the original decision that neccesitated its writing in the first place. This is not a _dream_, it's a reality... if you create a culture which is _intentionally asynchronous_ and non-ephemeral.

# Thinking of Imbalanced Systems




Sarah: When I see a people problem I'm like "bring it on bitch" 

books:
Lencioni
culture code

{% capture footnotes %}
As much of a cesspool of disinformation and racism as Twitter tends to be, I still believe it provides a wonderful breeding ground for ideas and discourse. In this case, the flame war invovled [dogmatic practitioners](https://twitter.com/allenholub/status/1492009142671720450) of pair programming [denigrating practitioners of asynchronous practices](https://twitter.com/allenholub/status/1491168642586710016) such as pull requests, [and vice versus](https://twitter.com/mattrickard/status/1492548554426048514). Honestly, it was all kind of childish, but it [sparked some valuable discussion](https://twitter.com/tdpauw/status/1493234376217354242).

I've definitely seen companies where the organisational governance differed across departments, potentially meaning that the company might follow two contradictory patterns. This will likely create a new dynamic within the company with its own impact, such as an inability to collaborate across departments.

When the pandemic kicked off in 2020 I saw many companies who practice XP transition into a remote first reaelity. As a result, many are no longer co-llocated at all and have found ways of adapting their XP practices to a remote environment.

These challenges are also the reason why _Extreme Programming_ teams often suffer from a lack of diversity. That said though, this is not an inevitable consequence of XP, as teams who have made the effort of addressing these challenges have discovered. When I was a member of an XP team, despite sadly suffering from a lack of diversity in some aspects (primarily a lack of ethnic diversity), it was by far the most diverse team I have ever worked on (in terms of gender, age and life experience diversity).
{% endcapture %}

{% include footnotes/footnote.html notes=footnotes %}



# TBD might drop these entirely

### Pattern Terms as I Use Them

I'm using the term _organisational patterns_ as a sort of umbrella term to describe the norms an organisation chooses to enforce internally around methods of communication, collaboration, and boundery setting (or lack there of). Specifically, in the context of engineering organisations, such a _pattern_ likely describes how the company plans, executes, and operates its products, covering key aspects such as the development methodology, the process of commercial decision making, and the means of communication employed by the different departments.

You might be familiar with a related term, _organisational governance_, which traditionally means the rules and processes by which an organisation is directed and controlled. It might help to think of the _patterns_ I'm referring to as the _generalisation_ of a certain ogranisation's chosen _governance_ in such a manner that you can then take it and apply it to other organizations.

When a company adopts a pattern they are in fact adopting a set of _organisational governance_ rules, and it is up to them to decide how strict, or loose, they are about enforcing these rules. They can adopt several patterns concurrently, {% include footnotes/footnote_link.html content="assuming the rules do not contradict each other" count=2 %}, potentially creating a new pattern in the process.

I use these terms in my own unique way, so I want to clarify what I mean when I use them.
It's hard to say precisely when a certain company's working culture graduates into **_a pattern_**, but I think a good candidate would be the _Spotify model_. This model, which tackles the challenge of communities, first popularised by **Spotify** and then adopted by _god-knows-how-many_ start-ups, has been held up as a successful example for _scaling_ an agile process as a company grows. I've seen this model adopted both successfully and disasterously, leading to the predictable zealous advocates and their equally vehement antagonists, but there's little doubt that this model has graduated into an _organisational pattern_.

Much could be said about how _organisational patterns_ are born, adopted, rejected and retired, but instead I'd rather focus on how, given an adopted _pattern_, I think an organisation should _think_ about the choice they have made. I'll demonstrate this by picking two specific implementations of such _organisational patterns_ off of the smorgasbord of _patterns_ with which I've become deeply aquiainted with.
