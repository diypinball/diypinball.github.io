---
layout: page
title: The System
use-site-title: true
---
Our pinball system differs from the traditional approach. In older machines, usually one or two circuit boards control the machine. These boards are very large – and can be expensive to build as a result.

FIXME photo of backbox

Our approach is to use a bunch of smaller boards, which are networked together.

FIXME photo of block diagram

This has a few benefits:

* Smaller boards are cheaper to make than large ones.
* We can network as many – or as few – modules together as we need to make a pinball game. With a single large board, you need different designs for games that have more lights or solenoids than others. By using a single, common module, and just using more of them, we can use the same design for any size of pinball machine.
* To repair a failed module, we can swap out just the module that failed – not the whole system. We only need to fix or replace the actual broken part.
* The boards can be upgraded with new technology without changing the whole system. As parts become obsolete, we can redesign the individual modules using newer components. If the interface is kept the same as older versions, then newer modules can be swapped into older machines, without changing their software

We use a [CAN bus](https://en.wikipedia.org/wiki/CAN_bus) network to link our modules together, along with a Linux-based computer – usually a Raspberry Pi. On the computer, we run the game logic through the Python-based [Mission Pinball Framework](https://missionpinball.org/).

Here are some details on some of the components of our system

* [CAN Network](can_network)
* [CAN Interface Board](can_interface_board)
* [Base Board](base_board)
* [Score Display Board](score_display_board)