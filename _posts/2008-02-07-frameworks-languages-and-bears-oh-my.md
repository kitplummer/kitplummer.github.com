---
layout: post
title: Frameworks, Languages and Bears Oh My!
---

The quagmire that is the world of software frameworks is growing on a
(almost) daily basis. And each language has its own pile of options.
Java, Python, Ruby, PHP (Smalltalk, Erlang, Perl, Haskell) and the like
all seem to have a play. I don’t want to waste anyone’s time … this post
is not a quantitative review, just some anecdotal commentary.

At the genesis of the rVooz project we were a little quick out the chute
and started in a direction that was more familiar to our “enterprisey”
skills. It didn’t take long to realize that we’d rushed in without
properly considering all of the requirements (at least the one’s we
knew).

Modularity desires led us in to the realm of OSGi - and we were really
comfortable moving in that direction due to our familiarity with Java,
Maven, and Eclipse. Unfortunately, a desire to architect around REST
interfaces (implying HTTP services) conflicted with the modularity from
a couple of fronts. First, thinking services when were building a
server. Second, thinking modules when we really wanted scalability -
both horizontally and vertically.

The architectural forces were shifting on us, and we needed to jump ship
on our framework choice fast. Thanks to this
[gem](http://video.google.com/videoplay?docid=6297126166376226181&amp;q=nasa+framework&amp;total=11&amp;start=0&amp;num=10&amp;so=0&amp;type=search&amp;plindex=0)
we decided to follow suit and construct a matrix that led us, obviously,
to the same conclusion. Ruby and Rails has been an interesting step, a
smart move for sure. We’re also playing with \<a
[Ramaze](http://www.ramaze.net) to get a feel for what else is available
in the Ruby landscape. It is very nice too.

The things we’ve been able to accomplish in a very short time with a few
developers are pretty amazing. However, it’s much more than just looking
at a language, and a subsequent framework. Your architectural ambitions
(Internet scale Vs. a few desktop application Vs. a personal blog) are
very important. Your project specific requirements are equally important
(i.e. our need for geographic data and processing support). Make sure
you weight the most important aspects as appropriate - to help provide
separation between like frameworks.

A couple more hints. I would also recommend that you place less of a
burden on the language you are currently comfortable with. It is much
better to think “the right tool for the right job” than busting out the
ole hammer - even when there’s the potential of an immediate learning
curve. Take a look at the community around both the framework and
language. Don’t get caught up in the “hip” factor either - make sure you
can really see the culture for what it is. If it is a commercial
offering ensure that you understand the company (and its life
expectancy). If it is an Open Source project spend some time in the
trenches chatting in IRC. Try and find out the formality of the
products/projects testing and release cycle and get a feel for the
objectively and drive that exists. Lastly, don’t ever be afraid to admit
a mistake or fear course correction. I could quite possibly mean
impending doom.
