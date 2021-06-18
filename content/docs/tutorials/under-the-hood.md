---
title: "Under the hood"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

# Under the hood

## Basics

The 3dasd 3D scanner is built around a
[Time-of-Flight](https://en.wikipedia.org/wiki/Time-of-flight_camera)
scanning LIDAR
([Garmin LIDAR-Lite v3](https://buy.garmin.com/en-US/US/p/557294))
that is capable of doing point-by-point
distance measurements. To scan the whole 3D space instead of a single point, the
3dasd scanner is rotating and tilting this LIDAR around the vertical and
horizontal axes while continuously taking and saving measurements.

These measurements are first saved in a custom file format
([.asdp]({{< relref "/docs/details/asdp-file" >}}))
that's essentially a list of
[spherical coordinates](https://en.wikipedia.org/wiki/Spherical_coordinate_system)
of the points. The
[point-convert](https://github.com/3dasd/point-convert)
utility helps converting from this format to common point cloud formats.

## Software components 

{{< container-image path="images/architecture.png" width=90% >}}

- [**lidar-driver**](https://github.com/3dasd/lidar-driver)
is the program running on the Arduino Nano. It is listening
for commands on the serial (UART) interface and controls the LIDAR and the
motors accordingly.
- [**lidar-client**](https://github.com/3dasd/lidar-client)
is the client running on the Raspberry Pi Zero that
connects to lidar-driver. It's a shell to send commands and also persists the
points cloud results coming back from the driver.
- [**point-convert**](https://github.com/3dasd/point-convert)
is a standalone application that converts from the `asdp`
format of the driver to `pcd` or `asc`.

{{< hint info >}}
**Need more details?**

Let me know what you're interested in! 
[Get in touch!]({{< relref "/docs/misc/contact" >}})
{{< /hint >}}
