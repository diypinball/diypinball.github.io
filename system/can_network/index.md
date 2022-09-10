---
layout: page
title: CAN Network
use-site-title: true
---
DIYPinball uses a CAN bus network to connect our modules with a Linux computer. We use CAN for a few reasons:

* Reliability – as a differential bus with error correction, CAN allows us to reliably transfer data between the modules and the computer, safe from interference from noise sources, like the solenoids all over the playfield
* Availability – microcontrollers and other CAN devices are available from a wide variety of manufacturers, because CAN is widely used in automotive electronics
* Longevity – as a key automotive technology, CAN will be around for a long time
* Compatibility – CAN devices from different manufacturers work well together, and CAN tools are widely available for Linux

[Our protocol documentation can be found at our GitHub page.](https://github.com/diypinball/protocol)