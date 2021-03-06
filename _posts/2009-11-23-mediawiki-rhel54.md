---
layout: post
title: MediaWiki and RHEL5.4
---

{{ page.title }}
================

I’ve recently been toying with Semantic stuff and MediaWiki.
Unfortunately, due to a few constraints I probably won’t have the luxury
of sitting on top of an Ubuntu server platform - requiring a more
“approved” OS. RHEL 5.x currently meets the my requirements. So, after
creating a new VMware can with the RHEL 5.2 Server install I begun the
process.

Fortunately, and somewhat to my surprise it was quite easy, and yet
Google revealed very little to let me think otherwise. In fact the only
recent docs/posts I found would’ve had me building and installing from
source - the xAMP pieces. Ugh.

The good news is that Yum support prevents all of that. But, better yet
the ‘Add Software’ menu option made it even easier/intuitive. With the
“Package Manager” opened you can browse the Servers section - and select
MySQL Database and Web Server. That’ll get the xAMx part. I did have to
hit “Apply” here.

Once those are set up and in place I then did a search for ‘php mysql’
and installed the latest of both the ‘php’ and ‘php-mysql’ packages.
Clicked “Apply” and that’s good.

I did configure both Apache (httpd) and MySQL to start automatically
using ‘chkconfig’.

To get MediaWiki install I simple downloaded the latest tarball and
exploded it in the /var/www directory structure. Then it was a simple
edit of the httpd.conf setting the DocumentRoot to /var/www/mediawiki
(which is what I exploded the tarball as).

I did have to set MySQL’s root password manually too.

That’s it. Not quite ‘sudo apt-get install mediawiki’ - but who cares,
and I’m on the latest MediaWiki not 1.13.x.
