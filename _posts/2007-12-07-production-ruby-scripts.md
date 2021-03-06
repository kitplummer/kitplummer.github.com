---
layout: post
title: Production Ruby Scripts?
---

Sure, why not? How about Ruby scripts as daemons? Over the past couples
years, where I’ve been working with Java I’ve had the need to daemonize
a handful of different Java apps including
[ActiveMQ](http://www.activemq.org) and
[ServiceMix](http://www.servicemix.org) and just recently
[Felix](http://felix.apache.org). Thanks to the [Java Service
Wrapper](http://wrapper.tanukisoftware.org/) this is all pretty
painless.

So, out of a “strange” need I found myself needing something similar to
JSW for a Ruby script. Thanks to Google I found
[Daemons](http://daemons.rubyforge.org/) a Ruby script wrapper.

From the Daemons site:

Layout: suppose you have your self-written server myserver.rb:

\# this is myserver.rb  
\# it does nothing really useful at the moment

loop do  
sleep(5)  
end

To use myserver.rb in a production environment, you need to be able to
run myserver.rb in the background (this means detach it from the
console, fork it in the background, release all directories and file
descriptors).

Just create myserver\_control.rb like this:

\# this is myserver\_control.rb

require ‘rubygems’ \# if you use RubyGems  
require ‘daemons’

Daemons.run(‘myserver.rb’)

And use it like this from the console:

$ ruby myserver\_control.rb start  
(myserver.rb is now running in the background)  
$ ruby myserver\_control.rb restart  
(…)  
$ ruby myserver\_control.rb stop

For testing purposes you can even run myserver.rb without forking in the
background:

$ ruby myserver\_control.rb run

An additional nice feature of Daemons is that you can pass additional
arguments to the script that should be daemonized by seperating them by
two hyphens:

$ ruby myserver\_control.rb start — —file=anyfile —a\_switch
another\_argument

And it is really that simple. Way cool.
