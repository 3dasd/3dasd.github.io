---
title: "Usage"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

# Usage

When you **power up** the scanner from the 12V power supply it automatically
**connects to your WiFi** network. You can connect to the scanner from your
computer via **SSH** and launch a command line application where you can **send
commands** to the scanner.

The point clouds taken by the scanner are saved on the scanner itself and can
be downloaded to your computer via the same SSH connection.

{{< container-image path="images/how-it-works.png" width=80% >}}

{{< hint info >}}
**Remote access**

The scanner and your computer don't necessarily have to be on the same WiFi
network. If you set up the network connectivity (e.g. via VPN or reverse SSH
tunnel), then you can access the scanner remotely.

{{< /hint >}}

## General use-case

Here's how you run a single scanning session:

1. Power up the scanner.
2. Connect via SSH.
3. Launch `lidar-client` and send the commands:
    1. `e`: enable motors
    2. `h`: go home
    3. `y-50`: tilt down a bit
    4. `r200`: scan until 200th row
4. Wait for scan to finish.
5. Download results in `asdp` format via SCP
6. Use `point-convert` to turn `asdp` into `pcd` or `asc` format.
7. Open the point cloud in your favorite 3D software!
