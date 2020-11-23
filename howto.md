# How To Build Loopy

Loopy is a medium complexity project for the occasional DIY-er, while it should be fairly straightforward for an avid one.

## Step 1: Drilling

In my opinion, the hardest part of the build process is drilling the enclosure, due to the large number of holes.

My method is the following:
- print the drilling template specific for your PCB
- attach the drilling template to the enclosure **being as precise as you can**
- use a good quality center punch to set a drilling guide for each hole. It is very important especially for the holes on the front panel
- drill every hole with a pilot bit (either 2mm, 2.5mm or 3mm works, but I usually tend towards the smaller size)
- work your way up through the holes up to the right size for your components, but don't overdrill the front panel 5mm LEDs holes
- slightly overdrill the holes on the backpanel, as this will make easier to insert the PCB at the end
- clean the enclosure and get ready for soldering

# Step 2: Soldering

[...]

# Step 3: Finish it up

[...]

### Components Guide

#### Relays

Loopy uses miniaturised signal relays. Some of the possible options are:

- Zettler AZ850-5
- NEC EA2-5NU
- Fujitsu A-5W-K
- Panasonic/NAIS TQ2-5V

Some of these models are discontinued, but any other signal relay with the same pinout will work just fine. I have uploaded a few datasheets for consultation in the `datasheets` folder.

#### LEDs 

Any 5mm LED work in this project, but you want to be careful with the type you use and the resistors you couple with it. 

I have personally used 400mcd LEDs like the ones in [this link](https://www.switchelectronics.co.uk/blue-5mm-led-diffused-400mcd-30) with an 820R resistor, however you want to use a larger resistor value if you use high brightness LEDs, or you'll end up with a front panel too bright to be looked at without problems.

#### Audio Jack

I suggest to use the REAN/Neutrik NYS2152, but the REAN/Neutrik NYS215 works too (stereo): PCB is designed around this footprint and the schematic use stereo jacks, so an additional (unused, unconnected) hole is available on the PCB and this should give you some flexibility in the source of the part.
Drawing diagram for these jacks is in the `datasheets` folder.