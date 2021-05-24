+++
author = "Arran Short"
date = 2010-12-01T22:25:00Z
description = ""
draft = false
slug = "arduino-canbus-megasquirt-win"
title = "Arduino + canbus + megasquirt = win."

+++


<div></div><div></div>Well few weeks ago I had another look at getting my arduino and an mcp2515 to play nice, not knowing where to start I had a search to see if anyone had made a lib that was easy to understand and found [canduino](http://code.google.com/p/canduino/).

<div></div><div>Had a play with that and after a few emails back and forth to the owner I had some response from the 2515 Yay!</div><div></div><div>The next task was to configure the chip to receive messages so after reading the datasheet and the megasquirt can docs 500 times I got a response from the MS2.</div><div></div><div>After Some more tweeks to the code and plenty of head scratching I set one of my MS2 ecus to can id 1 and connected it to the arduino, switched em both on and hey presto the buffer full led lit up and , some data values were in the serial monitor 🙂</div><div></div><div><div>Now the code is a bit scruffy and getto but its working so far, I need to do some more reading on how to request the rest of the data but its a result.</div><div></div><div>Few pics of the setup as it is.</div></div><div></div><div><div>[![](http://2.bp.blogspot.com/_ONdiVIrgPJg/TPbL2Is5izI/AAAAAAAAAF8/JViUSN064K4/s320/CANSHIELD2.jpg)](http://2.bp.blogspot.com/_ONdiVIrgPJg/TPbL2Is5izI/AAAAAAAAAF8/JViUSN064K4/s1600/CANSHIELD2.jpg)![](http://2.bp.blogspot.com/_ONdiVIrgPJg/TPbLtUiU2RI/AAAAAAAAAF0/LLdVyMgd2n4/s320/CANSHIELD.jpg)</div><div></div><div>more soon!</div></div>

