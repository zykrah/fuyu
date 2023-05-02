# Fuyu
 F12 TKL H87-Compat Type-C PCB for the Geon F1-8K, designed in KiCAD 6.0.
 
 > Fuyu, meaning Winter (in Japanese ofcourse)

## Availability

**UPDATE: I have partenered with Geon to make these available for purchase! As of writing, they are available [here on Geon's store](https://geon.works/products/fuyu-pcb-for-f1-8k).**

**They are also [available on CustomKBD](https://customkbd.com/products/fuyu-pcb-for-f1-8k).**

![image](https://user-images.githubusercontent.com/23428162/188166517-08c0ee08-2d27-457b-b19a-0e0a8b118f37.png)

![image](https://user-images.githubusercontent.com/23428162/210485233-4719a329-8249-44ba-88f0-81bde1015c26.png)

## Photos/Renders 
I try to keep them up to date, but they may not always be:

![image](https://user-images.githubusercontent.com/23428162/173288582-8047ac55-1b19-4a1d-a59a-7c4d466213c2.png)

![image](https://user-images.githubusercontent.com/23428162/173288587-bcbf432d-172f-419a-8a8b-ff128b5090c1.png)

![image](https://user-images.githubusercontent.com/23428162/173289100-b6df0503-4f23-4a3a-a53e-c50392240920.png)

IRL photos of rev1 protos (See further down the page for more photos):

![image](https://user-images.githubusercontent.com/23428162/175324271-d6ced88e-8490-4731-be7d-b73aabc4a0a7.png)

![image](https://user-images.githubusercontent.com/23428162/175324737-971ca447-1d73-4948-a0af-c8c13dcbce4b.png)

![image](https://user-images.githubusercontent.com/23428162/175324347-67ed2a7c-4865-4b66-b694-503b91dba786.png)


## Features
- Fits the h87(c) standard (means it should also be compatible with the F1-8X (non-f13))
- Uses the RP2040 MCU (new), with 16MB of external flash
- Has the 5 extra keys required for the F1-8X numpad/blocker (See below)
- Has programmable 7 SK6812 Mini-E ARGB LEDs for the "snowflake" (See below)
- Has 34 underglow LEDs (WS2812(C)-2020 LEDs)
- Multi-layout (see below)
- BOOT pins/header for getting into bootloader (short the pins while plugging in) if [bootmagic](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_bootmagic.md) isn't available . Acessible from both sides of the PCB, even when PCB is built in a keyboard. Just remove the **END key/switch** to access it.
- SWD header for debugging
- ESD chip (SRV05-4) to prevent damage from electrostatic discharge
- Polyfuse to prevent overcurrent
- Optimized for manufacturing and assembly with JLCPCB
- Bonus: Curved traces and teardrops

> Also, `Sleep-Lib` is just the library by [Sleepdealer](https://github.com/Sleepdealr), used in his [RP2040 Design guide](https://github.com/Sleepdealr/RP2040-designguide).


## Firmware
~~As of writing, the board runs the rp2040 branch/fork of vial-qmk. I will update this to use the official QMK implementation of RP2040 when it releases.~~

~~UPDATE: RP2040 support has recently made it into QMK's `develop` branch. It will be fully merged to `master` by Q3 this year. Until then, the official maintainer of vial doesn't intend to merge those changes into their vial repo either, so I have made my own fork for the boards. When vial-qmk is officially updated to use QMK's implementiation of the RP2040, I will update this page once again linking to that, assuming I get the board merged into the official repo too.~~

~~UPDATE 2: RP2040 support has now been merged to `master`. I have not yet submitted PRs to merge the FUYU into the official qmk/vial-qmk yet. For now, you can find the up-to-date firmware [here](https://github.com/zykrah/vial-qmk/tree/vdev-zykrah/keyboards/zykrah/fuyu).~~


You can find the up-to-date VIAL firmware [here](https://github.com/zykrah/vial-qmk/tree/vdev-zykrah/keyboards/zykrah/fuyu). This firmware utilises [VIAL](https://get.vial.today/download/). Download and run it, and it should automatically detect the board. (Boards sold on Geon's store should come with VIAL firmware installed by default)

**UPDATE**: The board is now also in [qmk master](https://github.com/qmk/qmk_firmware/tree/master/keyboards/zykrah/fuyu). (This particular version will only be VIA compatible). It should automatically be detected in VIA if you want to use that instead.

![image](https://user-images.githubusercontent.com/23428162/175326950-fc93dad0-5560-4668-9928-25309f9d02e1.png)

### Flashing

To flash an RP2040 board, you need to get it into bootloader mode. You can do this in two ways:
1. If the board already has functioning QMK firmware on it, you can simply hold the top left key (ESC) while plugging the board in
2. If for some reason the first method doesn't work, you can enter bootloader by shorting the `BOOT` pins located underneath the END key while plugging the board in

The board will appear as a drive on your computer as `RPI-RP2`.

![image](https://user-images.githubusercontent.com/23428162/177196278-5fe35d26-c702-4454-9853-49a5270c35e3.png)

Then you just need to move/copy/drag the firmware file (`.uf2` file) into that drive, and it should flash.

## WIP/Ideas
- ~~Add underglow LEDs~~ DONE
- Add more underglow LEDs to make the lighting more consistent
- Add removable USB port + JST/Daughterboard connector
- ~~Add ISO support (enter and pipe keys)~~ DONE
- Add more split space support/bottom row layout options
- Add layout indicators to the silkscreen of the pcb
- Do something more special with USB shield/ground connection (currently shield is connected straight to ground)
- Break out pins for 3v3, 5v, spare GPIO
- More via stitching

## Multi-Layout Support

![image](https://user-images.githubusercontent.com/23428162/177591986-058a0617-9812-4835-b993-37c275612ae7.png)


## Snowflake LED

The LEDs are typically TX LEDs that you have to solder in (i.e. Snow Pro PCB), but with this PCB I made them SK6812 Mini-E Reverse-mount ARGB LEDs

- Reverse mount to keep as many components on the same side of the PCB as possible (for cheaper assembly)
- RGB and programmable
- NOTE: Since these are surface mounted onto the PCB, they'll probably leak light. Could be fixed with light pipes or something else used to isolate the led rays from eachother. 

Snowflake LED IRL (NOTE: brightness has been modified in firmware to lower light leak):

![image](https://user-images.githubusercontent.com/23428162/177195014-1e64f7b9-a0cc-4141-bd91-7be9d9dd1cc2.png)

What it looks like close up on my PCB (KICAD preview/renders):

![image](https://user-images.githubusercontent.com/23428162/173289614-038f76c7-7c96-496d-881e-9553b830d751.png)

![image](https://user-images.githubusercontent.com/23428162/173289637-46e462bf-1fc8-4964-b973-eec148557887.png)


## Blocker

Blocker attached, unattached, and outside the board (test fit photos courtesy of my friend):

![image](https://user-images.githubusercontent.com/23428162/177194600-d748172b-6a8c-4ced-abd9-ef7ae97c55a8.png)

![image](https://user-images.githubusercontent.com/23428162/177194704-49909b1c-3749-4116-a4dd-4b31962de60d.png)

![image](https://user-images.githubusercontent.com/23428162/177195422-780b1844-a2f0-4927-a5e0-55bd36dd5747.png)

 What blocker looks like screwed in from the back:

![image](https://user-images.githubusercontent.com/23428162/177195448-bddc7c51-15eb-425e-a64b-a30716326048.png)
