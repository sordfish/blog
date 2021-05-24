+++
author = "Arran Short"
date = 2013-02-16T23:48:00Z
description = ""
draft = false
slug = "making-wr702n-run-openwrt-part-1"
title = "Making the WR702n run openwrt part 1"

+++


After blindly buying a blue tplink router off eBay at 3am, it turns out I bought the WR702n instead of the openwrt friendly WR703n.

The wr702n runs vxworks and only has 2MB flash and 16MB ram and no USB, This isn’t enough for openwrt.  
It turns out that other fellow hackers have upgraded the flash and ram on the 703 so I’v done the same to the WR702n.

**<span style="font-size: large;">Getting the Parts…</span>**

First port of call is to find suitable flash and ram chips.  
I have bought MX25L6445EM2I-10G from china and a 512MB sodimm DDR ram stick to harvest the <span style="background-color: white; font-family: sans-serif; font-size: 14px; line-height: 21.59375px;">Hynix HY5DU121622DTP-D43</span> chips.

<span style="font-size: large;">**Replacing the ram…**</span>  
<span style="font-size: large;">**  
**</span>Changing the ram first seemed best as vxworks would still run once done..  
so out with the Hot air and chip Quik and we now have a 64MB ram chip installed.

<table cellpadding="0" cellspacing="0" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody><tr><td style="text-align: center;">[![]()]() </td></tr><tr><td style="text-align: center;">Ram chip removed with flux and hot air</td></tr></tbody></table><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;"></div><table align="center" cellpadding="0" cellspacing="0" style="clear: left; margin-bottom: 1em; margin-left: auto; margin-right: auto; text-align: center;"><tbody><tr><td style="text-align: center;">[![]()]()</td></tr><tr><td style="text-align: center;">64MB RAM and serial wires.</td></tr></tbody></table><div style="text-align: left;">Vxworks still booted so ram success fully swapped (first boot too).</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: left;"><span style="font-size: large;">**The flash chip…**</span></div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">I needed an spi flasher of some kind, I had seen the bus pirate being used but I don’t have one and didn’t fancy buying anymore tools if I dint need to.</div><div style="clear: both; text-align: left;"></div><table align="center" cellpadding="0" cellspacing="0" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody><tr><td style="text-align: center;">[![]()]()</td></tr><tr><td style="text-align: center;">Arduino mini pro (3.3v) with spi chip attached to wires. Full size arduino used just for usb to serial.</td></tr></tbody></table><div style="clear: both; text-align: left;">After spotting  [a post](http://hackaday.com/2012/05/04/arduino-uno-bios-flasher/) on hack a day using an arduino to program the chips, I installed Ubuntu and programmed serprog onto an arduino mini pro. It took a bit of fiddling to get it recognized by flashrom but after a few port speed issues I was able to dump the contents of the new chip.</div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">**<span style="font-size: large;">DAS U-boot…</span>**</div><div style="clear: both; text-align: left;">Now with it all ready to go I needed to find a copy of uboot to install. turns out there’s an [awesome version](http://code.google.com/p/wr703n-uboot-with-web-failsafe/) with an http server built in for flashing.</div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">Wrote that to the chip with flashrom, verified it and then soldered it in place of the 2MB chip.</div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;"><span style="font-size: large;">**Success!!!**</span></div><div style="clear: both; text-align: left;"><span style="font-size: large;">**  
**</span></div><div style="clear: both; text-align: left;">powered it up and uboot started to scroll messages in putty. Next was to get openwrt installed.</div><div style="clear: both; text-align: left;">Turns out the http server is a bit temperamental and only likes firefox 13.0.1? </div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">after programming the latest sysupgrade file for openwrt it flashed itself and rebooted and was greeted by the boot log of openwrt 🙂</div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;"><span style="font-size: large;">To be continued…</span></div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">I still need to recover the unique “ART” partition from the original 2MB flash chip so the wifi will work.</div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">I also need to update uboot for 8mb as it only can access the first 4mb atm. </div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;">Lastly the usb port needs to work so I just need to add some components to get that working too.</div><div style="clear: both; text-align: left;"></div><div style="clear: both; text-align: left;"></div>

