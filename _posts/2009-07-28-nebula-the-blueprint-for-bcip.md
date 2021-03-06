---
layout: post
title: NEBULA, The Blueprint for BCIP
---

{{ page.title }}
================

I’ve been buried with Sprint review preparation and a painful
introduction to DDS (thanks Mitre). Sorry for the gap.

Well, it looks like NASA has beat us to the architectural punch.
[NEBULA](http://nebula.nasa.gov/services) is proclaimed to be a
“self-service” computing platform, built out of Open Source pieces. Just
glancing at the system “box” diagram it is easy to see that they
envision the full-range of “hosting” options as we’ve drawn in our
preliminary sketches of BCIP. NEBULA includes EC-like virtual hosting,
as well as an app-hosting platform based on
[Django](http://www.djangoproject.com). Cool.

We obviously need to reach out to them to discuss the potential for
gleaming their discovery and decision matrices - in order to prevent
wasted energy researching.

There are a couple of things that don’t really align with our
“individuals first” thinking. NEBULA has integrated Trac, a python
based, project-centric platform that sits on top of Subversion. Where we
think a Github(like) addresses our problem-solver needs, but still
provides project capabilities like issue tracking and wikis. I do
understand the logic behind the Trac decisions though. Testing and
continuous integration should be provided to any project with the need.
It is a question I’m sure we’ll have to answer.

Hopefully, I’ll have more insight in the near future - and some good
fortune in attempting to reuse NASA’s efforts.
