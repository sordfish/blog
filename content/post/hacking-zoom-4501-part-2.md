+++
author = "Arran Short"
date = 2011-02-20T12:13:00Z
description = ""
draft = false
slug = "hacking-zoom-4501-part-2"
title = "Hacking zoom 4501 part 2"

+++


I emailed zoom for sources and got the response “sorry- this is not possible.” so unless they miss understood the  email they are violating gpl by not releasing it., noobs.Any way it seems it is also known as Aluratek CDW530AM and Zalip CDW530AM, I’ve downloaded some firmware for the aluratek model to see if I could flash that.

They have different headers but even after changing that the zoom router wouldn’t accept the firmware. 🙁 so its not just headers that it needs.

I was using hyperterm to connect to the serial console but I didn’t have much success, I’m now using putty and that seems to work.

So I now have console access 😀

The bootloader (jboot?) can be stopped by pressing enter after boot up, and has a prompt for commands typing ‘help’spits out this.

```
# help  
command list…  
reboot  
info  
load  
go  
dm  
wm  
rm  
copy  
ip [ip]  
mac [mac]  
ping  
areacode  
```

I emailed zoom for sources and got the response “sorry, this is not possible.” so unless they miss understood the email they are violating gpl by not releasing it, noobs.Any way it seems it is also known as Aluratek CDW530AM and Zalip CDW530AM, I’ve downloaded some firmware for the aluratek model to see if I could flash that.

They have different headers but even after changing that the zoom router wouldn’t accept the firmware. 🙁

So it's not just headers that it needs. I was using hyperterm to connect to the serial console but I didn’t have much success, I’m now using putty and that seems to work.

So I now have console access 😀

The bootloader (jboot?) can be stopped by pressing enter after boot up, and has a prompt for commands typing ‘help’spits out this.

it also responds to ‘erase’ and ‘flash’I’m not sure what to do with any of the commands yet but hopefully I can figure out how to get around only using zoom firmware.

Also the router is not as linux friendly as I’d hoped, there are no open source wifi drivers for it so it relies on binary drivers from ralink, the only ones avaliable only work with 2.6.21 kernel, so no backfire :/

Fortunately the fonera 2.0n and simpl use the same chipsets and use older openwrt and seem to have stable firmware. yay!

Update: The bootloader has a built in tftp so pressing enter to stop the boot process then “putting” a firmware file over seems to do the trick now to test non zoom firmware!

it also has http server which directs to a page called “jon recovery system” with just a browse and upgrade button.

I”ve done some more messing with headers and non zoom firmware and it seems theres a checksum of some sort as well, so more guess work needed

