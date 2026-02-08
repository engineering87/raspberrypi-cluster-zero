# ClusterHAT setup & control

This document covers **only** the minimal steps and commands needed to control a ClusterHAT from the controller Pi (power on/off nodes, LEDs, hub).  
Commands are taken from the official ClusterHAT/ClusterCTRL docs.

## 1) Hardware assembly (controller + HAT + nodes)

Follow the official assembly sequence (standoffs → mount HAT → secure → connect USB cable between controller and ClusterHAT → plug nodes P1–P4).

## 2) Software image (recommended)

ClusterCTRL provides pre-created images for the **controller** and each node (P1/P2/P3/P4). Use one of their setup methods (Simple/Intermediate/Manual).

## 3) Verify USB hub visibility (optional but useful)

The ClusterHAT docs describe checking the USB topology using `lsusb -t`.

```bash
lsusb -t
```

Also note the documented port mapping shown in the ClusterHAT control docs (USB “Port 4/3/2/1” map to P1/P2/P3/P4).

## 4) Power control (from the controller)

The following commands are documented for powering nodes on/off from the controller.

```bash
# Turn on all nodes (P1–P4)
clusterctrl on

# Turn off all nodes (P1–P4)
clusterctrl off

# Turn on a single node
clusterctrl on p1

# Turn on a subset of nodes
clusterctrl on p1 p3 p4

# Turn off a subset of nodes
clusterctrl off p2 p3
```

## 5) ALERT LED

Documented commands to toggle the ALERT LED.

```bash
clusterctrl alert on
clusterctrl alert off
```

## 6) ClusterHAT v2.x only: USB hub power + LEDs

The ClusterHAT docs list these as **v2.x** commands (not available on v1.x).

```bash
# USB hub power
clusterctrl hub on
clusterctrl hub off

# Power + P1–P4 LEDs (does not disable ALERT LED)
clusterctrl led on
clusterctrl led off
```

## 7) EEPROM write-protect (only if needed)

Documented write-protect toggles.

```bash
clusterctrl wp on
clusterctrl wp off
```
