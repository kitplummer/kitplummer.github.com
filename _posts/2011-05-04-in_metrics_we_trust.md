---
layout: post
title: In Metrics We Trust
tags: devops
categories:
- devops
---

{{ page.title }}
================

![](http://www.rpi.edu/dept/acs/pcinfo/labview.jpg)

As I’ve stated in the past [Trust is the Cornerstone of DevOps
Culture](http://www.maestrodev.com/blogs/trust-as-the-cornerstone-of-devops-culture)
and I think we’re getting closer at the root apparatus for creating
trust. I do, now, believe that it is more than just QA, providing
assurance of functional and non-functional requirements. The problem,
that is becoming clearer to me, is the state of change (I know it is a
great oxymoron) that is always in play on both sides of the lifecycle
(dev and ops). Not only are requirements a moving target, but so is the
solution. Agile has taught us to treat the solution as a dynamic entity
that is reacquiring the end-state - based on requirements, technology,
and people. So, there’s no way QA (process and people) can keep up with
the lot, in an effective way that allows for continuous delivery, or
even “more” rapid delivery without some means for providing a feedback
loop.

That feedback loop is created by metrics. But, metrics that identify the
performance of the applications (UI, internal, external, asynchronous
processes, etc.) are well beyond just access and availability.
[Effective Code
Instrumentation](http://stackoverflow.com/questions/2345081/effective-code-instrumentation)
is really more than “live” tracking a block of code, or capturing log
files. Instrumentation also goes beyond failure cases. Metrics provided
by instrumentation need to look beyond just a single application, or a
single relationship (front-end to database query) and into the full
architecture - all tiers.

DevOps is here to help. By creating DevOps-minded environment for
Operations to work directly with Developers, early in the cycle (and
each cycle) there’s an opportunity to build better applications/services
that include the required instrumentation triggers. QA can be included
to define the appropriate test cases, and monitoring patterns that will
identify trends (especially those associated with changes to
infrastructure, business activities, and general load). Obviously, the
actual strategy for which metrics are best suited is part of the
problem. The Dev, QA, Operations triad is required to work the strategy
from the start, and to continuous evolve the strategy - learning from
all angles as the solution matures.

Did you know there’s actually an [open
standard](https://secure.wikimedia.org/wikipedia/en/wiki/Application_Response_Measurement)
for instrumenting code? Wonder if anybody actually uses it in their
Apache HTTP server runtimes.

I’m sure we’ll be hearing more about it at [Devopsdays 2011 - Mountain
View](http://devopsdays.org/events/2011-mountainview/)

Help us out - and vote on a t-shirt design for the event too:

[In Metrics We
Trust](http://devopsdays.uservoice.com/forums/113611-t-shirt-design-ideas-for-devopsdays-mountain-vie)
- could be a really cool t-shirt design. (I think this was actually
Patrick Debois’ idea. :))
