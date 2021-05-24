+++
author = "Arran Short"
date = 2016-12-17T12:30:00Z
description = ""
draft = false
image = "/images/2017/04/20161216_211431.jpg"
slug = "ive-been-meaning-to-try-new-cortex-m0"
title = "DIY 50mil (1.27mm) to 100mil (2.54mm) adapter for atatmel ice"

+++


I’ve been meaning to try the new cortex m0 chips by atmel but was put off by the high programmer price, fortunately, they now sell a bare version known as **atatmel-ice-pcba** with no case or cables. So after the initial shock of how small the cortex debug connector is I set off to find a cheap way to break this out to 0.1″ headers.

 Fortunately a soic chip has the same footprint as the SMD variant of the mating connector. Flicking through the CPC site to find anything 1.27mm (50mil) I found some soic to dip adapters, after checking the data sheets to confirm it would work I made the order

<div class="post-img">
<a href="/content/images/2017/03/20161216_211209.jpg" target="_blank">
<img src="/content/images/2017/03/20161216_211209.jpg" />
</a>
</div>

<div class="post-img">
<a href="/content/images/2017/03/20161216_211243.jpg" target="_blank">
<img src="/content/images/2017/03/20161216_211243.jpg" />
</a>
</div>

<div class="post-img">
<a href="/content/images/2017/03/20161216_211256.jpg" target="_blank">
<img src="/content/images/2017/03/20161216_211256.jpg" />
</a>
</div>

<div class="post-img">
<a href="/content/images/2017/03/20161216_211256.jpg" target="_blank">
<img src="/content/images/2017/03/20161216_211431-1.jpg" />
</a>
</div>

<table>
<tbody>
<tr><th>Description</th><th>CPC code</th><th>Manufacturer code</th></tr>
<tr>
<td>AMPHENOL FCI Minitek127 10way SMT RECEPTACLE</td>
<td><a href="http://cpc.farnell.com/amphenol-fci/20021321-00010c4lf/receptacle-vert-1-27mm-smt-10way/dp/CN18263">CN18263</a></td><td>20021321-00010C4LF</td>
</tr>
<tr><td>PROTO ADVANTAGE SOIC-14 to DIP-14 Adapter</td><td><a href="http://cpc.farnell.com/proto-advantage/pa0003/adaptor-soic-14-to-dip-14-1-27/dp/PC01795">PC01795</a></td><td>PA0003</td></tr>
</tbody>
</table>

