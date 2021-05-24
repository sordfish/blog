+++
author = "Arran Short"
date = 2010-04-22T12:18:00Z
description = ""
draft = false
slug = "megasquirt-on-nokia-770"
title = "Megasquirt on nokia 770"

+++


I was thinking the other day how good would it be to have some gauges and basic tuning abilities on the [nokia 770](https://en.wikipedia.org/wiki/Nokia_770_Internet_Tablet) as its based on Linux and gtk I thought it shouldn’t be that hard to write something in python, but thought why start from scratch when there’s megatunix.I’ve had a tiny look into building it from source but it seems a chore just to even get scratchbox working..  
So I thought sod it and started learning python and pygtk and after about a month of head scratching and swearing.

this happened

<div class="post-img">
<a href="/content/images/2017/04/screenshot01.png" target="_blank">
![](/content/images/2017/04/screenshot01.png)
</a>
</div>

<object height="385" width="480"><param name="movie" value="https://www.youtube.com/v/dUmZYu9f5II&hl=en_GB&fs=1&"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed allowfullscreen="true" allowscriptaccess="always" height="385" src="https://www.youtube.com/v/dUmZYu9f5II&hl=en_GB&fs=1&" type="application/x-shockwave-flash" width="480"></embed></object>

I’m still working out the kinks but it's not bad considering it's my first proper python app.

The next things I’d like to learn:

- ecu version detection
- ini file parsing to support multiple firmwares
- guage customisation
- bluetooth scanner and connector (have to do it in the command line atm)
- learn cairo and maybe create some proper gauges
- histograms?
- datalogging to sd card?

There’s a plenty to do but I need a bluetooth to rs232 board as I’ve been using my laptop as a bridge and its a bit glitchy keep getting drop outs.

