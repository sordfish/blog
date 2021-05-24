+++
author = "Arran Short"
date = 2020-05-10T14:53:05Z
description = ""
draft = true
slug = "ultimate-hub-pt2-hacking-smartthings-hubs"
title = "Ultimate Hub Pt2 - SmartThings Hubs teardown and hardware review"

+++


In my last post I set off looking for the Ultimate IoT hub to manage my Zigbee and other wireless sensors.

I've already been using the Samsung SmartThings v2 Hub and didn't want to have to dispose of decent hardware if there is an _easy_ way to add my own code.

I first [asked on Reddit](https://www.reddit.com/r/SmartThings/comments/g3vtwr/has_anyone_tried_to_root_the_smartthings_hub_v2/) to see if anyone has rooted the stock linux OS and it doesn't seem that anyone has openly hacked this hub.

I've also acquired a v3 hub to teardown as well

## The V3 Hub Teardown

{{< figure src="/images/2020/05/smartthingsv3hubpcb-1.jpg" caption="SmartThings V3 Hub PCB" >}}

## Hardware Comparison

<table class="table">
<thead>
  <tr>
    <th></th>
    <th>Hub V2</th>
    <th>Hub V3</th>
  </tr>
</thead>
<tbody>
  <tr>
    <th>CPU</th>
    <td>NXP IMX6<br>MCIMX6L2DVN10AB</td>
    <td>NXP IMX6UL<br>MCIMX6Y1DVM05AB</td>
  </tr>
  <tr>
    <th>RAM</th>
    <td>Samsung 4Gb<br>K4B4G1646D</td>
    <td>ESMT 2Gb<br>M15T2G16128A</td>
  </tr>
  <tr>
    <th>EMMC</th>
    <td>Samsung 4GB<br>KLM4G1FEPD</td>
    <td>Samsung 4GB<br>KLM4G1FEPD</td>
  </tr>
  <tr>
    <th>ZWAVE</th>
    <td>ZM5304-U module with Silicon Labs<br>SD3503A-CNE3</td>
    <td>Silicon Labs<br>SD3503A-CNE3</td>
  </tr>
  <tr>
    <th>Zigbee</th>
    <td>Silicon Labs<br>EM3587<br>Skyworks<br>SE2432L</td>
    <td>Silicon Labs<br>EFR32</td>
  </tr>
  <tr>
    <th>Wifi</th>
    <td>N/A</td>
    <td>Atheros Qualcom<br>QCA9379</td>
  </tr>
  <tr>
    <th>Bluetooth</th>
    <td>Nordic Semi<br>N51822</td>
    <td>Atheros Qualcom<br>QCA9379</td>
  </tr>
  <tr>
    <th>USB Hub</th>
    <td>N/A</td>
    <td>USB2512B</td>
  </tr>
  <tr>
    <th>Ethernet</th>
    <td>Microchip<br>KSZ8081</td>
    <td>Microchip<br>KSZ8081</td>
  </tr>
</tbody>
</table>



## 

