# How to Program Loopy

In order to program Loopy, you need:
- an atmega328(p) chip
- an AVR programmer (an inexhpensive USBasp is perfectly fine, like the one [here](https://www.bitsbox.co.uk/index.php?main_page=product_info&cPath=140_161_163&products_id=1233))
- a 10 to 6 pin adapter if your programmer is not supplied with one, like the one [here](https://www.bitsbox.co.uk/index.php?main_page=product_info&cPath=140_161_163&products_id=2848)
- [avrdude](https://www.nongnu.org/avrdude/) correctly installed on your computer (installation are dependent on your OS of choice -- if you are on Mac, the easier way is to use [brew](https://formulae.brew.sh/formula/avrdude))

Once your computer is setup, you need to run three commands on your terminal.

The first command is mandatory to initialise the chip, and needs to be performed only on a blank chip. 

Once the initialisation is completed, the chip will work only if correctly connected to an oscillator: I strongly suggest to use the 6 pin header on the PCB to install the firmware.

## Fuses

If your chip has already a working copy of the firmware, you can skip this step. Otherwise, run:

```
avrdude -c usbasp -p atmega328p -B16 -U lfuse:w:0xFF:m -U hfuse:w:0xD9:m -U efuse:w:0xFF:m -U lock:w:0xFF:m
```

## Firwmare

The second command will upload the firmware on the chip:

```
avrdude -c usbasp -p atmega328p -U flash:w:<hex file location>
```

## EEPROM

The third command will setup the EEPROM, where the chip stores presets. Upload of the firmware will reset this location of memory: the following command will restore default values.

```
avrdude -c usbasp -p atmega328p -U eeprom:w:loopy.eep
```
