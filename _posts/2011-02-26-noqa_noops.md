---
layout: post
title: No QA and No Ops Needed - Yeh Right
tags: devops
categories:
- devops
---

{{ page.title }}
================

This is a great example of NoOps & NoQA.

<iframe title="YouTube video player" width="480" height="390" src="http://www.youtube.com/embed/UiInBOVHpO8" frameborder="0" allowfullscreen>
</iframe>

I can’t remember exactly how, but I was pointed to this (above)
[video](http://www.youtube.com/watch?v=UiInBOVHpO8) of [Dub
FX](http://dubfx.bandcamp.com) that just totally blew me away. I’m a fan
of anyone with exceptional talent…and after having watched it a couple
of times I began to envision the parallel between what he’s doing on the
street with what modern software devers are doing with webapps (the
dev-to-deploy) process. For both the awesome sound and metaphor to “NoQA
NoOps” I highly recommend taking the few minutes to [watch
him](http://www.youtube.com/watch?v=UiInBOVHpO8).

If you don’t get the same vision that I did, let me break it down real
quick. He records a single track (read feature development), then
immediately listens to it (read feature QA), then promtes the track loop
into his operational environment (live). He (by himself, fulfilling the
three cultures of dev, QA, and ops) does this a few times over,
continuously deploying new tracks to the song - in realtime.

Cage Rattling
=============

[Mike Gualtieri](http://www.forrester.com/rb/analyst/mike_gualtieri) has
written a couple great “cage rattling” posts, that have generated an
excellent dialog.

NoOps?
------

The first one, [I Don’t Want DevOps. I Want
NoOps.](http://blogs.forrester.com/mike_gualtieri/11-02-07-i_dont_want_devops_i_want_noops),
is a look at the desire/need for developers to be truly abstracted from
their target platforms - to include the need for deep understanding of
the hardware constraints.

Mike’s post also pushed on the aspect of deployment, suggesting that
cloud-based providers will proved the “Ops” needed, to ops teams who can
then pass through to developers. In saying this he’s obviously added a
touch of irony. Ops is still needed. Yesterday at DevOpsDay (at SCALE9x)
I heard [Christophe Louvion](http://www.linkedin.com/in/chrislouvion)
say explicitly that he gives his developers a credit card and the “go
ahead” to manage their own cloud resources. That’s great for “Dev”and is
a critical “Yes” required in the DevOps culture to empower developers to
gain performance efficiencies and a better understanding of Ops, as long
as they work with Ops to utilize cloud resources in the best way that
will optimize the deliver/deployment process in the greater release
function.

I’m a huge fan of [Heroku](http://www.heroku.com) - especially how it
enables me to quickly deploy, within my existing software engineering
workflow by simply ’git push’ing to Heroku’s remote repo that represents
my target environment. I’m already committing my to my local (in-work
branches) repo, pushing to remote branches and trunk/mainline. It really
is nothing to push my “prod” branch to Heroku - simplicity. I’m doing
something very similar with this blog, using Github’s
[Pages](http://pages.github.com/) (I use
[Jekyll](https://github.com/mojombo/jekyll) - a cool static site
generator).

### NoOps for the “One-Liners”

Ok, here’s the reality. This flow makes great sense for my simple (in
the sense of both functional and non-functional/operational
requirements), single dever, self-QA’d, environment. This flow might
make sense for “hot” app dev-to-production for large-scale
infrastructures, where the app will have a short life expectancy and
won’t change much. For anything more complex, or that is being produced
and managed by a multi-person, multi-organizational environment, forget
it. Sure, you could use SCM and a binary repo to manage the steps and
promotions - but that will be a struggle where there is a “wares”
hierarchy with transitive dependencies and version releases along the
way. Note, I’m not trying to imply that the simple use case is any less
professional, this is just the difference between manufacturing a
skateboard and a car.

NoQA?
-----

Mike continues in another post [Want Better Quality? Fire Your QA
Team.](http://blogs.forrester.com/mike_gualtieri/11-02-17-want_better_quality_fire_your_qa_team),
where here acknowledges a client’s of his identification that getting
rid of their QA team actually resulted in higher quality software. Mike
notes the reason that it worked was because “Dev” is required to take
responsibility for the quality of the “deliverable” and not rely on QA
as a crutch. Makes perfect sense, and I’ve seen the same things in many
different types of organizations and products.

### Testing is…Well, it is Hard!

There are problems with pushing the responsibility for testing forward.
Testing is a skill. And the greater the complexity of the
product/project, the more complex the testing environment gets. Most
developers think testing is an impedance - not discounting it’s
importance - just identifying that testing can break creative progress.
Even though I have fully swallowed the value of \*DD (specifically
[BDD](http://behaviour-driven.org/) - it is very easy to end up with a
brittle test harness. This is even more of an issue where there are
multiple customers - each injecting unique requirements.

[Continuous
integration](http://martinfowler.com/articles/continuousIntegration.html)
isn’t enough anymore; functional testing isn’t enough; measuring and
monitoring isn’t enough. Truth is always changing. Wether it is a
changing customer requirement, or a version change on an internal
service, or a turn-over in a key team role, the proof that is quality
assurance is a moving target - a true byproduct of the need for agility.

We do need to make QA a shared responsibility across the DevOps culture,
and grow the skills that will allow for realistic accountability. But,
at the end of the day, we can’t short-change the complexity and
importance of focusing on Quality Assurance tasks.

A Couple of Closing Thoughts
============================

To Ops: give devers and QA testing environment that mirror upper-level
staging and production environments.

To Devers: ask for help, but do yourself a favor and dig a little and be
prepared to offer some help too. Never demand.

To QA: spread your knowledge of requirements, processes and tools to Dev
and Ops, and make an effort to get a deeper understanding of the overall
methodologies and practices.
