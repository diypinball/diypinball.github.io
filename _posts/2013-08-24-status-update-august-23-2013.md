---
layout: post
title: Status Update - August 23, 2013
tags: [Updates]
Comments: false
---
This was our first time firing up the machine since Maker Faire Detroit, and thus the first time with the Solenoid MOSFETs replaced with properly-rated units. We re-installed the boards and bridged the 12V supply to the 50V input, at which point the system promptly shut down. Repeated attempts led to some troubleshooting – is the 50V rail now shorted? A quick trip to the corner store to replace the DMM’s battery, and… no, that’s not it.

It took about a half hour of troubleshooting before it dawned on Mike and I that it was probably inrush current. There’s a 220uF capacitor (value chosen by guessing) on the 50V rail for the solenoids, and attaching that to the 12V rail after startup probably drew enough current to make the power supply freak out and shut down. Driving the 50V input off of a 12V battery worked fine for testing the solenoid outputs with the LEDs, though.

Next, we wired up two 12V car batteries in series to try and test the solenoids. The solenoids did actuate on 24V, but were sluggish, and latches on drop targets didn’t engage. So 24V isn’t enough.

<iframe width="560" height="315" src="https://www.youtube.com/embed/KCbP3j1cWS4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

We tried it with a 30V 3A power supply, originally for an HP printer, that I picked up at a computer store when they were closing. That was sufficient for some decent kick on the flippers, and for the drop targets to reset.

Around this time we powered down the system and found an error in doing so. If the 12V supply drops before the solenoid power supply does, the solenoids all engage. Oops. There will be a follow up post on this later, but it’s kind of a serious issue. We’re working on a power supply sequencing system to make sure that the solenoids are only powered when the rest of the system is, too.

We then moved on to mapping which switch, lamp and solenoid was attached to which output / input on our boards. This involved me looking through my [Adafruit Video Glasses](http://www.adafruit.com/products/1452) (we had no monitor), typing commands on a keyboard, and Mike writing down what turned on. Mike mocked me incessantly for how I looked.

FIXME ADD PHOTOS FROM https://web.archive.org/web/20180924162424/http://diypinball.ca/2013/08/status-update-august-23-2013/

We found the following issues:

1. Turning on one lamp on board 1, turned on two
2. Board 3 Solenoid 2 didn’t do anything – no actuation, no light
3. One switch was wired such that it always appeared closed
4. A few switches were dirty and/or misaligned
5. A couple lamps were out

In addition to those, we still had to sort out our power cord issues, and a couple nagging firmware issues. Annoying, to be sure, but better than the “no solenoids work” situation we had in Detroit.

We ended the day by writing some basic code to run the flippers from the buttons, which worked quite nicely.

I love it when a plan comes together.