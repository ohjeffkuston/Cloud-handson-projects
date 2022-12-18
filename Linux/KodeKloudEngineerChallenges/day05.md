<p align="center">
 <img src="../../img/GLN_Logo.png?raw=true" alt="GIFTED LANE Logo" width="50%" height="50%" />
</p>

# Linux Run Levels
Set the runlevel defualt to GUI for all the application servers.

## The Dig 

-  ♾️ Dig 1 > [Change default runlevel](https://www.itzgeek.com/how-tos/linux/centos-how-tos/change-default-runlevel-in-centos-7-rhel-7.html)
-  ♾️ Dig 2 > [How to check a current runlevel of your Linux system](https://linuxconfig.org/how-to-check-a-current-runlevel-of-your-linux-system)

## What I Ultimately Did

```bash
#log into the applicable server
$ ssh username@ip_address
```

```bash
#verify the current default runlevel of the system
$ runlevel




# **_OUTPUT_**:
# inittab is no longer used when using systemd.
#
# ADDING CONFIGURATION HERE WILL HAVE NO EFFECT ON YOUR SYSTEM.
#
# Ctrl-Alt-Delete is handled by /usr/lib/systemd/system/ctrl-alt-del.target
#
# systemd uses 'targets' instead of runlevels. By default, there are two main targets:
#
# multi-user.target: analogous to runlevel 3
# graphical.target: analogous to runlevel 5
#
# To view current default target, run:
# systemctl get-default
#
# To set a default target, run:
# systemctl set-default TARGET.target
```

```bash
#correct command for newer versions of Linux 
$ systemctl get-default




# **_OUTPUT_**:
multi-user.target
```

```bash
#list out targets supported by the server 
$ systemctl list-units --type=target




# **_OUTPUT_**:
UNIT                  LOAD   ACTIVE SUB    DESCRIPTION
basic.target          loaded active active Basic System
cryptsetup.target     loaded active active Local Encrypted Volumes
getty.target          loaded active active Login Prompts
local-fs-pre.target   loaded active active Local File Systems (Pre)
local-fs.target       loaded active active Local File Systems
multi-user.target     loaded active active Multi-User System
network-online.target loaded active active Network is Online
network.target        loaded active active Network
paths.target          loaded active active Paths
remote-fs.target      loaded active active Remote File Systems
slices.target         loaded active active Slices
sockets.target        loaded active active Sockets
swap.target           loaded active active Swap
sysinit.target        loaded active active System Initialization
timers.target         loaded active active Timers

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.

15 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'.
```

```bash
#correct command for newer versions of Linux 
$ sudo systemctl set-default graphical.target



# **_OUTPUT_**:
Removed symlink /etc/systemd/system/default.target.
Created symlink from /etc/systemd/system/default.target to /usr/lib/systemd/system/graphical.target.
```
```bash
#verify the default runlevel/target changed
$ systemctl get-default



# **_OUTPUT_**:
graphical.target
```

[< prev Day 4](day04.md)  |  [Home](../../..)  |  [Day 6 next >](day06.md)
