---
layout: post
title: Why CANBus?
tags: [Updates]
Comments: false
---
One of the big questions we get is why we used CANBus to design the system. It’s normally used for automotive applications, so it’s certainly weird to see it in a pinball machine.

# What is CANBus?
First off, an introduction. CANBus is an automotive networking standard – it’s used throughout vehicles for everything from engine management to power windows and changing the station on the radio. Basically every little computer in a car – and there are a lot of them – connects and talks over CANBus. It’s what’s known as “multi-drop” – so a bunch of devices can connect over the same pair of wires – and doesn’t require a hub or switch like Ethernet does. It also includes features for detecting errors in transmission, and re-sending messages that got garbled.

There’s a lot more information on [CANBus over at Wikipedia](https://web.archive.org/web/20201130103441/http://en.wikipedia.org/wiki/Controller_area_network).

# Advantages for Pinball
There are a lot of advantages for using CANBus in our system:

* Error detection. This is built into the CANBus controllers, so it’s done for you – other systems, such as RS485, require that you do this in your own software.
* Collision detection. In a multi-drop network, sometimes two (or more) systems try to talk at the same time, and walk all over each other. In this case, you can’t make out what was being said, and each system needs to retransmit its message so that they can be heard. This is very tricky to implement on your own. CANBus not only handles the detection of this for you, but also the retransmission.
* Noise immunity – electrical noise, that is. With all sorts of solenoid coils being turned on and off rapidly, the inside of a pinball machine is a noisy environment for electronics. CANBus was designed for cars, which are even worse, so it should work fine for us. Systems like RS485 would also work for this, but others, such as I2C, would not.
* Linux support. Linux’s SocketCAN layer provides excellent CANBus support, which really reduces the amount of work we have to do to get a computer talking to CANBus.
* Hardware support. Basically every major microcontroller manufacturer makes not only CANBus devices, but also provides software to get you started with building support into your software. For those that don’t make the hardware, external chips are available that do the job.
* Addressing. Built into almost every CANBus device is the ability to have it detect when a message of interest comes across the network, and notify your software when that happens. This means that we can we can make a board that “hears” every message on the network but only “wakes up” when a message meant for it arrives, and the software can work on other things in the interim.

# Disadvantages for Pinball
There are also a few reasons for not using CANBus:

* Cost. Though this doesn’t add a lot, CANBus devices do definitely add a little in extra cost.
* Complexity. You need a fair bit of extra software to use CANBus – and the more software you add, the more that can go wrong. Further, it can be a tricky protocol to debug – there are specialized tools to help with this, but they cost money.

Having looked at both of these, though, we found that the cost wasn’t that much higher, and that the complexity shouldn’t be too hard to manage – Mike had access to some automotive CANBus equipment should we need it, and vendor-provided CAN examples are usually pretty well documented.

# Conclusion
After exploring the devices available, we landed on NXP’s LPC11C2x family, which integrate all of the CANBus circuitry into the microcontroller, eliminating most of our concerns. These parts even embed the CANBus driver code in ROM on the part, so you don’t have to write it yourself. A match made in heaven. Between that and the Linux support, we felt CANBus was a winner, and went ahead with it.
