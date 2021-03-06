---
layout: post
title: Thinking Rich Server-Side with OSGi...
---

I’ve been toying with OSGi for the past few weeks, in an attempt to see
if it is a good starting point for a project I’m working on. Let me just
cut to it - OSGi is much more than just a good starting point. The
framework is very ready and capable of meeting my technical
requirements.

The part that I’m missing is how OSGi can fit in to my software
engineering process to include Test-Driven Design (TDD) and Continuous
Integration. I think the latter is a bit easier to conceptualize. But,
I’m just now learning that TDD can be accomplished by combining Spring
Framework with OSGi (see
[spring-osgi](http://www.springframework.org/osgi) for more info).

I just want to make a couple of points regarding my learning process.

Starting with a Google search of OSGi will not lead anyone to any useful
OSGi trailhead. You’ll find the OSGi implementations which is useful -
but, nothing really telling you what to do next.

I would highly suggest starting
[here](http://www.eclipsecon.org/2007/index.php?page=sub/&id=3632) and
then roll back to
[this](http://www2.osgi.org/wiki/uploads/Conference/OSGiBestPractices.pdf)

If you can understand why TDD is so important to me, you’ll surely
appreciate the SpringOSGi stuff from EclipseCon2007.

Keep in mind that I’ve no desire to rationalize the differences between
implementations, or a need to consider embedded/constrained deployments.
My genesis is a need for modular and dynamic service delivery - at an
Enterprise clip. So, here’s some stuff I’m still strugglin’ with:

-   Scalability
-   Fault tolerance
-   Clustering?
-   Security

I’m sure there are answers - I’ve just not found good resources yet.
There also is no “book” to turn to. There isn’t even a book covering
OSGi r4, the latest spec. The is more a testament to where OSGi is
seeing its growth - in the Open Source space. But, it sure would be nice
to have something to read…
