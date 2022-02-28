---
layout: post
title:  "Remote isn't Distributed"
date: 2022-02-20 00:00:00
categories: [Team-Dynamics]
tags: [distributed,remote]
icon: seedling
description: ""
image: "/images/banners/remote-distributed.png"
banner-img: "/images/banners/remote-distributed.png"
image-desc: "Fairland's juvenile artist"
image-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14783922702/"
---

Two years ago our entire industry, and to a certain extent most office-based industries, was thrown into a new remote-first reality by a global pandemic.
This was particularly interesting for me as, unlike most of my friends and my family who found themselves forced into an unfamiliar work environment, I did not. For me, this was already familiar ground as six months earlier in late 2019, I had intentionally chosen to go remote by joining [Elastic](https://www.elastic.co/), which has operated as a remote-first team since its inception.

My interest in remote work began as a team lead at [Unruly](https://medium.com/unruly-engineering), where my team and I had been [trying to introduce remote work and were finding it hard](https://unruly.co/blog/article/2018/10/03/inside-prodev-unrulys-software-engineer-ina-tsetsova-on-remote-working-open-sources-and-stuffed-toys/).
To be more accurate, we were failing miserably at it.
Following years as practitioners of _Extreme Programming_, utilising _pair programming_, _agile boards_, and co-located _osmotic communication_, we couldn't figure out how to balance remote work with the heavy reliance we had developed on in-person collaboration.

With an interest in addressing this gap in my competency, I decided to join Elastic, as I wanted to learn how an engineering team as large as theirs was able to scale and operate in a remote-first fashion.

What I've learned from my time at Elastic has been that _remote ≠ distributed_, and that doing so well requires you to learn to collaborate asynchronously. This is hard and, discussing this topic with friends and colleagues, I have come to recognise as not well understood. This is, I believe, why many of them have struggled to make their teams's shift to remote a success.

# Remote ≠ Distributed

We tend to talk about engineers who work on _Distributed Systems_ with a certain degree of reverence. Mostly, this is because distributed systems tend to make problems harder to solve due to the high cost of coordination throughout the constituent parts of the system.

This is as true for human systems as it is for software systems, which is why remote collaboration, a form of a _distributed human system_, is harder than co-located collaboartion; and as we have learned over the years, software engineering is an exercise in human collaboration more than anything else.
It's a team effort, and if we were to compare those challenges that make _co-located_ collaboration hard with those afflicting _remote_ and _distributed_ team, we would find that the gap between _remote_ and _distributed_ is as wide as the one between _co-located_ and _remote_.

I nice simile for this gap, which might be less helpful if you're less of a nerd than I am, is that a _co-located_ team is to a _remote_ team as the team on _Apollo 11_ is to the team in _Inception_; but a _distributed_ team is more like the team in _Tenet_.

![Co-Located is to Remote as Remote is to Distributed](/images/2022/02/colocated-remote-distributed.png)

I'm exaggerating, obviously, as _distributed_ teams don't have to, **spoiler-alert**, {% include footnotes/footnote_link.html content="collaborate across the plains of an inverted time dimension" count=1 %}. That said, unlike most of the _remote_ teams formed by the digital transformation of the global pandemic, they _do_ have to collaborate in an environment where their teammates are _out-of-sync_ with each other. This is where an _Intentionally Asynchronous_ culture where asynchronous communication is not only encouraged, but enforced, is demonstrably impactful.

![Remote and Distributed by timezone spread](/images/2022/02/remote-distributed.png)

Being _globally distributed_ means that any role that _can_ be distributed, should be, as it enables the organisation to maximise its diversity and its ability to hire the best person for the job, no matter their location. Elastic, is globally distributed by [design and intention](https://www.elastic.co/about/distributed). This means that however we collaborate, it has to enable every role in the company to operate no matter the teammate's chosen timezone. Ideally not an inverted time dimension, but for the right candidate, we'd make it work 😉.

## Distributed by Design

I mentioned above that the ideas of a _globally distributed_ team and being _intentionally asynchronous_ aren't well understood, and I'd like to address that by sharing what I have learned over the past two and a half years of work at Elastic, in a three-part essay:<br/>

[Part I: Intentionally Asynchronous]({% post_url 2022-02-21-intentionally-asynchronous %}) covers some practical practices that Elastic has adopted to successfully scale as a distributed company.

[Part II: A Chain of Archived Context]({% post_url 2022-02-22-a-chain-of-archived-context %}) explores a couple of real-world examples where, in my opinion, asynchronous communication improves on in-person collaboration by empowering teams to archive their communications and link these archives to the _source of truth_, which enables teams to retain context across generations.

[Part III: Managing Distributed Teams]({% post_url 2022-02-23-managing-distributed-teams %}) covers some of the things I've learned from managing teams in a distributed setting. These are very subjective and anecdotal, but I believe they are also worth sharing.

<ol class="footnote" id="footnote">
    <li><i class="fas fa-asterisk"></i> Though they **are** better placed to do so, thanks to their archived communications, and we'll get to that in <a href="{% post_url 2022-02-22-a-chain-of-archived-context %}">Part II: A Chain of Archived Context</a>.</li>
</ol>