+++
author = "Arran Short"
date = 2015-12-26T16:49:00Z
description = ""
draft = false
slug = "innovate-mts-to-megasquirt-can-bus"
title = "Innovate MTS to Megasquirt CAN Bus converter part 1"

+++


After quiting my job last month I’ve finally had some time to put my collection of STM32 boards to work.

With the addition of the STM32 cpus to the MBED platform its made it super simple to write code for them.

The first thing that I’ve decided to develop is an Innovate MTS to Megasquirt CANBUS converter.

You can see the MBED project here  
[  
](https://www.blogger.com/goog_2034459118) [https://developer.mbed.org/users/sordfish/code/MTS_TO_MSCAN/wiki/Homepage](https://developer.mbed.org/users/sordfish/code/MTS_TO_MSCAN/wiki/Homepage)

Its still alpha code but I’ve had it connected to a Microsquirt and it was doing something!

I’ve added CAN filtering since I last tested so it may or may not work at this moment in time but I’ll be adding a part 2 with the actual hardware in the next few days.

