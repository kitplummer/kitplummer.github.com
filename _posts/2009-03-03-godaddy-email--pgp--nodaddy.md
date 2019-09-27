---
layout: post
title: GoDaddy Email + PGP = NoDaddy!
---

After way too much time spent by me and a PGP support guy I finally came
to the conclusion that GoDaddy was mucking with the SMTP side of things
- to the point where I couldn’t send an encrypted email. I’m already a
tad bit disgusted with GoDaddy’s “Girls Gone Wild” marketing slant. So,
this new revelation that there is some inherent need to not allow me to
send encrypted emails is a bid awkward. Remember just because you may
being using SSL to send mail, it is only SSL’ed/encrypted between you
and their relay. (I could be wrong here, and it wouldn’t be the first
time - but, I’m just too lazy to find out. Plus I’d like to think there
is more to me wanting to leave GoDaddy besides their sleeziness.) The
problem is that the PGP Desktop/email proxy wasn’t able to do its thing
based on the email configuration. I happen to be on a Mac and using
Apple Mail, which at first I was willing to drop the blame on. But,
after switching to a new provider the PGP Desktop client configure
everything transparently with no issues. It did do a number on my Gmail
configuration - disabling TLS there. But, all I had to do was turn it
back on, and disable the PGP auto-configure option.

So…if you are hoping you’ll be able to sign and encrypt emails for a
domain hosted through GoDaddy - get ready for a battle, or a switch.
