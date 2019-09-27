---
layout: post
title: Grails and OSGi (Preface)...
---

Just teasing. Hehe.

No seriously, for whatever reason there are those few things that come
around (technically) every once and a while that just make me giddy. It
was embedded systems, then it QNX, then it was Integrity, then is was
ActiveMQ/ServiceMix, throw Ruby in there some where - and now it is OSGi
(again).

I have a couple of cool project spinning these days - and totally
divergent. One is in the “enterprisy” space and the other is in
pervasive devices/ubiquitous computing. The common denominator is OSGi,
and there’s no irony here. Unfortunately, I can’t talk at all about the
latter project - but the former probably can leak a few details here and
there. One of the things that is really interesting about this project
is that its current form is seriously broken. Not just broken
functionally, but from a developmental perspective too (code, compile,
test, deply, test, code, blah, blah). It is just too damn hard to build
in modularity where it is needed, and integrate external and internal
interfaces, while maintaining simplicity. The needs are not great, nor
complex. But, the implementation dwarfs the needs, and the complexity
went through the roof. And we are just now considering persistence.
Soooo.

Enter the need for an off-the-shelf framework. Grails? Yes, because we
are a predominantly customer-driven, and agile environment; the customer
prescribes Java. Grails affords us the potential support many different
external interfaces including ReST (default), WS/SOAP, and JMS.
Nevermind the beauty of GORM’s abstraction to Hibernate.

Behind Grails comes OSGi. Not beneath, or around - but behind. We need a
service infrastructure to house extensible algorithms. Sure we could go
the strange world of ESBs (and we do have the JBI expertise in house).
But, we don’t need that overhead. OSGi allows us to provide a *nice*
package around a simple API pushing the extensibility with absolute
modularity and scalability (with cool stuff like hot-deploy).

Both Grails and OSGi are well-blogged topics and I don’t intend to rave
and praise them. Over the next couple of days I’ll drop a bit more, in
detail, about how I’m going about integrating the too. I suppose I
should state that I have given zero thought to getting Grails OSGI
bundle-ized. That’s just not something at this point that I really want
to think about. But, is an interesting notion - and does make sense
because it would afford us a bit of independence from any one OSGi
framework. We are using Felix, really just because it is an Apache
project and it is a little less coupled to any major project like
Equinox is to Eclipse.

More to come…
