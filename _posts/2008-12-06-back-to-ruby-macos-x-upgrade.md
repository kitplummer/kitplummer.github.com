---
layout: post
title: Back to Ruby, MacOS X Upgrade...
---

Well…it has been a while since I’ve had a chance to do *anything* with
Ruby, which sucked. I’d figured I start with upgrading Ruby itself since
the version I’ve installed (default) is 1.8.6. But, since 1.8.7 is the
current (all the dev must be going into 1.9+) I figured updating
RubyGems and all of my gems would be the best place to start.

I instantly hit a wall with ‘gem update —system’ or even ‘gem update’.

But thanks to the Internet and people hitting this problem many months
back I found solutions:

Merbivore was killing me first, solution found
[here](http://kl93.blogspot.com/2008/08/add-and-remove-remote-source-from-gem.html)

Then, I ran into an issue with an older version of RubyGems itself.
Found a decent blog
[here](http://www.theodorenguyen-cao.com/2008/11/08/undefined-local-variable-or-method-remote_gemspecs/)
describing the steps to resolve - upgrading RubyGems to 1.3.1.

Phew…I’d have hated to have had to figure it out myself. On to playing
with [RSS feed
parsing](http://nasir.wordpress.com/2007/12/03/rss-feeds-ruby-on-rails-web-app/).
