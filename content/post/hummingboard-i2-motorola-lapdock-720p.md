+++
author = "Arran Short"
date = 2016-05-21T12:45:00Z
description = ""
draft = false
slug = "hummingboard-i2-motorola-lapdock-720p"
title = "Hummingboard i2 & Motorola lapdock 720p fix."

+++


I bought a Hummingboard i2 off ebay as it was going cheap and I’ve wanted to play with an sbc with canbus and lvds.

Anyway it came with openelec on the memory card so to test it I connected it up to my to my lapdock and getto usb cable.

Kodi loaded but it would only give 720x576p resolution.

Turns out any none standard resolutions given over edid are ignored by the kernel and it defaults to 576p.

I did some investigation on the solidrun forums and came across [this post](http://forum.solid-run.com/viewtopic.php?f=16&t=474&p=2631&hilit=Lapdock#p7223) which has some manual timings for the lapdock.

I’ve added the below command to /storage/.config/autostart.sh which sorts everything out before kodi boots


    #!/bin/sh
    fbset -g 1280 720 1280 720 16 -t 13468 140 210 10 10 20 10


Reboot and hey presto it all works.

