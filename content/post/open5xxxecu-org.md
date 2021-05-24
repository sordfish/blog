+++
author = "Arran Short"
date = 2019-05-13T10:22:44Z
description = ""
draft = false
slug = "open5xxxecu-org"
title = "open5xxxecu.org"

+++


So I noticed that this domain has been left to expire as the project hasn't really taken off.

With RusEFI and Speeduino getting traction it seems there is still interest for an open ECUs but nothing is really covering the higher end ECU market.

I've been looking at starting my own OSEK/AUTOSAR based open ECU using the Erika RTOS but haven't decided on what hardware is best to use.

I've got my eye on the following CPUs

**ATSAMC21N**
Pros
 - Cheap
 - 5V ADC
 - CANFD
 - Lots of code examples from Arduino SAMD21 Zero
 - Automotive grade

Cons
 - Cortex M0
 - No crank angle ASIC/CPU

**TI TMS570**
Pros
 - FAST
 - Cortex R lock step
 - Angle Clock

Cons
 - Faffy dev enviroment
 
**MPC5xxx** 

Pros
 - Defacto processor for automotive ECUs

Cons
 - TPU hard to program



I've registered the domain but I'm not sure of my plans yet but my Open ECU project might involve the MPC5xxx platform in some form as there are OEM ECUs that could be a complete DEV kit e.g. Delco E83 for not a lot of money.



