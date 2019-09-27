---
layout: post
title: SCA and JBI, Playing Nice?...
---

About the summer of ’06 I began to realize the need for my company to
adopt Open principles within its walls. It is a big company, with
distinctly different business units, and target objectives. The key
problem is duplicate effort. I won’t go into the problems of contractual
work (but a quick read of this
[post](http://www.blackholelogic.com/2007/7/4/open-on-the-4th-of-july))
will enlighten a bit. Anyway…a particular project was building out from
a handful of Open (Apache) projects. It made perfectly good sense to me,
that all work that was done, should be shared across the company. So,
with a lot of “pitching” I convince some leadership to fund the effort
as an internally-Open project. I’ve shown great success. Now, I’m trying
to figure out how to play in the Open Standards world to help drive some
feature/capability needs we have.

Getting my employer to understand this need has been troublesome. Part
of the problem is that there are a few parallel/similar projects that
are working towards proprietary solutions, including patents - in which
my employer believes an income source may exist. \[They couldn’t be more
wrong, and are quickly learning just how wrong.\] But, I’ve recently
received some funding to participate in the [JBI
2.0](http://jcp.org/en/jsr/detail?id=312) specification community.
Hopefully, the application will go through soon.

From the time I decided I should be in the JBI Expert Group I began to
realize some of the issues that lie ahead. The slow awakening of
[SCA](http://www.ibm.com/developerworks/library/specification/ws-sca/) -
and the impending riff between the two camps (SCA and JBI) began to
worry me a bit. What worries me even more is the ignorance that is
spreading FUD amongst the general technology community. Just this last
week we had some “sales” folks in from one of the SCA-camp leaders in.
As soon as I brought up that we were interested in JBI - I got the full
BS-line from one of the “sales engineers”. The only thing who could
really come up with was the SCA language independence bit…and that they
believe there’s more to life than Java. As soon as I mentioned that SCA
runtimes were all Java - he shut up. But, it is this blatant disregard
for logic that retards the true potential for SCA and JBI.

After a few discussions with different folks (from the user’s
perspective) it has become clear to me that there is/will be a need to
provide SCA deployment capabilities from a JBI-based implementation. The
division should be that SCA is a developer’s spec, and JBI is an
integrator’s spec. There are many posts out there discussing the
complementary nature - but, it just doesn’t seem to be making it to any
implementation. So, a colleague of mine has recently spun up a
“grassroots” effort to look at this [SCA on/in
JBI](http://www.jbizint.org/wiki/index.php?title=SCA) problem.

It is unfortunate that IBM and BEA are so unwilling to accept a spec
that they’ve been “dissin’” forever - and, thinking that theirs is the
right way. If you can arrive at the understand that SCA and JBI are
indeed complementary, then why can’t we all just get along? I’ve left
out many details in this story - to both protect the innocent, but also
to avoid a “details” flame war. Yes, there are things that both SCA and
JBI do. But, I think the fact that SCA lacks an integration mindset and
that JBI lacks language independence - promotes a future collaboration,
if nothing else. Never mind the other specifications and messaging
technologies (ala CORBA). FWIW, we also need to get past the notion of
an ESB, unless we can really fulfill the Enterprise bit.

So. Put the (SCA/JBI) politics aside. Rationalize service interfaces and
heterogeneous deployment environments. The business/fiduciary ROI will
follow. And, dead-weight companies will fall off the landscape.
