---
title: "System Up- & Downtime Calculations for SLAs"
subtitle: Talk is cheap, when it comes to uptime guarantees
slug: system-uptime-and-downtime-calculations-for-slas
publishdate: 2014-01-20T12:33:19+09:00
date: 2015-06-07T21:33:19+09:00
banner: /img/Cogley-Banner-Hashioki-1170x350-001-mono.JPG
images:
  - /img/Cogley-Post-Do-Not-Unplug-Sign-2.jpg
  - /img/Cogley-Banner-Hashioki-1170x350-001-mono.JPG
  - /img/rick-cogley-avatar-240x240.png
description: Calculating downtime and uptime with SLAs in mind, a post by Rick Cogley.
topics: [Technology, SysAdmin, Troubleshooting, Service]
tags: [uptime, downtime, availability, nines, marketing, maintenance, sla, risk]
draft: "false"
aliases:
  - /articles/2014/01/20/system-uptime-and-downtime-calculations-for-slas/
postsummary: Marketing speak, when it comes to system uptime or downtime, can be  misleading. Learn some basic relationships between your "nines" of downtime to be ready.
postsvg: icon-origami-fish
---

Marketing speak, when it comes to system uptime or downtime, can be  misleading. Learn some basic relationships between your "nines" of downtime to be ready.

<!--more-->

It's easy to believe slick marketing speak, when discussing system uptime, downtime or availability. System design for maximum business availability, and the skillful maintenance required therein, are complex and difficult topics.

Most businesses don't have unlimited budgets to put toward keeping systems available, so it's always a balance between your spend, difficulty of maintenance, and the business risk involved with downtime. It's case by case.

Indeed, if you are doing your job right as a sysadmin, keeping your systems up and running without incident, people think it must be easy _because_ there are no problems. You're only noticed when something goes wrong.

## What's the scoop on uptime and downtime?  

Uptime is, strictly speaking, the percentage a system is "running", and downtime is the inverse of that. However, the key thing to follow is "availability", which is a measurement of whether a system's target users can access and normally use a system.

A system can be "up" but unavailable, so when defining SLAs or "working agreements" with businesses, it is best to focus on availability guarantees and not just simple uptime.

But availability is a more complex calculation, so let me simplify to just talk about downtime and uptime.

### System Downtimes as Percentages & Durations

I put together the handy spreadsheet below, to show the number relationships between amounts of downtime. A few points to note about this sheet:

* I assume an average days per year of 365.25 accounting for leap years. Mins / month is pretty different if you calculate at 365 vs 365.25.
* I list "marketing" uptime as six nines, five nines, four nines and so on. Notice the marketing terms cover a range of downtime. For example, four nines is anywhere from 27 sec to just under 15 min / month. A user might not even notice 27 seconds, but 15 min will likely be noticed.
* The difference between six & five nines, 5 & 4, 4 & 3, 3 & 2, and 2 & 1 nines, is 10 times the downtime in each case. Six nines is 2.63 sec / month down, whereas five nines is 26.30 sec / month down.

<figure class="fit">
<iframe width='580px' height='480px' frameborder='1px' allowtransparency='true' scrolling='no' src='https://docs.google.com/spreadsheet/pub?key=0AoreQ_hTvc2XdGQxZURCdU9YTUJheVVwd1h5MGZhTUE&single=true&gid=0&range=A1%3AH24&output=html'></iframe>
<figcaption class="sans center"><em>Figure</em>: System Downtimes as Percentages and Durations</figcaption>
</figure>

I hope you can find some value in knowing these ranges and number relationships, when you are discussing system uptime. But the hard work of figuring out how to keep systems _available_ still has to be done, and in the most practical way possible.

{{< figure1 link="/img/Cogley-Post-Do-Not-Unplug-Sign.jpg" src="/img/Cogley-Post-Do-Not-Unplug-Sign-2.jpg" type="Photo" title="'Do Not Unplug' as an Availability Method, by Rick Cogley" class="" >}}

Then again, you _could_ just put a sign on it saying "don't unplug" like this one from my _hall of shame_. But I hope you don't.

{{% ack1 %}}
The banner photo is a photo of "hashioki" chopstick props that you balance your chopsticks on during a meal. I shot this at Roppongi Robataya. Original is [here](https://www.flickr.com/photos/rickcogley/2926475169).
{{% /ack1 %}}
