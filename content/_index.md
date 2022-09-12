---
title: Introduction
type: docs
---

# 3dasd

Welcome to `3dasd.com`, home for a fully open-source DIY room-scale 3D scanner!

{{< hint info >}}
**No longer maintained**  
I'm not maintaining this site and this whole project anymore. If you happen to
have any questions, you can still reach me via the
[contacts]({{< relref "/docs/misc/contact" >}}) though.
{{< /hint >}}

## What's this all about?

This site is here to help you build a room-scale 3D scanner like this:

{{< container-image path="images/scanner-photo-2021-06-03.jpg" width=80% >}}

## Who is this for?

The goal is to make this **as accessible as possible**! However, at this point you
need to have access to a 3D printer, do some very basic soldering and assemble
a few cables (JST connectors).

Everything you see is open-source and free (as in free beer **and** free
speech). I'm more than happy to hear your ideas and incorporate your feedback.
Shoot me an
[email or find me on Discord]({{< relref "/docs/misc/contact" >}}), open a
[GitHub](https://github.com/3dasd)
issue or **pull-request**! Get involved! (;

## Is it any good?

[Yes](https://about.gitlab.com/is-it-any-good/)! Well, okay, it depends. (:

This is not a production-grade scanner, it's way too slow, loud and just not
accurate enough for most real-world applications. It could be a great entry into
the world of 3D scanning though.

Check out the [examples page](https://examples.3dasd.com) for scans taken
with the scanner.

## Is it expensive?

It tries not to be. (:

Prices will depend on a lot of factors. Do you 3d-print your own pieces? Where
do you order the electronic components from? Do you trust the cheapest modules?
Do you
[get in contact]({{< relref "/docs/misc/contact" >}})
with me so I can send you a leftover PCB? (;

A very-very rough estimate would be around **350 USD** with the bulk of it being
the LIDAR sensor.

## Acknowledgements

This project started off as the combination of these Youtube videos:

- ["Making a Lidar scanner in the home shop with a lathe, a pair of STM32s, and a Garmin Lidar Lite"](https://www.youtube.com/watch?v=KGN82vLjguI)
by **David Cambridge**. This was the original inspiration for 3dasd.
- ["3D Printed DSLR Camera Pan Tilt Mount (Arduino/Stepper Driven) 2020"](https://www.youtube.com/watch?v=uJO7mv4-0PY)
by **isaac879**. This has inspired the mechanical design and also parts of the
software was borrowed from here.