+++
author = "Arran Short"
date = 2016-12-01T20:00:00Z
description = ""
draft = false
slug = "using-tplink-tl-poe10r-poe-splitter"
title = "Using the TPLink TL-POE10R PoE Splitter with a Cisco Inline power switch WS-C3550-24PWR-SMI"

+++


---

**TL:DR** using some relays to bridge the Tx and Rx pins on the “normally closed” pins so that it go open circuit when powered is enough to enable the power output and it works no problem with a TL-POE10R

---

As part of my Raspberry Pi Zero CCTV project, I’ve opted to use PoE to get data and power outside to the cameras.

After another hasty ebay spree, I ended up with a Cisco WS-C3550-24PWR-SMI 24 port “PoE” switch.  Little did I know Cisco had their own version of PoE before the 802.3af standard arrived called Inline power.

After doing my usual and researching what I’ve bought after purchasing (and not before) and realizing it wasn’t compatible 🙁  I initially I thought to just return it but after pricing up real PoE or passive PoE compared to what I payed for this switch (£25) it seemed daft to not give it a go.

I took the switch apart and googled some of the part numbers that looked like they may control the Inline power circuit and I couldn’t find any datasheets to see if there was any way to “hot wire” or reverse engineer the circuit.

Anyway, after hours of searching Cisco inline power and seeing if anyone else had the pleasure, all I could find were people trying to use inline power phones with 802.3af switches.

At this point, the only information I had was that a “PD” echoes a low-frequency signal back to the switch via a low pass filter which then tells it to enable the power output.

So now the plan is to measure this low-frequency signal with my scope and try and reproduce this filter with my own circuit.

By this point, I figured a Cisco Inline power phone is going to be the cheapest method of seeing this signal being used and what components are used in the phone.

Back to eBay to acquire a cheap Cisco phone, so £8 lighter and a few days later a CP-7912G-A arrived. Connected it up to the switch and its powered up OK so good news!

Get the screwdriver out and take the phone apart and everything is very compact and there isn’t the magical silkscreen with labels to the filter PCB that I was hoping for to copy however I did spot some relays which help explain some of the Cisco troubleshooting guides.

