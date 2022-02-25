---
layout: post
title:  "Remote isn't Distributed"
date: 2022-01-26 00:00:00
categories: [Communication]
tags: [distributed,remote]
icon: seedling
description: ""
image: "/images/banners/remote-distributed.png"
banner-img: "/images/banners/remote-distributed.png"
image-desc: "Fairland's juvenile artist"
image-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14783922702/"
---

Two years ago our entire industry, and to a certain extent most office-based industries, was thrown into a new remote-first reality by a global pandemic.
This was particularly interesting for me as, unlike most of my friends and my family who found themselves forced into an unfamiliar work envirnment, I did not. For me, this was already familiar ground as six months earlier in late 2019, I had intentionally chosen to go remote by joining [Elastic](https://www.elastic.co/), which has operated as a remote-first team since its inception.

My interest in remote work began as a team lead at [Unruly](https://medium.com/unruly-engineering), where my team and I had been [trying to introduce remote work and were finding it hard](https://unruly.co/blog/article/2018/10/03/inside-prodev-unrulys-software-engineer-ina-tsetsova-on-remote-working-open-sources-and-stuffed-toys/). Actually, to be more accurate, we were failing miserably at it. We couldn't figure out how to balance remote work with the heavy realiance we had developed on in-person collaboration following years as practitioners of _Extreme Programming_ which utilises _pair programming_, _agile boards_, and co-located _osmotic communication_.

With an interest in addressing this gap in my competency, I decided to join Elastic, as I wanted to learn how an engineering team as large as theirs was able to scale and operate in a remote-first fashion.

What I've learned from my time at Elastic has been that _remote ≠ distributed_, and that doing so well requires you to learn to collaborate asynchronously. This is hard and, as I have learned from discussing this topic with friends and colleagues, is not well understood, which I believe is related to why many of them have struggled to make their own teams shift to remote a success.

# Remote ≠ Distributed

We tend to talk about engineers who work on _Distributed Systems_ with a certain degree of reverence. Mostly, this is because the term refers to such a wide range of different, often unrelated, problems that I doubt any person could ever acurately say they are _experts_ in the field. But, additionally, this is because distributed systems are made hard by the fact that the cost of coordination is high, if it is even possible at all.

This is as true for human systems as it is for software systems. This is why remote collaboration, as a subset of a distributed human system, is harder than co-located collaboartion; and as we have learned over the years, software engineering is an exercise in human collaboration more than anything else.
It's a team effort, and if we were to compare the challenges that make collaboration hard for a _co-located_ team with those afflicting teammates on a _remote_ or _distributed_ team, we would find that there is as much of a gap between _co-located_ and _remote_ as there is between _remote_ and _distributed_.

The way I've described this gap, which is only helpful if you're as much a movie geek as I am, is that a _co-located_ team is to a _remote_ team as the team on _Apollo 11_ is to the team in _Inception_; but a _distributed_ team is more like the team in _Tenet_.

![Co-Located is to Remote as Remote is to Distributed](/images/2022/02/colocated-remote-distributed.png)

OK, I'm exagerating, <a href="#footnote">_distributed_ teams don't have to, _spoiler-alert_, collaborate across the plains of an inverted time dimension<i class="fas fa-asterisk"></i></a>, but unlike most of the _remote_ teams formed by the digital transformation of the global pandemic, they _do_ have to collaborate in an environment where their teammates are _out-of-sync_ with each other. This is where an _Intentionally Asynchronous_ culture, where asychronous communication is not only encouraged but enforced, is demostrably impacatful.

Being _globally distributed_ means that any role that _can_ be distibuted, should be, as it enables the organisation to maximise its diversity and its ability to hire the best person for the job, no matter their location. Elastic, is globally distributed by [design and intention](https://www.elastic.co/about/distributed). This means that however we collaborate, it has to enable each and every role in the company to operate no matter the teammate's chosen timezone. Ideally not an inverted time dimension, but for the right candidate, we'd make it work 😉.

![Remote and Distributed by timezone spread](/images/2022/02/remote-distributed.png)

## Distributed by Design

I'd like to address that by sharing what I have learned from over two years of work at Elastic in a three part series:<br/>

[Part I: Intentionally Asynchronous]({% post_url _drafts/2022-01-27-intentionally-asynchronous %}) covers some practical practices that Elastic has adopted in order to successfully scale as a distributed company.<br/>
[Part II: A Chain of Archived Context]({% post_url _drafts/2022-01-28-a-chain-of-archived-context %}) explores a couple of real world examples where, in my opinion, asynchronous communication improves on in-peson collaboration by empowering team to archive their communications and link these archives to the _source of truth_, which enables teams to retain context across generations.<br/>
[Part III: Managing Distributed Teams]({% post_url _drafts/2022-01-29-managing-distributed-teams %}) covers some of the things I've learned from managing teams in a distributed setting. These are very subjective and anecdotal, but I believe they are also worth sharing.

<ol class="footnote" id="footnote">
    <li><i class="fas fa-asterisk"></i> Though they **are** better placed to do so, thanks to their archived communications, and we'll get to that in [Part II: A Chain of Archived Context](#part-ii-a-chain-of-archived-context).</li>
</ol>