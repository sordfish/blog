+++
author = "Arran Short"
date = 2015-12-29T12:24:00Z
description = ""
draft = false
slug = "stm32f103xc-ili9341-lcd-fsmc-chibios"
title = "STM32F103xC + ILI9341 LCD + FSMC + CHIBiOS + UGFX = Success! - CC9060 hacking Part 2"

+++


After re writing the ugfx board config from scratch and going through the code with a fine tooth comb I finally got the LCD to work!

The included drivers for the ILI9341 are only written for 8bit wiring configs, so I got an Image of sorts, but just in blue.

After reading every thread on the ugfx forum relating to the ILI9341 I found [this one](http://forum.ugfx.org/viewtopic.php?f=23&t=130&p=2427#p2427) which explained what I need to do to get the other 8 bits back.

Tiny tweak of the code and hey presto!

<div style="clear: both; text-align: center;">[![]()]()</div>*<span style="font-size: x-small;">  
</span>*

<div style="text-align: center;">*<span style="font-size: x-small;">Now that I have working LCD drivers I can push on with canbus and gauges!</span>*</div>I’ll be uploading a complete ChibiStudio project for this board once I have all the kinks worked out.

