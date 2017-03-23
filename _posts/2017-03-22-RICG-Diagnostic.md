---
layout: post
title: RICG ICRF Reflectometry Diagnostic on ASDEX Upgrade
categories: diagnostic troubleshooting
tags:
---

# RICG ICRF Reflectometry Diagnostic Documentation

---

[Start vncserver](#starting-vncserver)

[Running the diagnostic](#running-the-diagnostic)

[Troubleshooting](#troubleshooting)



---


## Starting vncserver

Starting and opening vncserver on ricg diagnostic:

```
ssh ricg@lnxricg.aug.ipp.mpg.de
vncserver -kill :3
vncserver :3
exit
```

Open vncviewer now from any terminal: ```vncviewer lnxricg.aug.ipp.mpg.de:3```



## Running the diagnostic

Running the ricg diagnostic during discharge days

It is easier to use the VNC session on the diagnostic machine to run the
diagnostic program, however, it can be ran on any ssh session to the same
machine.

Connect to the vncviewer

```
vncviewer lnxricg.aug.ipp.mpg.de:3
```





![VNC Screen][ricg_vncscreen]


## Troubleshooting



### Could not connect to vncviewer for the ricg diagnostic

Are you connecting to the correct address?

```
vncviewer lnxricg.aug.ipp.mpg.de:3
```


- VNC server may not be running or diagnostic computer may be off

Can you ping the diagnostic computer?

```
ping lnxricg.aug.ipp.mpg.de
```

If diagnostic computer does not respond may be powered off

#### Troubleshooting solutions

If computer is dead: [Start vncserver](#starting-vncserver)

If computer is alive:








[ricg_vncscreen]: /images/ricg_vncscreen.png
