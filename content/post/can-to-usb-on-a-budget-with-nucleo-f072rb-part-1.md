+++
author = "Arran Short"
categories = ["microcontrollers"]
date = 2019-10-13T14:30:34Z
description = ""
draft = false
slug = "can-to-usb-on-a-budget-with-nucleo-f072rb-part-1"
tags = ["microcontrollers"]
title = "CAN to USB on a budget with Nucleo-f072rb part 1"

+++


I've been looking to get back into CANbus hacking but all my USB to CAN boards are a bit of a bodge and after recently wasting an evening trying to get one to work again I've decided I want to scrap everything and start again with a known good USB to CAN _tool_ that does the job everytime.

I've seen various boards crop up on hackaday but most just emulate the lawciel serial protocol so consistancy at high bus load isn't great. 

After looking at various low cost turn key devices I stumbled upon [Candlelight](https://github.com/HubertD/candleLight_fw) an STM32F0 firmware that use Linux kernel drivers (gs_usb) allowing direct socketcan access. This gives higher performance and it's simple to use Wireshark and other software like nodejs to help me automate my MED17 Infineon tricore programming (hopefully).

In terms of getting some actual hardware, Cantact is a nice bit of kit but it means importing from the states plus the Cantact only has support for a regular CAN transceiver and I might want to work on devices that need a fault tolerant CAN transceiver e.g. BMW iDrive controllers.

So...  enter the nucleo-f072rb dev kit.

![nucleof072](/content/images/2019/10/nucleof072.jpg)

The Nucleo-f072rb dev kit was chosen as it has the perfect chip to run candlelight and it has arduino shield headers or their 2x19 headers morpho expansion devices. For my project I'll be building a custom stripboard hat/shield using the morpho headers with a device usb port and a canbus transceiver or two.

