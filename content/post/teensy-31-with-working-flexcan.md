+++
author = "Arran Short"
date = 2016-01-05T14:46:00Z
description = ""
draft = false
slug = "teensy-31-with-working-flexcan"
title = "Teensy 3.1 with working flexCAN interrupts and BUSMASTER compatibility"

+++


The Teensy 3.1 flexCAN library doesn’t have the facility for setting up interrupts for incoming messages. So I set out to fix the problem, and after a lot of forum research and a few tweaks I’ve been able to get interrupts working.

I’ve ported my mcp2515 based Arduino CAN to USB logger to the Teensy, this firmware implements the Lawicel protocol (badly haha) to be compatible with canhacker software.

While doing a bit of research I discovered that VScom’s ser-com tool also uses the Lawicel protocol and they have drivers built into Bosch’s BUSMASTER software, WINNER!! so I’ve now got access to what looks like a pretty sweet bit of canbus logging software.

To test I programmed one of my STM32 boards to spam the bus continuously and it seems that BUSMASTER and the teensy were able to keep up, and the network stats showed 99.9% bus load! horray.

I still have the transmit side of the Lawicel protocol to implement and maybe tidy up and complete my changes (add loopback and listen only mode and some error detection) made to the flexCAN library.

