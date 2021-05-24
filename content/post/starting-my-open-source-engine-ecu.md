+++
author = "Arran Short"
categories = ["microcontrollers", "FPGA", "Automotive"]
date = 2020-07-04T22:52:01Z
description = ""
draft = false
image = "https://images.unsplash.com/photo-1583198432859-635beb4e8600?ixlib=rb-1.2.1&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=2000&fit=max&ixid=eyJhcHBfaWQiOjExNzczfQ"
slug = "starting-my-open-source-engine-ecu"
tags = ["microcontrollers", "FPGA", "Automotive"]
title = "Getting the cogs turning for My Open Source Engine ECU"

+++


After moving my TMS750 development kit from box to box I've recently decided to see if there had been any community progress on getting the hardware angle clock (HWAG) working.

The **tl;dr** seems to be that a few have tried but came up against a possible hardware bug making it practically useless. I've even asked on the TI forums for example code but they don't have any.

My aim for this ECU is to have a fully open source, highly versatile and precise base to be used on affordable hardware. To achieve this I'm looking into what choices the OEMs and Motorsport ECUs use as inspiration on what direction would suit my ECU's requirements.

Looking at recent OEM ECU's they have chosen a CPU with an on chip co-processor which handles all the angle calculations, these are commonly known by either Freescale/NXP's eTPU or the newer Bosch GTM IP core.

Obviously due to the nature of most OEM's choice of CPUs they need close source tools to make use of the co-processor and are very expensive and hard to source.

Higher end Motorsport ECUs use a Microcontroller and FPGA to handle crank angle and all other time critical computation. Thankfully FPGAs are cheaper and are something I've always wanted to experiment with but the lack of open tools have put it to the back of the queue, Until now...

In comes open source tools like yosys, nextpnr & prjtrellis which are the hard work of some very smart people that have reverse engineered the manufacturer development tools and built the software to build awesome projects.

My choice of FPGA is a Lattice ECP5 (for now) as the base of my experimenting with as it's cheap and has up to 85K luts and is fast!

There are lots to explore with open FPGA development including a large learning curve which I'll try to document as I go along, so stay tuned!

