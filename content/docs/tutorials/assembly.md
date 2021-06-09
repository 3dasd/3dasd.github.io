---
title: "Assembly"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

# Assembly

Once you have all the mechanic components printed and all the electronics
soldered together, it's time to assemble the scanner.

## Power plug into chassis

This step isn't absolutely necessary but I highly recommend gluing the
`scanner-power-supply` PCB into its place inside the `purple` piece of the
chassis. Make sure the power plug is facing outwards.

{{< container-image path="images/power-supply-in-purple.jpg" width=50% >}}

## Chassis assembly

The following video walks you through the entire process of assembling the
chassis.

{{< youtube pa0eAv-M82A >}}

## Cables

Hook up everything using the cables that you've made.

{{< container-image path="images/cables-attached.jpg" width=50% >}}

- Push the Hall sensor with the **longer cable** into its hole on the plate
(`green` piece). Pay attention to the correct orientation, the **flat side should
be facing downwards**. Lead the cable back to the its connector (labeled `HALLX`)
tucking it in between the motor on the plate and the idle leg.
- Push the Hall sensor with the **shorter cable** into its hole on the idle leg.
Pay attention to the correct orientation, the **flat side should be facing
inwards**. Connect to the `HALLY` connector.
- Hook up **both motors** with their cables. The motor mounted on the plate (`green`
piece) should be connected to `MOTX` and the one on the driver leg to `MOTY`.
- Connect the Lidar to the `LIDAR` connector.


## Conclusion

Congratulations, you're done with the assembly! At this point you can power up
the scanner via the connector on the side of the chassis and continue with the
[software setup]({{< relref "/docs/tutorials/software" >}}).