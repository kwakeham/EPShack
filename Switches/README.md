There are 4 designs here
Button26 - Truncated design (only 90 degree) for 26mm bars
Button26f - Design with 22mm ID for stretch to 26mm bars
Button318 - Truncated design (only 80 degree) for 31.8mm bars
Button318f - Design with 28mm ID for stretch to 31.8mm bars

STL files should be printed such that the layers wrap around the bulk of the length (flat side edges down). Mirror the design in CAD (step) or 3d printing software to filp the edges. Don't print using supports. The overhang is very small and most machines are capable without support, but if you use support you'll have a issue getting it out.

Switches to be used are Panasonic EVQ-3PLA15
https://www.digikey.ca/product-detail/en/panasonic-electronic-components/EVQ-3PLA15/P122436CT-ND/7561421

357gram-force feels good inside, the switch makes a good audible click but outside a higher force seems to be desirable.

This design is NOT waterproof. I've attempted multiple methods to waterproof it, but no success yet. My plan is to revise this design with Tact switches that are waterproof and over 600gram-force, englarge the design for a PCB, and secure it with an adhesive.

Solder the small wires onto the edges of the switch and not the bottom or else the increase in height

![Switch Solder](/Switches/Images/Switch.jpg "Switch Soldering orientation")

Use your thumb to hold open the living hinge switch and push it in via the side. The cables should fall into the two channels on the side.

![Switch Install](/Switches/Images/Switch-Installing.jpg "Switch Soldering Installations")

Check the placement as shown below. It should sit in the little cutout well.

![Switch Install](/Switches/Images/Switch-Placement.jpg "Switch Placement")

You should feel a good click and it should be reliable. With the "f" designated ones you should be able to stretch it open a bit and still click. The 26f design generally won't work on a 31.8mm bar. The stretch is too much and the deformation forces it clicked.

The cable connection is fragile, this is why there will be a version 2 in the future. Securing the cables with some tape is useful.