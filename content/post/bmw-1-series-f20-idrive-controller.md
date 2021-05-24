+++
author = "Arran Short"
categories = ["microcontrollers"]
date = 2017-02-01T14:51:00Z
description = ""
draft = false
image = "/images/2017/04/20170131_215600-1.jpg"
slug = "bmw-1-series-f20-idrive-controller"
tags = ["microcontrollers"]
title = "BMW 1 series F20 iDrive controller hacking with arduino and PI"

+++


As part of a larger in car entertainment project, I needed a simple and safe input method to control the software that wasn’t a touch screen. As BMWs are popular in the car PC scene I thought I’d buy an IDrive controller as surely there will be an Arduino lib to get it working.

Nope, there are a few pages of people giving out tiny bits of information or claiming to have done it but haven’t shared it on the Web.

The one piece of helpful information I did pull from the aforementioned websites was the fact that these controllers use a low speed  ( 100kbit for BMW ) fault tolerant CANbus transceiver, the TJA1054 or TJA1055.

Some more googling pointed out that the MCP2551 I normally use wasn’t going to work and I needed to use the TJA1054/5

The frugal/lazy part of me didn’t want to have to make up a PCB board straight away for the TJA1054 before it was tested and I was more familiar with it.

In comes a VAG CANbus gateway. These handy devices are how VAG manage the different speed CANbus networks at the obd2 port. TL;DR these are a cheap board with 2x TJA1054, 2x high-speed transceivers and a 5v regulator.

After removing the NEC Cpu from the gateway I connected one of the low-speed transceivers to an Arduino with my DIY MCP2515 shield and the other to a PI zero with an MCP2515 canpi hat.

The first controller I tried was from an e60 which has 2 external buttons and the twist joystick.

With any can frames on the bus this would reply with 0x4e7 messages, turns out there isn’t much info on these and I couldn’t find any example of someone getting it to work.

The second was from a 2012 1 series this is the lower spec model that only has the 5 buttons and the left-right joystick with a rotary encoder.

Everyone seems to know that sending frames to 0x202 will enable the lights but no other information exists to explain how to get it to reply back with button presses.

So it’s time to brute force the CANbus. a tiny bit of Arduino code later got me sending 8 bytes of 0xff to every 11bit ID twice every 100ms while I repeatedly pressed the buttons.

With both eyes on Wireshark, it gets to the 0x500 numbers and thing replies start happening then the magic number appears 0x535 this is the ID that will keep the device awake and will allow you to get the frames for button presses.

This sadly doesn’t give any data for the rotary encoder but I thing that may need extra data to “initialize”.

I’ll be doing some more testing to get the rotary encoder working as well as some code to use this a hid device.

Keep an eye out for that!

![](/content/images/2017/04/20170131_215801.jpg)

