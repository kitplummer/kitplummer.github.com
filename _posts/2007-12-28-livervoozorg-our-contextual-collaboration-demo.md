---
layout: post
title: live.rvooz.org, Our Contextual Collaboration Demo...
---

![](http://www.rvooz.org/demo.png)

We’ve recently opened our [silly lil’ web app](http://live.rvooz.org) to
the world. It is a very basic app that shows how it is possible to
register a “context” with our Salient server, use an instant messaging
client that is connected to an Openfire Jabber server (running our
Openfire Voozer), and get matches based on that context.

Unfortunately, the app opened up a few cans of “worms” including Adobe’s
Flex(Builder). We also have spent a bit of time with Javascript which we
ultimately dumped in favor of an all-Flash version of the app.

Take ’er for a spin - and let me know if it doesn’t make sense. The
potential for integrating IM, or VoIP into existing applications in
order to “link” people is just huge. We are beginning to think about
scalability issues and are considering a jump to a true web-application
enviro - over our current server-based architecture based on OSGi and
Jetty. One of the key problems we have to overcome is the handling of
user-security and data-security. The solution here will push in one
direction over the other. Although I really appreciate OSGi (and to a
lesser extent Java), the need for this Open Source project’s product to
function as a “software service” is driving us away. Ruby on Rails is
looking nice, simply because it solves a lot of our problems out of the
box.

We’ve also done some preliminary research on Amazon’s EC2 and S3
services. Those combined with RoR’s “portability” make for a nice
delivery platform that scales out as necessary.

Anyway…check out the [demo](http://live.rvooz.org).
