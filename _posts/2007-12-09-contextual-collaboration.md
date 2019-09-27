---
layout: post
title: Contextual Collaboration...
---

One of the cool things about starting a project from scratch is that you
get to pick all kinds of funny new names for things. rVooz is no
different. The name itself is a play on “rendezvous” and the fact that
we’d really like to make it easy for people with the same interest to
meet (communicate, or even work together). This last part is where the
“collaboration” bit comes in to play. It is one thing to rendezvous, it
is another to improve productivity or efficiency. So, we don’t just want
to stop at making the link and providing the communications mechanism.

Here’s a rough example…and it might seem totally ridiculous, but what
edgy idea doesn’t at first.

Imagine a ride-share application to which you could publish your
positional information. The application could take that information and…

-   match others based on a half-mile radius
-   create an instant messaging session
-   create a VoIP/SIP voice session
-   send a TXT message
-   send an email
-   if no match, contact a shuttle/cab/etc.

The context here is the positional information. The collaboration is the
interaction between multiple “users”, the context matching system, the
communication system, and external entities.

In the rVooz system there is a client-side, the piece of the puzzle
which does the registration of the information (a website, instant
message, etc.). The client registers with the Salient server. The
Salient server provides a simple RESTful (HTTP) interface for collecting
context registrations. Within the Salient server there are different
“engines” that process the different kinds of context and rules about
what constitute a match. Once a match is found, the engine notifies
internally the users and context.

On the other side of the client the rVooz system provides a piece called
a Voozer, which is the mechanism for creating the link between multiple
users. This could be as simple as having a “buddy” added to your Instant
Messaging roster, or ringing a soft-phone. Or, it could be complex -
triggering a sequence of events (like causing a report to be generated
and an email sent containing the report). The thought is that a Voozer
can be created for whatever should happen based on a match. In some of
our early concepts we have a Voozers that poll for matches and Voozers
that can get notified on a match event.

Match is a pretty boring term, and doesn’t do justice - so we’ve come up
with contextion. A contextion, is the result of a matched context.

I’m sure you can come up with many other ideas - where contextual
collaboration would be useful. How about Last.fm? Imagine getting a list
of potential “friends” based on a very refined music contextion. Or,
what about an integrated mapping tool that could be used in disaster
recovery efforts to reduce the amount of cross-agency duplication?

Check out the http://www.rvooz.org project for more info…
