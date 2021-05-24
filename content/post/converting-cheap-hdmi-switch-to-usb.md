+++
author = "Arran Short"
date = 2013-10-24T18:38:00Z
description = ""
draft = false
slug = "converting-cheap-hdmi-switch-to-usb"
title = "Converting Cheap HDMI switch to usb. with added php magic"

+++


<div style="text-align: center;">Finally got round to adding some usb goodness to a cheapy hdmi switch  I got off ebay.</div><div style="text-align: center;"></div><div style="text-align: center;">it has 3 inputs and is controlled by a button in the center to choose which channel  is active, it has auto detect but i tend not to switch anything off so thats useless, plus having to get out of bed once I’ve got comfy to change inputs was slighty 2001 so…</div><div style="clear: both; text-align: center;">[![]()]()</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;">out the goody box comes a minimus avr dev board i acquired of ebay fairly cheap, it has an at90usb162 mcu that can be [persuaded](http://www.mattairtech.com/index.php/development-boards/mt-db-u1.html) to work with the arduino ide.</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;">few blobs of solder and some wire, and an npn transistor (to emulate the button press) later we have a usb controlled hdmi switch.</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;">Now i couldn’t just stop there…</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;">My hp micro server is also stashed in my “wardrobe”  with the switch so I have plugged the switch into that, and with a bit of php magic the I now have a web controlled hdmi switch</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;">Now i couldn’t just stop there…</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;">There’s this awesome app called tasker for android that pretty much lets you automate everything, so with a task setup to http get my php code I now have a button on my phone to change inputs.</div><div style="clear: both; text-align: center;"></div><div style="clear: both; text-align: center;"></div>

