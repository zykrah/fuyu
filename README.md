# Fuyu
 F12 TKL H87-Compat Type-C PCB for the Geon F1-8K, designed in KiCAD 6.0.
 
**Disclaimer: This board has not been prototyped yet.**
 
 > Fuyu: Winter

![image](https://user-images.githubusercontent.com/23428162/173242896-39ed07ce-ba2a-473d-a73b-6189538d4ace.png)

![image](https://user-images.githubusercontent.com/23428162/173242911-ce343f14-1dd3-4f5c-9337-3b3a7f97995a.png)


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

~~Note the keys that have LED indicator support.~~ Removed

![image](https://user-images.githubusercontent.com/23428162/173192900-2607653f-76fe-4558-9563-d40445c1b6b9.png)


## Snowflake LED

The LEDs are typically TX LEDs that you have to solder in (i.e. Snow Pro PCB), but with this PCB I made them SK6812 Mini-E Reverse-mount ARGB LEDs

- Reverse mount to keep as many components on the same side of the PCB as possible (for cheaper assembly)
- RGB and programmable
- NOTE: Since these are surface mounted onto the PCB, they'll probably leak light. Could be fixed with light pipes or something else used to isolate the led rays from eachother. 

Snowflake LED (Snow Pro PCB) [(source)](https://imgur.com/gallery/PWgU1so):

![image](https://user-images.githubusercontent.com/23428162/173171805-9e53ca19-3b54-4cbd-8b22-2a6411c695ef.png)

What it looks like close up on my PCB:

![image](https://user-images.githubusercontent.com/23428162/173194816-5e418f11-7e2e-4253-901c-96ff8c0e067c.png)

![image](https://user-images.githubusercontent.com/23428162/173194825-bf7cd126-6020-47d6-b501-67cb6bb582cb.png)


## Blocker
(These are photos of an F1-8K with a Snow Pro PCB, not this PCB)

Blocker attached, unattached, and outside the board [(source)](https://imgur.com/gallery/PWgU1so):

![image](https://user-images.githubusercontent.com/23428162/173171785-204a90aa-8525-4962-9c77-a5bbc544fd98.png)

![image](https://user-images.githubusercontent.com/23428162/173171855-8923517a-5afe-4d32-adc5-5c5c9a072711.png)


 What blocker looks like screwed in from the back:

![image](https://user-images.githubusercontent.com/23428162/173171709-e3288a28-84b4-4c09-b1b5-62d534b72170.png)
