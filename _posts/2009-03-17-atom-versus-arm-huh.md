---
layout: post
title: Atom Versus ARM, huh?
---

As the Netbook market continues to evolve - so has the technical
specifications that drive the smaller form-factors and architectures. I
actually don’t believe that ARM has any place in the Netbook market.

Here’s why. I spend a considerable amount of time developing for the
[Gumstix](http://www.gumstix.com) platform. The Gumstix runs
OpenEmbedded, a cross-compile environment for many embedded processors -
most notably, the ARM family. Without going into great detail ARM != x86
(Intel stuff). The cross-compile dance is required to build all the
Linux pieces specifically for the ARM architecture on a (normally)
x86-based machine. While OpenEmbedded supports many of the pieces, that
normally doesn’t cut it. If it is not a supported package the process
(project creation, make manipulation and cross-compiling) is just gross.
Now, coming from an embedded background I’m used to that. The Linux
community in general is not. I can’t speak for the Winders folks, but
guessing not. :)
![](http://gumstix.com/store/catalog/images/prd_verdexXL6P.jpg)

Sure, the ARM platform will get you lower power consumption/longer
battery life. But, at the cost of CPU/RAM resources, and the above
mentioned architecture mess.

To be honest I’m not sure the ARM even has a place is micro devices like
the Gumstix.

The
[fit-PC2](http://www.compulab.co.il/fitpc2/html/fitpc2-datasheet.htm)
shows just how close we could be from a form-factor perspective to the
Gumstix with an Atom-based(x86) processor and 1GB of RAM. Shoot, just
get rid of the connectors and we’re damn close.
![](http://www.linuxdevices.com/files/misc/compulab_fitpcslim-thm.jpg)

The fit-PC2 runs a full-blown Ubuntu environment, which means no
cross-compiling.

The downside is that the fit-PC2 requires 12V and consumes \~6W. For
many applications that may just work…leaving the door open for the ARM
platform. But, I just have to wonder how long before we see 1+GHz
Atom-based platform running off of 3.3-5v at 1-2W. Lights out ARM.

But, the ARM fights back. The [BeagleBoard](http://www.beagleboard.org)
an almost viral phenomenon parented by TI is proving that the ARM is a
valid, general purpose platform.

Again, I’m waiting with intense curiosity…I have to believe Intel is
hard at work (probably with Apple’s interest in mind) on a super
low-power high-performance processor that will bridge the gap and
extinguish the need for cross-compiling.

All this stuff said, I do understand the deltas between the truly
embedded architectures. I’m just a software engineer who appreciates the
OS and application side of things and really want to see a simpler means
for eliminating the void between desktop and mobile platforms.
