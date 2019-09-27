---
layout: post
title: A Jabber Bot in Ruby...Cool.
---

[Brett Stimmerman](http://www.socket7.net) (I don’t know the guy) has
this Ruby abstraction for xmpp4r-simple (which an abstraction for
xmpp4r) call Jabber::Bot. Maybe it is just the pure geek in me, but I
think this stuff is cool.

    <code>
    #!/usr/bin/env ruby
    require 'rubygems'
    require 'jabber/bot'

    # Create a public Jabber::Bot
    bot = Jabber::Bot.new(
      :jabber_id => 'test@blitz.local', 
      :password  => 'test', 
      :master    => 'kplummer@blitz.local',
      :is_public => true
    )

    # Give your bot a public command
    bot.add_command(
      :syntax      => 'rand',
      :description => 'Produce a random number from 0 to 10',
      :regex       => /^rand$/,
      :is_public   => true
    ) { rand(10).to_s }

    # Give your bot a private command with an alias
    bot.add_command(
      :syntax      => 'puts <string>',
      :description => 'Write something to $stdout',
      :regex       => /^puts\s+.+$/,
      :is_public  => false,
      :alias       => [ 
          :syntax => 'p <string>', 
          :regex => /^p\s+.+$/
      ]
    ) do |sender, message|
      puts message
      "'#{message}' written to $stdout"
    end

    # Give your bot a private command
    bot.add_command(
      :syntax      => 'uname',
      :description => 'Fetch the uname -a command',
      :regex       => /^uname$/,
      :is_public   => false
    )   do |sender, message|
       # puts message
        `uname -a`
    end

    # Bring your new bot to life
    bot.connect
    </code>

Requires [jabber/bot](http://socket7.net/software/jabber-bot) and
[xmpp4r-simple](http://xmpp4r-simple.rubyforge.org/)

Have at it, let your imagination run wild.
