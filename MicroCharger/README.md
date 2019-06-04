#Overview
There are 1 designs here
PCB located in Electronics/Tension
2 Plastic designs are located in Housing MKI-Snap or MKII-Screw

![tbltop](/MicroCharger/Images/DSC_1424.jpg "Table Top Charging")

PCB is designed in Kicad, but because of the NTC detection circuit used by the Campagnolo V3/V4 a modification was needed on how to drive the NTC, however this makes the boost voltage important.

Needed
Populated PCB (Tension Board, based on LTC4079 which is an expensive 3x3 10DFN chip)
MT3608 Micro USB boost set to 13.4v.
3D printed housing (MKI or MKII, your preference)
M5 4pin male "sensor cable"

MT3608 Epacket to Canada and this supplier worked well https://www.aliexpress.com/item/MT3608-DC-DC-Adjustable-Boost-Module-2A-Boost-Plate-2A-Step-Up-Module-with-MICRO-USB/32676502704.html?spm=a2g0s.9042311.0.0.6b784c4dcOo234)

M5 Cable https://www.digikey.ca/products/en/cable-assemblies/circular-cable-assemblies/448?k=&pkeyword=&sv=0&pv2344=3&sf=1&FV=24a8000f%2Cffe001c0%2C25300003&quantity=&ColumnSort=0&page=1&stock=1&pageSize=25 (yes, it's expensive!)

So build it then charge your bike, or check out my Tindie store to order one. In action it looks like this

![stem](/MicroCharger/Images/DSC_1468.jpg "Stem Charging")
![brake](/MicroCharger/Images/DSC_1457.jpg "Brake Charging")


#Build

*NOTE
There is a hack that is necessary. I you want to use this to charge standard 3S lithium it works great, but to use it with a Campagnolo V2/V3/V4 you need to modify the NTC. I'm going to post a new Tension V2 schematic when I update it.*
![Mod](/MicroCharger/Electronics/Images/MOD.jpg "EPS Mod")

The LTC pulses the NTC through a completion resistor from the NTC Bias line and reads back the value. The completion resistor is equvalent to the NTC nominal value. However, the EPS unit must read > 0.2v (I think, it's not exactly important) constantly on the NTC to enable charging. This is a charge detection circuit and it triggers the PU to stop functioning while charging as well as acting as a protection.

The LTC4079 wants to see 2v nominally at the NTC. We take away Bias control by NOT populating R5, but instead bias from the main power supply. So we bias the NTC using a 56k resistor to just over 2v from 13.4v. The NTCbias will still pulse but during the read the voltage is supplied elsewhere. The LTC4079 is providing a proper overheat / undertempm safety circuit while tricking the PU into enable charging. Didn't notice this on the original design since I didn't breadboard it. Small mod.

PCB / BOM (html) / etc are located in Electronics

Gerbers in subfolder Gerber. I made mine at PCBway (Rohs copliant, scared of lead) but OSHpark is good. Recommend 0.8mm board instead of 1.6mm to more easily mount LTC4079
Populated it should look like below
![Charge1](/MicroCharger/Electronics/Images/DSC_1434.jpg "EPS Charge 1")
![Charge2](/MicroCharger/Electronics/Images/DSC_1436.jpg "EPS Charge 2")

Make sure to thread the cable through the hole before soldering first if using MKII screw housing.

M5 4P pinout
Brown - Battery +V
Black - GND / Battery -V
White - NTC (NTC Thermistor other end to GND)
Blue - 12V aux, no longer used in EPS V3/V4

Cable is a 30 dollar CAD norcomp unit, but it's male to male so provides two ends for 2 chargers.

Solder the MT3608 USB boost to the back of the Tension board as shown in the two pictures above. There should be approximately 1mm spacing

#Housing
There are two housings. A snap clost unit and a screw closed.

The snap close snaps from the top but I didn't like the aesthetic finish.

Youtube video shows MKI (snap), photos show MKII (screw). 

![MKI](/MicroCharger/Housing/Images/MKI.jpg "MKI snap housing")
Drop PCB in from top, get latches under, press close. Friction Fit


![MKII](/MicroCharger/Housing/Images/MKII.jpg "MKII screw housing")
Need to be careful on gap between boards. Slide down, there are grooves to hold them in place so wiggle is the name of the game. Use M3 button head screws on the housing to close through the sides.
