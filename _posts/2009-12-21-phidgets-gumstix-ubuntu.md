---
layout: post
title: Phidgets (Gumstix) and Ubuntu 9.10
---

{{ page.title }} Well, it’s that time of the year ago…my home automation spirit kicks in, and the robot pieces come out of the closet.
======================================================================================================================================

It started with a rebuild of my dev environment. Said to say that the
Gumstix docs still suck. I was able to get my dev enviro, based on
Ubuntu 9.10, with the help of the mailing list.

Then it was installing the Linux drivers for the
[Phidget](http://www.phidgets.com) SDK. They installed no problem, but I
couldn’t get the drivers to actually load when I installed a device. I
figured something was missing around *udev*. Sure enough…just needed to
set *udev* up.

    <code>$ sudo cp udev/99-phidgets.rules /etc/udev/rules.d/</code>

and

    <code>$ sudo /etc/init.d/udev restart</code>

The I ran both the example *manager* and the Servo Test that comes with
the standardC examples SDK.

I was also able to get a version of the Phidgets SDK to compile against
my OpenEmbedded Gumstix enviro. The Bitbake recipe is
[here](http://github.com/kitplummer/phidgets-oe) - maybe somebody will
find it and run.
