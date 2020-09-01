---
layout: post
title:  "Paterns"
categories: [Organisational-Patterns]
tags: []
icon: seedling
description: ""

---

{%- capture night_as_primary_url -%}
  {% post_url 2019-02-13-a-night-as-primary-at-unruly %}
{%- endcapture -%}

{%- capture secret_sauce_to_an_effective_team_url -%}
  {% post_url 2018-07-28-the-secret-sauce-to-an-effective-team %}
{%- endcapture -%}

When humans band together in pursuit of a shared goal they enjoy an endless range of _organisational patterns_ to coalesce around. All patterns have their advantages, disadvantages, and limitations, and we often find that the very act of chosing one of them over the others, enourages dogmatic preferences amongst their followers, which means your chosen pattern often dictates, or at least influences, the organisation's culture.

Discussing this topic with colleagues, I'll often hear the prespective that "in the tech industry we do things _this_ way" or "_that_ way" and that we do so for _this_ reason, or _that_ reason. In truth though, it has been my experience that even if two organisations seem to do things the same _way_ in practice they can be miles apart, and attributing reasoning to these choices, such as their choice of _organistional governance_, requires a degree of familiarity with the individuals involved that we rarely attain without actually spending a substantial amount of time within that organisation. In fact, if we narrow our analysis of an organisation to their choice of _organistional governance_ (the **way** in _this way_), I don't believe we'll learn as much about the pattern as we instinctively think we will. Additionally, I'd say that even if a certain pattern _was_ successful for said organisation, that provides me with little assurance that said pattern would be succesful for mine. I believe that to understand why a specific pattern works succesfully within a specific organisation, is to understand more about the people applying it, than about the pattern itself.

In this blog post I'll delve into an analysis of two _organisational patterns_ applied within two different _organisation_ to a measurable degree of success and do my best to express how these _organizations_ succeeded at making these _patters_ work for them. 

# Patterns

I'm far from an expert in _Systems of Governance_, so to make sure we're all on the same page, allow me to clarify what I mean by the term _organisational patterns_. By _pattern_ I'm referring to end result of taking the norms enforced around methods of communication, collaboration, and boundery setting (or lack there of) by a specific group of individuals and generalising them into a reusable set of working agreements which can be applied more broadly by other groups of individuals within their own organisation.<br/>
Another term you might hear me use is _organisational governance_, which traditionally means the rules and processes by which an organisation is directed and controlled, but in the context of this article I would urge you to try and think of as describing the _result_ of applying such an _organisational patterns_ to an organisation.

The emergance of _organisational patterns_ is usually inpired by the case story, successful or otherwise, of an existing organisation. Most often, these case studies are success stories, in which the organisations' success is attributed to their choice of _organistional governance_, though interestingly, at times it can also be an organisation's failure story which goes on to inspire the birth of a new _pattern_ <i class="fas fa-asterisk"></i>. Either way, we see potential pitfalls in basing our choice of an _organisational pattern_ on a case study from the past. Success stories are prone to _survivorship bias_ <i class="fas fa-asterisk"></i><i class="fas fa-asterisk"></i>, and learning from stories of failure is prone to a variety of biases that might convince us that our story will be different. But, that said, I believe that as long as we keep in mind that we're going to have to do the leg work ourselves rather than blindly follow the _pattern_ as implemented by these origin stories, then learning from the experience of those that came before us is extremly valuable.

<small class="footnote"><i class="fas fa-asterisk"></i>Ironically, the greater the failure, the likelier the birth of a pattern, as it's only the better publicised failures you're likely to hear about, and subsequently choose as a source of inspiration. An interesting example of this would be the _Holacracy pattern_, which has been applied by organisations such as [Google](https://qz.com/work/1397516/is-holacracy-the-future-of-work-or-a-management-cult/) and [Extinction Rebellion](https://www.youtube.com/watch?v=tS3kNkq64d8), despite having either been abandoned in [part](https://www.workforce.com/news/qa-with-john-bunch-holacracy-helps-zappos-swing-from-job-ladder-to-job-jungle-gym) or in [full](https://blog.medium.com/management-and-organization-at-medium-2228cc9d93e9)) by the highest profile groups to have addopted it in the past.</small>

<small class="footnote"><i class="fas fa-asterisk"></i><i class="fas fa-asterisk"></i>_Survivorship Bias_ happens when we attribute the survival of an individual (or a group of people, such as an organisation) to a certain defining attribute, despite having little evidence at hand to support such a claim to causation.</small>

## Two Extremes

Focusing in on the more radical options on the menu of _organisational patterns_, you would be hard pressed to find two patterns more diametrically opposed than the _Localised Extreme Programming team_, where collocated collaboration is demanded, and the _Globally Distributed team_ where physical and temporal freedom, and asynchronous communication are paramount. I can think of about a dozen different axis by which you could compare different patterns, but if we narrow our view to two aspects, the _synchronisation_ and the _collocation_ of a team, you can clearly see how these two _patterns_ represent seemingly contradictory paradigms to teamwork.

{% include posts/chart-two-extremes.html %}

A _Localised Extreme Programming team_ practices the [_Extreme Programming_](http://www.extremeprogramming.org/) (XP) agile process by co-locating all of the individuals involved in building a product. The software developers, product owners, managers, sales, marketing, bunsiness development, and, ideally, customer, are all based in the same physical working environment. They all participate in regular face-to-face meeting which facilitate their communication, prioritisation, and learning activities, and they do so by enforcing expectation around their colleagues' physical location and working hours. Team alignment is mostly achieved through synchronous means, such as [physical boards]({{ night_as_primary_url }}#red-cards-across-the-board), daily stand-up meetings and hand written story cards. To be clear, I am not suggesting all XP teams opperate in this manner <i class="fas fa-asterisk"></i>, but rather that an organisation operating in this manner is the _pattern_ under discussion.

On the other hand, a _Globally Distributed team_ approaches the process of product building by aligning individuals through asynchronous communication, such that they can each collaborate at the time and physical location of their choosing. This approach relies on every individual, no matter their role on the team, ensuring that they strike the right balance between effective communication with their colleagues and scaling the distributed nature of the team. Aligning the different individuals on priorities, development and operations practices happens asynchronously using distributed tools and non-ephemeral communication. Achieving this effectively means that every step of the team's collaborative process, be it prioritisation, development and supporting the product and its customers, must all handle the asynchronous nature of the team's communication effectively.

<small class="footnote"><i class="fas fa-asterisk"></i>In my research I have come across multiple Extreme Programming teams who are not collocated at all and have found ways of adapting the XP practices to a distributed environment. That, though, is a topic for another article.</small>

## Diametrically Opposed
Measured by the aspects of _synchronisation_ and _collocation_ it's easy to see how .these two patterns differ, but why would I refer to them as _diametrically opposed_? That term would suggest not only that they differ, but that they are actively opposed to each other. You might wonder, is that not an exageration?

Throughout my research into these two _patterns_ I discussed this topic with their practicionares across several different organisations. Interestingly, I encountered a repeating _oditty_ where simply describing the practices adopted by practitioners of any one of these patterns to practitioners of the other would result in a veriety of vehement responses. I describe this as an _oditty_ as asking these very same people to consider other, often equally uncommon, _patterns_ then they would almost exclusively respond with curioucity, and even a hunger, for ways in which to tweak and improve their own way of working. They seemed to thrive on new ideas and perspectives, but these two _patterns_ seemed to produce a deeply ingrained aversion to each other.

At one such organisation, where the _Localised XP team_ pattern is practiced, I was told that _"We should regularly reflect on our values and our practices to ensure they’re appropriate to our changing context."_, and yet when discussing the practices of the _Globally Distributed team_ they responded by exclaiming: _"it's a threat to my sense of self to do things so differently!"_.
I don't say this to suggest an internal contradiction, but rather to express that no matter how open these practiotioners are to reevaluating their current _organisational governance_, I would consistently find that these two _patterns_ present as so inherently contradictory that it would be challenging to find practitioners who would not express a clear preference for one and a complete rejection of the other.

This led me to the realization that the choice of an _organisation pattern_ doesn't solely influence how an organisation operates on the day to day. But rather, that the application of a certain _pattern_ can have a deep influence on the experience that members of the organisation have while operating it, and the further away from the mainstream a _pattern_ is, the deeper this influence. This _influence_ dictates the _organisational culture_ that evolves in the organisation and that _culture_ in turn dictates, or at the very least influences, the talent pool that an organisation can gain access to.

# An Unbalanced System
If you think of an organisation as a system, assigning roles to the different members of that system, 

## What is your secret?
I don't believe that there exists a universal secret to forming successful teams, as we would have found it by now. Nor do I believe that given a specific _organisational pattern_ there exists a secret which, when followed by all teams, will lead to success either. If we keep in mind that ever team is unique and that, [as we have discussed before]({{ secret_sauce_to_an_effective_team_url }}#achievement-unlocked), even the addition of one new person to a team results in a _unique new team_, I don't believe you will ever find a single seceret which you can apply uniformally to achieve success.

With that in mind, given the opportunity to ask a team what secret they attribute to their success at applying a certain _pattern_, can produce valuable lessons for any team looking to apply these patterns as well. This is said with the assumption that each team will have to do the leg work on their own to achieve buy-in, adoption and unltimately adaptation as needed.

Interestingly, or perhaps obviously, in both cases it would seem the secret to success is rooted in tackling the biggest source of tension introduced by the specific _organisational pattern_. Though there are many different _patterns_ to choose from, it does seem most of them are designed to reduce the tensions that make it harder to produce work. They often align with the status-quo when it comes to _organisational governance_, and rarely do they introduce practices that might be perceived as creating unnecessery interpersonal tension.

In the case of our _two extremes_ though, they both priortise practices which potentially, and perhaps even inherrently, encourage interpersonal tension. _Localised Extreme Programming teams_ enforce a collocation teammates which is inherent in XP practices. _Globally Distributed teams_ on the other hand, are challenged by a lack of face to face and timely communication which creates the exact opposite tension, but a tension none the less. In both cases these tensions could easily be avoided by adopting the status-quo, which is why addressing these tensions is likely the _secret to success_ most expressed by its practitioners.

## The Localised Extreme Programming Team
To understand the source of tension inherent in a _Localised Extreme Programming team_ you must understand Extreme Programming, and though I feel like introducing you to XP is out of scope for this article, I will try to convey my perception of it.

A former manager of mine, [Steve Hayes](https://www.youtube.com/watch?v=pvbw8dWVwR0), once told me that when [Kent Beck](https://www.kentbeck.com/) first named it Extreme Programming he was trying to be divisive and force the conversation about it. I found that ironic, at the time, as when I was first introduced to XP it was presented to me as _hippies, unicorns and puppy dogs_. In hindsight I now understand that this was most likely due to how the engineering department of an XP team appears from the outside, where instead of a room full of headphone-clad engineers silently solving complex engineering problems, the engineering department of an XP team looks like a group of friends trying to solve their problems by talking about them.

It isn't unusual for teams who practice pair programming to spend 8 hours day _talking_. In fact, it's encouraged. All work is performed in _pairs_, or on some teams in [_mobs_](https://www.youtube.com/watch?v=SHOVVnRB4h0) (where more than three people or more are invovled), whether it's writing code, making design changes or writing marketing strategy, everything is _paired on_. XP consists of many practices other than pairing, such as Test Driven Development, Continuous Integration and Delivery, all of whom represent the most _extreme_ approach to a certain software engineering practice. If you talk to its practitioners you'll find that, to them, this is precisely _Extreme Programming_'s selling point- that it enforces the most extreme version of practices that, they belive, enable them to produce their best possible work.

But the problem with all extremes is that, by their very nature, they defy the status-quo and for many people this introduces understandable challenges.

We touched on these challenges when we disucssed our [_Feedback & Cake_]({% post_url 2018-08-04-feedback-and-cake %}) and [_Pairing checklist_]({% post_url 2018-08-11-pairing-checklist %}) practices, but the bottom line is this: pairing is emotionally taxing, exasperates both intrinsic and extrinsic _power dynamics_ and enforces strict working hours and cohabitation.
These challenges are the primarily source of tension<i class="fas fa-asterisk"></i> inherent to _Localised Extreme Programming teams_, and based on my observations of teams practicing XP, addressing them appears to be a prerequisite to becoming a high performing XP team.

The daugnting thing is, though, that addressing these challenges is hard. Emotions are a difficult things to address, and it requires attention to and investment into things that aren't always highest on a team's list of priorities. That said, when I led a _Localised Extreme Programming_ team we decided that prioritising these priotising these things was worth it and we came up with a list of practices that we felt ...

<small class="footnote"><i class="fas fa-asterisk"></i>These challenges are also the reason why _Extreme Programming_ teams often suffer from a lack of diversity. That said though, this is not an inevitable consequence of XP, as teams who have made the effort of addressing these challenges have discovered. When I was a member of an XP team, despite sadly suffering from a lack of diversity in some aspects (primarily a lack of ethnic diversity), it was by far the most diverse team I have ever worked on (in terms of gender, age and experience diversity).</small>

## The Globally Distributed Team

The first pattern

# 

Sarah: When I see a people problem I'm like "bring it on bitch" 

books:
Lencioni
culture code
