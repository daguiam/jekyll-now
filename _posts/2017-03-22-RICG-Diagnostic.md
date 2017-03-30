---
layout: post
title: Documentation RICG ICRF Reflectometry Diagnostic on ASDEX Upgrade
categories: diagnostic troubleshooting
tags:
---



---

[Start vncserver](#starting-vncserver)

[Running the diagnostic](#running-the-diagnostic)

[Troubleshooting](#troubleshooting)



---

## Starting from shutdown


Assuming that diagnostic is completetly turned off (Diagnostic PC, Acquisiton System and Microwave Reflectometer)
ssh to any solaris computer on user ```ricg```.
For example:

```ssh ricg@sxaug35.aug.ipp.mpg.de```


Turn on  the Diagnostic PC + Acquisition System.
From home directory:

```bin/powerricg on```

Turn on Microwave Reflectometer

```bin/powerreflectometer on```


Wait a few seconds then ssh into the ricg diagnostic computer (lnxricg):

```ssh ricg@lnxricg.aug.ipp.mpg.de```

Start the VNC server on the ricg computer.
Due to a bug it is never properly shutdown or properly started at start up so you need
to do this everytime the computer shuts down:

```
vncserver -kill :3

vncserver :3

```

Exit both ssh and open a VNC viewer into ```lnxricg:3```

```vncviewer lnxricg.aug.ipp.mpg.de:3```

Insert password

You should already see the typical vncwindow:


![VNC Screen][ricg_vncscreen]


The main working directories are:

### Diagnostic operation directory

Directory path is:

``` ~/software/diag ```

Commands to execute diagnostic:

```./loop_diag.sh```

Runs the diagnostic acquisition in loop by waiting for the TS06 trigger.

```./run_test.sh```

Runs a single small acquisition with software trigger and plots the
acquired raw data from all the channels in order to check that everything is alright.
You can usually see the back-wall reflection and spurious signals from each antenna.

```python check_rawfiles.py```

Checks that the rawfiles inside the [rawfile directory](#local-rawfile-directory) are
valid (shotnumber>32734) and that they are in the stored in the correct AFS path.
If the script confirms everything is alright, it is ok to assume that you can delete
the local copies.

Otherwise you have to check that the correct files are stored in AFS.


### Local rawfile directory

```~/raw_data_dump/```

has the temporary local cache of rawfiles that are transferred to AFS.
You should check that the rawfiles are already stored in AFS by running ```python check_rawfiles.py#####``` from [**Diag** directory](#diagnostic-operation-directory)





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
