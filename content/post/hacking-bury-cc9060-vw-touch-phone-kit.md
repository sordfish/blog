+++
author = "Arran Short"
date = 2015-12-26T17:17:00Z
description = ""
draft = false
slug = "hacking-bury-cc9060-vw-touch-phone-kit"
title = "Hacking the Bury CC9060 / VW Touch Phone Kit - Part 1"

+++


Whilst looking for an LCD to use as a display for Megasquirt

I found a display from a Volkswagen Touch Phone kit, these are a VW themed and branded version of the Bury CC9060
The 708 version of this hardware has an STM32F103 with some nice little goodies left on the board from when it was being developed.

I’ve sacrificed one to work out the JTAG/SWD pinouts and to establish how the LCD is connected to the board.
[![]()]()

Yes that is an unpopulated mini usb connector and that vertical row of pads is the JTAG/SWD interface.
Which works out as the following

    pin 1 – voltage, (haven’t checked what voltage, suspect 3v) 
    pin 2 – PA14 – JTCK – SWCLK
    pin 3 – PB3 – JTDO – SWO
    pin 4 – PA13 – JTMS – SWDIO
    pin 5 – PA15 – JTDI
    pin 6 – PB4 – NJTRST
    pin 7 – ground

The LCD seems to be an ILI9341 made by Top Foison the data sheet can be found here.http://www.topfoison.com/product/2.8inch-TFT-LCD-module.html

It's connected to the STM32 on the fsmc pins, I’ve been trying to get Chibios and ugfx to work with it but example code is a bit scarce for this controller in 16bit.

I’m going to keep poking as its a nice device and once I’ve go the LCD going, CANbus etc shouldn’t be far behind.

