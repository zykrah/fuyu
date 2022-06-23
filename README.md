# Fuyu
 F12 TKL H87-Compat Type-C PCB for the Geon F1-8K, designed in KiCAD 6.0.
 
**This board has now been prototyped! See IRL images below.**
 
 > Fuyu: Winter

Photos/Renders (I try to keep them up to date, but they may not always be):

![image](https://user-images.githubusercontent.com/23428162/173288582-8047ac55-1b19-4a1d-a59a-7c4d466213c2.png)

![image](https://user-images.githubusercontent.com/23428162/173288587-bcbf432d-172f-419a-8a8b-ff128b5090c1.png)

![image](https://user-images.githubusercontent.com/23428162/173289100-b6df0503-4f23-4a3a-a53e-c50392240920.png)

IRL photos of rev1 protos (I don't actually own an F1-8K but I'll upload photos of my PCB in one when I get the chance):

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
You can find the firmware [here](https://github.com/zykrah/vial-qmk/tree/rp2040/keyboards/zykrah/fuyu). As of writing, the board runs the rp2040 branch/fork of vial-qmk. I will update this to use the official QMK implementation of RP2040 when it releases.


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

![image](https://user-images.githubusercontent.com/23428162/173289614-038f76c7-7c96-496d-881e-9553b830d751.png)

![image](https://user-images.githubusercontent.com/23428162/173289637-46e462bf-1fc8-4964-b973-eec148557887.png)


## Blocker
(These are photos of an F1-8K with a Snow Pro PCB, not this PCB)

Blocker attached, unattached, and outside the board [(source)](https://imgur.com/gallery/PWgU1so):

![image](https://user-images.githubusercontent.com/23428162/173171785-204a90aa-8525-4962-9c77-a5bbc544fd98.png)

![image](https://user-images.githubusercontent.com/23428162/173171855-8923517a-5afe-4d32-adc5-5c5c9a072711.png)


 What blocker looks like screwed in from the back:

![image](https://user-images.githubusercontent.com/23428162/173171709-e3288a28-84b4-4c09-b1b5-62d534b72170.png)
