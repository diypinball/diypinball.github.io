---
layout: post
title: Status Update: August 26, 2013
tags: [Updates]
Comments: false
---
The three of us got together to try out the rest of the fixed base boards, and try and get some game logic done. The faults from Friday were resolved:

1. A miswired switch was properly wired
2.  A burnt out lamp was replaced (though we could do with slightly brighter replacements)
3. Board 3 Solenoid 6’s output was fixed (the MCU pin wasn’t properly soldered)
4. The dual-lamp display issue on Board 1 was fixed (one of the MOSFET drive transistors was populated with a PNP rather than an NPN, so it was always on)
5. We tested the fixes, and found them to be working. We then got some game logic going – pop bumpers, kickers, and the newly-wired start button was set up to dispense a ball. The solenoids are still being driven from a 30V printer power supply, so we’d like to get up to 36V to get a bit more oomph from them, but it’s playable now.

Alan’s working on getting photos from this night, but did manage to post the following video:

<iframe width="600" height="363" src="http://www.youtube.com/embed/pAP4J0mwOJ8?rel=0" frameborder="0" allowfullscreen=""></iframe>

Still to be done:

1. Power supply sequencing
2. Wiring in the power entry module
3. Lights
4. More game logic
5. Power supply sequencing
6. Sound
7. Score display modules

Overall, though, we’re looking really good for [Mini Maker Faire Ottawa](http://www.makerfaireottawa.com/) this weekend.