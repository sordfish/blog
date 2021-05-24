+++
author = "Arran Short"
date = 2015-12-26T00:59:00Z
description = ""
draft = false
slug = "burg-on-linux-mint-173"
title = "Burg on Linux Mint 17.3"

+++


Santa dropped off an SSD for my dev laptop which duel boots windows xp and Linux mint.
I’ve always wanted something a bit more polished for a boot manager and found
Burg **B**rand-new **U**niversal loade**R** from **G**RUB

Here’s how I installed it

    sudo add-apt-repository ppa:n-muench/burg
    sudo apt-get update
    sudo apt-get install burg burg-themes
    sudo burg-install /dev/sda (please check the name of your drive)
    sudo update-burg

Then to test

    burg-emu

ta da! **F2** allows you to choose what theme and **F3** will change the resolution.

*please bear in mind adding a repo can be a security risk, I don’t own that repo nor have the ability to check how genuine it is, us at your own risk.
Using sudo with boot managers can brick your machine, have a live distro handy in case you make a mistake!*

