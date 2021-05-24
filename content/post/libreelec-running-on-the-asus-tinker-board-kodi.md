+++
author = "Arran Short"
date = 2017-05-07T12:19:58Z
description = ""
draft = false
image = "/images/2017/05/20170507_105700.jpg"
slug = "libreelec-running-on-the-asus-tinker-board-kodi"
title = "LibreElec running on the ASUS Tinker Board ( KODI )"

+++


Yep you've read that correctly the ASUS Tinkerboard has finally had some LibreElec lovin'

[Omegamoon](http://www.omegamoon.com) has forked LibreElec and added all the necessary patches and tools to build a bootable SD card image of LibreElec for the ASUS tinker board.

You can find the fork here https://github.com/omegamoon/LibreELEC.tv/tree/Rockchip
And the guide I followed to build it here https://wiki.libreelec.tv/index.php?title=Compile

**Progress**

* [x] LEDs (power, sd-card activity and heartbeat)
* [x] Persistent ethernet MAC-address set in u-boot
* [x] Kodi fbdev (for performance testing, no vsync, no double buffering)
* [ ] Kodi DRM/KMS
  * [x] Basic rendering
  * [x] Resolution / refresh rate change
  * [ ] Atomic DRM
* [ ] Audio
  * [x] I2S Stereo L-PCM
  * [x] I2S Multi-channel L-PCM
  * [x] I2S NL-PCM (AC3/E-AC3/DTS)
  * [ ] I2S/SPDIF HBR (TrueHD/DTS-HD)
  * [x] HDA 3.5 mm jack
* [ ] Video
  * [x] Software decoding
  * [x] Hardware decoding (works with mpv)
    * [x] h264 / hevc / vp8
    * [x] mpegts container
    * [ ] scale video correctly
* [x] WiFi
* [ ] ~~Bluetooth~~
* [ ] CEC

**Known Issues**

* Video is stretched to full screen and uses wrong aspect ratio
* Scaling 2160p video to 1080p causes green lines at bottom of screen
* Bluetooth requires unwanted changes to uart in kernel
* Generic USB-Audio do not work due to a custom alsa config
* 4K resolution is limited to 30hz

**Demo**
<iframe width="560" height="315" src="https://www.youtube.com/embed/q8v-gZ-2DGA" frameborder="0" allowfullscreen></iframe>

**One thing I would suggest is a fan!**

After a few minutes of watching youtube (via kodi) with just the heatsink it got hot enough to trigger a reboot :( 



You can buy an ASUS tinkerboard at Amazon 
UK - http://amzn.to/2qdlL4O
GLOBAL - http://amzn.to/2qd9sWi

