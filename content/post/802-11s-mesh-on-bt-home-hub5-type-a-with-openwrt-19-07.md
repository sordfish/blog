+++
author = "Arran Short"
date = 2020-06-21T14:19:33Z
description = ""
draft = true
slug = "802-11s-mesh-on-bt-home-hub5-type-a-with-openwrt-19-07"
title = "802.11s Mesh on BT Home Hub5 type A with Openwrt 19.07"

+++




### TL;DR - I got 802.11S mesh working over the 5Ghz radio in a BT Home hub 5 type A but from initial benchmarks performance is below average.



### Reasons?

Until I can CAT6 my house I need a cheap and effective way of getting decent wifi coverage.

Home Hub 5 routers are littered on ebay for not much money but they have dual radios and are fairly compact.

### Setup

I followed the long winded process of getting OpenWRT installed via uart and tftp after that you need do to the following extra commands

```
opkg update
opkg remove wpad-basic
opkg install wpad-mesh-openssl

opkg remove atk10-firmware-ct
opkg install atk10-firmware
```

Then replace `/etc/config/wireless` with the following







