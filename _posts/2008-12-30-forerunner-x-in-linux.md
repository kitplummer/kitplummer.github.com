---
layout: post
title: Forerunner 30x in Linux...
---

I’ve been ‘toying’ with using my [Garmin](http://www.garmin.com)
Forerunner 30x training GPSes in Linux. I’d been having all kinds of
problems getting [gpsd](http://gpsd.berlios.de) to work with it. Neither
my 301 or 305 units are “supported” by gpsd - but, there was plenty of
posts floating in the Interstew that led me to believe it *could* be
done.

The key ingredient was this dandy diddle:

    $ sudo mount -t usbfs none /proc/bus/usb/ 

I accidentally found it in an [Ubuntu
forum](http://ubuntuforums.org/showthread.php?t=642999) and to my
surprise I was quickly able to get gpsd working.

Now, on to the fun stuff - reading gpsd from Ruby. :-)
