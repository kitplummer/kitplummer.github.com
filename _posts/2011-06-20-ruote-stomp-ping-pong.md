---
layout: post
title: Ruote-Stomp Ping Pong
tags: workflow
categories:
- workflow
---

# {{ page.title }}

Just returning from some time with the [DevOpsDays crew](http://devopsdays.org/events/2011-mountainview/) and a bit of an extending "vacation" at the Taos Holy Cross Hospital (after my son's attempt to fly a mountain bike down the Angel Fire ski resort :)).  I've been meaning to get this tidbit blogged for a bit, but it just hasn't happened - seemingly more typical these days.  Ah well.

Quickly, here are the players:

* [Ruote](http://ruote.rubyforge.org)
* [Stomp](https://github.com/kellyp/stomp)
* [stompserver](http://stompserver.rubyforge.org/) or ActiveMQ
* [ruote-stomp](https://github.com/maestrodev/ruote-stomp)
* [daemon-kit](https://github.com/kennethkalmer/daemon-kit) - for generating the simple "workers"

![pingpong](http://www.orangejuiceblog.com/wp-content/uploads/2010/12/world-championship-ping-pong.jpg)

This story began with the [AMQP-based Ping Pong exercise](http://simplic.it/blog/an-investigiation-into-ruote-and-amqp) as I was looking hard at [Ruote](http://ruote.rubyforge.org) for a project needing remote, distributed work units, similar to what is possible to [Resque](https://github.com/defunkt/resque) that could be attached to managed workflows.  

![ruote](http://ruote.rubyforge.org/images/ruote.png)

Ruote itself is deserving of an entire blog post.  It is an amazing framework, that captures the need for a simple, lightweight engine that could - do more than basic state machine stuffs - accommodating standard [workflow patterns](http://ruote.rubyforge.org/patterns.html).
  
Although I think AMQP is definitely up to the task of brokering the work units, I need something that can be run from within a JVM, and is a bit easier to test in isolation.  Since the only content that is passed between Ruote's "engine" and "participants" is textual, and JSON at that I figured the [Stomp protocol](http://stomp.codehaus.org) was a logical choice.  Stomp is supported in many messaging brokers (ActiveMQ, RabbitMQ, stompserver).  So, I set off to port the AMQP ping pong setup to Stomp.

I shamelessly started with the work Kenneth Kalmer did in the [ruote-amqp](https://github.com/kennethkalmer/ruote-amqp) gem, simply swapping the appropriate AMQP calls for Stomp calls.  And, thus [ruote-stomp](https://github.com/maestrodev/ruote-stomp) was born.  It tests pretty easily with the embedded ruby-based stompserver.

I then needed to get the ping and pong participants to use stomp.  The AMQP-based ping pong version uses [daemon-kit](https://github.com/kennethkalmer/daemon-kit) to build participants that consume work off of queues.  So, I then [forked](https://github.com/kitplummer/daemon-kit) Kenneth's work, and added the stomp capability.

The end result, my Ruote-Stomp Ping Pong experiment, can be found at [https://github.com/kitplummer/ruote-stomp-ping-pong](https://github.com/kitplummer/ruote-stomp-ping-pong).  To run it is pretty straightforward:

1. Clone the [ruote-stomp-ping-pong](https://github.com/kitplummer/ruote-stomp-ping-pong) project.

2. Open 3 terminal windows and cd into each project subdirectory (ping/, pong/,
ping-pong-engine/).

3. Ping

```
➜  ping bundle
```

```
➜  ping bin/ping
```

4. Pong

```
➜  pong bundle
```

```
➜  pong bin/pong
```

5. Ping-Pong-Engine

```
➜  ping-pong-engine bundle
```

```
➜  ping-pong-engine stompserver &
```

```
➜  ping-pong-engine ruby lib/main.rb
```

