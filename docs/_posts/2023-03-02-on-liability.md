---
layout: post
title:  "On Liability"
date:   2013-03-02 21:55:16 -0700
categories: Zen
---

(inspired from a few conversations with my manager and few more folks in 1:1s)

It has been 5 months since I wrote the first one. So many things have happened - some still happening in production. I have experienced chaos in both work and life, and want to share a little bit of a retrospective. Feel free to discuss in this thread.

One day, I was trying to look for a pocket microscope bought months before, man it was a hell of a search and no veil. Why? Because there is just too much stuff in the room. I end up buying a new one as it is faster and guaranteed for the weekend use. Before purchases, I often imagine when and how to use the thing, but rarely about maintaining them. Slowly the stuff took a toll on everyday life - less space to use, useful things are hard to find and daily life was surrounded with junk. Not only that, sometimes ***a half-junk broke and there is an urge to fix it***.

Since the pandemic began, I've spent more time in my home than ever before, and this made the clutter unbearable. I resolved to gradually clean up my space, starting with my old clothes. I donated or threw away most of them, leaving only four drawers of items. Gradually I also cleared out my shelves, donated boxes of toys and other unused things, and reorganized my cabinets. I've also become more intentional about my purchases, with an emphasis on low maintenance. Although I still have much more to do, the delightfulness every time I can easily find something to wear or use is priceless.

Sounds familiar to day-to-day engineering, right? The more experience I have in engineering, the deeper I understand the cost of maintenance. First and foremost, **any code shipped to production is a liability**. Backward compatibility, system / infra upgrades, architecture complexity, tribal knowledge and gap between ownership transitions, shutoff controls, all of these are shipped along with the code, predating all the benefits the code can bring. If a feature / function shipped doesn’t have enough benefit to offset the liability, it is a net loss shipping it, with the added cost of sunsetting it and removing the dead code.

Of course, we should continue shipping things, but we must recognize that everything we ship immediately becomes a liability. This should be considered before shipping, before implementing, in the design phase, discuss and make conscious decisions about added liability to the system and team. That’s why there is a process in place for introducing new technologies, and a group of quality champions is working on design review processes.

How to help? Try to leave things a little bit better than when you found them. Clean up trash when you can. Help establish and spread best practices where possible. Let’s all do something about it.

Cheers!
