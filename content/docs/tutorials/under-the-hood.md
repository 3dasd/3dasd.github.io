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