---
title: "Getting Started"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

# Getting started

This is an overview of the steps required for building your own scanner. See the
links below for the detailed instructions on every topic.

## Electronics

> See [Electronics]({{< relref "/docs/tutorials/electronics" >}}) for details.

Get the two PCBs:
- main PCB: [Gerber](https://github.com/3dasd/lidar-pcb/raw/master/scanner/v4/Gerber_v4-2021-05-17.zip),
[BOM](https://raw.githubusercontent.com/3dasd/lidar-pcb/master/scanner/v4/BOM_v4-2021-05-17_2021-05-17.csv),
[PCL](https://raw.githubusercontent.com/3dasd/lidar-pcb/master/scanner/v4/PickAndPlace_v4-2021-05-17_2021-05-17.csv)
- power supply: [Gerber](https://github.com/3dasd/lidar-pcb/raw/master/scanner-power-supply/v3/Gerber_v3-2021-04-01_2021-04-02.zip)

Order the parts that aren't soldered onto the main PCB:
[LCSC parts list](https://github.com/3dasd/lidar-pcb/raw/master/scanner-misc/v3/scanner_misc_LCSC_Exported_20210518_012325.xlsx).

Order the following:
- [Garmin LIDAR-Lite v3](https://buy.garmin.com/en-US/US/p/557294)
- [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
- [Arduino Nano](https://store.arduino.cc/arduino-nano)
- [2x NEMA 17 motors (with 1.8deg step angle)](https://www.omc-stepperonline.com/nema-17-stepper-motor/)
- [2x A4988 stepper driver boards](https://www.pololu.com/product/1182)
- 12V 2A Power supply (with 5.5*2.5mm barrel plug)


## Mechanics

> See [Mechanics]({{< relref "/docs/tutorials/mechanics" >}}) for details.

Almost all of the mechanical parts are 3D-printed. It takes around 20 hours to
print everything. You also need a couple nuts and bolts and also a few ball
bearings and magnets.

## Assembly

> See [Assembly]({{< relref "/docs/tutorials/assembly" >}}) for details.

Once you have everything it's time to assemble the scanner.

## Software

> See [Software]({{< relref "/docs/tutorials/software" >}}) for details.

With everything wired up you will need to install the 3dasd software components
on the scanner.
