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

This page walks you through obtaining and putting together all the electronics
components required for building a 3dasd scanner.

## Ordering everything

You need to get the following:
- two PCBs (main and power supply) with a bunch of electronic components
- two sets of NEMA 17 stepper motors and A4988 drivers
- Garmin LIDAR-Lite v3
- a Raspberry Pi Zero W
- an Arduino Nano
- a slip-ring
- a 12V 2A power supply
- wires for making the cables

### Getting the PCBs

{{< hint info >}}
**Check with me first!**

Since you can only order 5+ PCBs from JLCPCB, I happen to have some extras! I'd
be more than happy to send them your way so you don't have to order more PCBs
than you need.
[Get in touch!]({{< relref "/docs/misc/contact" >}})
{{< /hint >}}


You need to get two PCBs: the **scanner** and the **scanner-power-supply**. Both
designs are available in the [lidar-pcb](https://github.com/3dasd/lidar-pcb)
Github repository. You could order PCBs with the Gerber files stored there from
any manufacturer.

The following describes the process of ordering from JLCPCB. It's probably the
easiest option as the designs include parts that are availble in their webshop
so you can order assembled PCBs.

Start at the [JCLPCB order page](https://cart.jlcpcb.com/quote#EZ). Click on
`Add gerber file` and upload the Gerber file you've downloaded from
[here](https://github.com/3dasd/lidar-pcb/raw/master/scanner/v4/Gerber_v4-2021-05-17.zip).
The default options should work, you can leave them as is:

{{< container-image path="images/jlcpcb-order-1.png" width=50% >}}

Enable the `SMT assembly` option and select how many of the PCBs you want
assembled:

{{< container-image path="images/jlcpcb-order-2.png" width=50% >}}

Click `Confirm` to proceed to the next page where you need to upload the BOM
and CPL files downloaded from
[here (BOM)](https://raw.githubusercontent.com/3dasd/lidar-pcb/master/scanner/v4/BOM_v4-2021-05-17_2021-05-17.csv)
and
[here (CPL)](https://raw.githubusercontent.com/3dasd/lidar-pcb/master/scanner/v4/PickAndPlace_v4-2021-05-17_2021-05-17.csv).

{{< container-image path="images/jlcpcb-order-3.png" width=80% >}}

Hit `NEXT` to continue. You will be presented with a list of parts that JLCPCB
will solder onto the board. 

{{< details-image title="Inventory shortage for some parts?" open=false path="images/jlcpcb-order-4.png" width=80% >}}
Depending on their inventory you may find that some
parts are not available ("Inventory shortage"). You can try replacing these with
equivalent parts (connectors with different color, other brand) using the
magnifying glass icon in that row.

I've found that some items are avaible even if they're displayed as "Inventory
shortage". Try to search for the same part using it's part ID first (the
`CXXXXXX` number).

{{< /details-image >}}

JLCPCB isn't selling the following components, **it's okay that you see "No part
selected" for A4988, Raspberry Pi Zero, arduino_nano**:

{{< container-image path="images/jlcpcb-order-5.png" width=80% >}}

If you're happy with the parts list, hit `NEXT` to continue. Then review the
placement, it should look something like this:

{{< container-image path="images/jlcpcb-order-6.png" width=50% >}}

If you're satisfied with the list of parts, continue with `SAVE TO CART`. Now
you have the "main PCB" (`scanner`) in your cart. It's time to **repeat the same
process with the "power plug PCB" (`scanner-power-supply`)**. Go to the
[order page](https://cart.jlcpcb.com/quote#EZ) and do the same thing but this
time you should upload
[this Gerber file](https://github.com/3dasd/lidar-pcb/raw/master/scanner-power-supply/v3/Gerber_v3-2021-04-01_2021-04-02.zip).

The power plug PCB is too small for automated assembly. You won't be able to
enable `SMT assembly` and will need to separately order parts for this PCB.

Once you're done with the second PCB, finish your order with `Secure Checkout`.

### Connectors and Hall sensor

You can order the following from LCSC:

- `3x JST PH-6 male`: one for the LIDAR connector and two for the motors
- `2x JST PH-4 male`: for the motors
- `2x JST PH-3 male`: for the Hall sensors
- `28+x JST PH crimping terminals`: for the connectors above (get more, they're
easy to screw up!)
- `1x screw terminal`: for the `scanner-power-supply` PCB
- `1x 5.5-2.0MM DC plug`: for the `scanner-power-supply` PCB
- `2x TLE4905 unipolar Hall sensor`

Download the parts list from [here](https://github.com/3dasd/lidar-pcb/raw/master/scanner-misc/v3/scanner_misc_LCSC_Exported_20210518_012325.xlsx) and upload with the
[LCSC BOM tool](https://lcsc.com/bom.html#/upload)

Select "LCSC Part number" above the first column and "Quantity" above
"Order Qty." then click `Next`:

{{< container-image path="images/jlcpcb-order-7.png" width=50% >}}

Review the list of components. The quantities in the BOM should be enough to
complete the minimum of 5 `scanner-power-supply` PCBs you've ordered in the
previous step and to assemble a **single** scanner. Adjust the quantities if
you need more (or less)!

If you're happy with the list, hit `Add to Cart`, then go to your cart and
finish your order.

### Rest of the modules

Unfortunately the rest of the electronics are not available from a single
webshop, so you'll need to find the best place you can get them. Depending on
your location you can try ordering from Amazon, AliExpress or even better,
your favorite local electronics shop.

Here's what you need:

| Item | Notes |
|------|-------|
| [Garmin LIDAR-Lite v3](https://buy.garmin.com/en-US/US/p/557294) | `v3 HP` might also work but I haven't tested that. |
| [2x 1.8deg NEMA 17 stepper motors](https://www.omc-stepperonline.com/nema-17-stepper-motor/) | **Get two!** Make sure you get ones with **1.8deg step angle**. I've tested with **0.4Nm torque** motors, but that's probably overkill, especially for the Y axis. |
| [2x A4988 stepper drivers](https://www.pololu.com/product/1182) | **Get two!** Also available from other manufacturers. |
| [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/) | Make sure you get the **W kind** for WiFi access. Try to get one **without the header pins**, because you'll need those to be on the bottom. |
| [Arduino Nano](https://store.arduino.cc/arduino-nano) | Or anything compatible. |
| [Slip-ring](https://www.adafruit.com/product/736) | The chassis is designed to fit **SRC022A-6 or SRC022A-12** but can be modified relatively easily to fit something similar. If you can't get these, make sure yours have at least **2 wires** and is rated for at least **2 amps and 12 volts**. |
| [12V 2A DC power supply](https://www.amazon.com/UL-Listed-Supply-Adapter-Wireless-Monitor/dp/B071NCHTM8) | With **5.5*2.5mm** barrel DC plug. |
| 2 meters of AWG 24 wire | Should fit into the [JST PH](https://www.jst-mfg.com/product/pdf/eng/ePH.pdf) connector's crimping terminal. Preferably in four colors (red, black, blue, green). |
| Crimping tool for JST PH connectors | You might be able to assemble the cables without this ([video](https://www.youtube.com/watch?v=UD1h8ug3wQQ)) but it makes your life a lot easier if you can borrow one. |
| 40 pin male 2-row header pin for the Raspberry | If you were able to get a Raspberry without the pins. ([solderless connectors maybe?](https://www.adafruit.com/product/3662))|
| ball bearings |  |
| nuts & bolts |  |

## Soldering

TODO

- header pin to Raspberry
- RPi+Arduino+A4988 onto main PCB
- power-supply PCB

## Calibrating

### A4988 motor current tuning

{{< hint danger >}}
**WARNING!**
Don't hook up your motors to the board until you've completed this step!
{{< /hint >}}

You need to tune the A4988 drivers to match your stepper motors' current
ratings. There's a pot on the A4988 driver board that lets you adjust the
maximum current delivered to the motor. Power up the PCB plugging the 12V
power supply into the on-board plug, then follow
[this guide](https://ardufocus.com/howto/a4988-motor-current-tuning/).

## Cables

You need to craft five cables using the JST PH connectors. The LIDAR cable comes
with the LIDAR, you only need to replace the original connector on the non-LIDAR
side with a 6-pin JST PH connector.

Here's a video tutorial for crimping the terminals
[with](https://www.youtube.com/watch?v=BMtQDWCH4kQ)
and
[without](https://www.youtube.com/watch?v=UD1h8ug3wQQ)
a crimping tool.

Refer to the image below for the connections:

{{< container-image path="images/cables-diagram.png" width=90% >}}

{{< columns >}}
### Hall sensors

Solder three cables to the three legs of the sensor. Use insulation sleeves or
tape to make sure the three legs won't touch.

<--->

### Motors

Make sure you connect to the right places on the 6-pin side. 2nd and 5th places
are supposed to be empty.

<--->

### LIDAR

Cut the original connector from the LIDAR cable leaving around 18cm of the wires.
**Don't remove the connector that goes into the LIDAR!**

{{< /columns >}}

Here's how my cables turned out, but I'm sure you can do better! (;

{{< container-image path="images/cables-photo.jpg" width=50% >}}

{{< container-image path="images/cables-photo2.jpg" width=50% >}}