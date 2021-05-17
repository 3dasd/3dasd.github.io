---
title: "Electronics"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

# Electronics

This tutorial walks you through obtaining all the electronics components
required for building a 3dasd 3D Scanner.

## Ordering everything

You need to get the following:
- PCBs (main and power plug) with a bunch of electronic components
- a Raspberry Pi Zero
- an Arduino Nano
- two sets of NEMA 17 stepper motors and A4988 drivers
- a few wires and JST connectors
- a slip-ring
- two Hall sensors
- a 2A power adapter

### Getting the PCBs

You need to get two PCBs: the **scanner** and the **scanner-power-plug**. Both
designs are available in the [lidar-pcb](https://github.com/3dasd/lidar-pcb)
Github repository. You could order PCBs with the Gerber files stored there from
any manufacturer.

The following describes the process of ordering from JLCPCB. It's probably the
easiest option as the designs include parts that are availble in their webshop
so you can order assembled PCBs.

Start at the [JCLPCB order page](https://cart.jlcpcb.com/quote#EZ). Click the
"Add gerber file" and upload the Gerber file you've downloaded from
(here)[https://github.com/3dasd/lidar-pcb/raw/master/scanner/v4/Gerber_v4-2021-05-17.zip].

{{< container-image path="images/jlcpcb-order-1.png" >}}

