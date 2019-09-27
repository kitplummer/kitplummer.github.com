---
layout: post
title: Gumstix, Wifistix and a WPA-configured Airport Extreme...
---

I ran into a bit of an issue trying to connect a suite of
[Gumstix](http://www.gumstix.com) computers to my local Airport Extreme
(WPA2) WAP. The fix is really simple; I just had to add a “proto”
configuration in the /etc/wpa\_supplicant.conf file:

    network={
            ssid="yourSSID"
            proto=WPA2
            #psk="your_passphrase"
            psk=bf83f4c896110b115bee8ff77b372f844435108950476a51667dd1b4a97e5b98
    }

The rest of the directions
[here](http://docwiki.gumstix.org/WPA_for_wifistix) are still good.
