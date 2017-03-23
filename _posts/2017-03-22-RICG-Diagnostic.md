---
layout: post
title: RICG ICRF Reflectometry Diagnostic on ASDEX Upgrade
categories: diagnostic troubleshooting
tags:
---

#RICG ICRF Reflectometry Diagnostic


 ##Troubleshooting tips

###Could not connect to vncviewer for the ricg diagnostic

Are you connecting to the correct address? ```vncviewer lnxricg.aug.ipp.mpg.de:3```
VNC server may not be running or diagnostic computer may be off

Can you ping the diagnostic computer? ```ping lnxricg.aug.ipp.mpg.de```
If diagnostic computer does not respond may be powered off

#### Solutions

If computer is dead: [Start vncserver](#starting-vncserver)

If computer is alive:


### Starting vncserver
Starting and opening vncserver on ricg diagnostic:

```
ssh ricg@lnxricg.aug.ipp.mpg.de
vncserver -kill :3
vncserver :3
exit
```

Open vncviewer now from any terminal: ```vncviewer lnxricg.aug.ipp.mpg.de:3```
