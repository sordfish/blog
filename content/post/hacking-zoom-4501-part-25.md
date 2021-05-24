+++
author = "Arran Short"
date = 2011-02-24T23:00:00Z
description = ""
draft = false
slug = "hacking-zoom-4501-part-25"
title = "Hacking Zoom 4501 part 2.5"

+++


while randomly searching ebay for bargin rt305x devices i spotted a **LEVEL ONE WBR-6800** which looks  very familiar to the zalip CDW530AM…  
Found [the manufactures website](http://uk.level1.com/product_d.php?id=890#) and hey presto its the same and there’s a gpl zip for it.  
Followed the instructions that came with it and make fails, it seems a lot has bee stripped out, but I’ve spotted the make file and program that builds the firmware.

I’ve also had reply from zoom with a link for gpl stuff and it look like it has come from the same place (amit) but dated older so fingers crossed that compiles.

Still no luck dumping the flash, httpd wont budge from /var/www which is read only and the tftp doesn’t allow the put command.

built a wiggler and tried some jtag but that was a waste of time, none of the software made any sense and they all seem to be written in the stone age.

