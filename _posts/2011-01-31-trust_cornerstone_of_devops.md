---
layout: post
title: Trust as the Cornerstone of DevOps Culture
tags: devops
categories:
- devops
---

{{ page.title }}
================

[Patrick Debois’ How to Bootstrap a DevOps Mentality
prezo](http://www.slideshare.net/jedi4ever/bootstrapping-a-devops-mentality-at-skillsmatter-by-patrick-debois)
- is so good, I can only wish that I’d have been there. Since, I can not
catch the next hop to a Euro DevOps meetup, nor execute time-travel a
follow-up blog post is the best I can do.

First, let me caveat with saying that I’m a software engineer, and come
from a history of Agile attempts (some successful, and some
not-so-much). I can’t help but feel like the current buzz around DevOps
is tilted towards the Ops functions. Perhaps this is due to the
well-deserved attention tools like Puppet and Chef are getting (and the
hype revolving around all-things cloud). Automation in the Ops space is
very much needed.

I completely agree with Patrick, DevOps is a cultural issue, and
subsequently a behaviorial one. Having spent many years working in
realtime, embedded software, I can assure you that the current
development-operations flux is no different than the current
software-hardware riff in the longer running product/widget space. And
yes, respect is the “correct” answer. However, changing culture in most
organizations with dev and ops shops is an unrealistic expectation.
Every organization regardless of a product or service focus, in widget
or web form, will be challenged with respect, responsibility, and
accountability issues - by the pure dynamic nature of culture. Again
yes, there are exceptions to every rule, and there are a few
organizations that can overcome culture issues, but they are the
minority (especially as the size/complexity of the organization
increases).

**Trust is paramount.**

I love this: trust = f(character,competence)

As both character and competency are fluid with changing teams, changes
in organizational structure, and projects themselves it is very
important that there is a way to ensure that the values can be made more
concrete, improving over time. How we do this is the million
\[insert\_currency\_here, !pesos\] question, for the DevOps community to
debate.

I’ll go ahead and assert that the pivot point (for balancing the
relationship between development and deployment) is testing. Testing is
the proof of character and competence, the only practice that can
provide concrete values to these variables. And, testing is something
that can be proven over time. Proof, is the precursor to truth (read
trust). Take safety-critical systems for example (e.g. an automated
medicine injection system)…ok, bad example…take for example a mission
critcal system like a stock transaction processing system. The
development and operational activities aren’t left to culture, or
behavior to ensure quality (or rate of deployability). These systems are
tested, automatically and otherwise, out the wazoo - including the
deployment operation. These tests provide the confidence/proof required
to create an organizational culture of trust - not member behavior which
is susceptible to too many influences.

**Trust is derived from proof.**

IMHO, bootstrapping a DevOps culture of trust is solely dependent on
testing. And thus, DevOps is indeed a technology problem - assuming that
testing must be automated as much as possible in order to be of
long-term value.

Even within the software engineering microcosm the same issues of trust
exist. Agile practices, as stated in my [favorite
book](http://pragprog.com/titles/pad/practices-of-an-agile-developer) on
the subject, push for respect in the form of humans and technology.
Source code management tools enable Agile practices like “commit early,
commit often” and continuous integration, which lead to transparency and
respect, and thus trust later. Without source control, trust would never
survive developer turnover and external technology influences or
organizational culture.

In order to build and grow DevOps cultures we need to be more
“inclusive” of software development culture and practices, and extend to
and accept the technology discussion. The technology solution needs to
go all the way to the front-end (requirements/stories) and include
automated quality assurance in the middle. If we don’t end-to-end trust
and collaboration will be a pipe dream.

------------------------------------------------------------------------

I’ll be
[speaking](http://www.maestrodev.com/events/devops-day-los-angeles) on
this subject at [DevOps
Day](http://www.socallinuxexpo.org/scale9x/special-events/devops-day-los-angeles)
at [SCALE9X](http://www.socallinuxexpo.org/scale9x/) if you’d like to
engage on the discussion. I’d love any feedback, comments, or WTFs.
