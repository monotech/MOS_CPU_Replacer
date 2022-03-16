# Monotech PCs - MOS CPU Replacer  
**Replace rare/expensive/unreliable MOS CPUs**  
6510 *(C64) (8500 is same as 6510)*  
6510T *(1551 floppy drive)*  
8501 *(C16, C116, Plus/4) (7501 is same as 8501)*  
8502 *(C128)*

Licensed under Creative Commons BY-SA: (https://creativecommons.org/licenses/by-sa/4.0/)

If you want one, check my store for stock: (https://monotech.fwscart.com)

The above four CPUs have the same dies I believe, with just different internal pads exposed to the DIP-40 pins.  
It's a standard 6502 die, with an added 8-bit bidirectional I/O port, tri-state bus buffers, and an AEC latch enable for 8501 mode.

This device uses a standard 6502 CPU, and implements the extra functions using discrete logic - no programmable parts.  
Standard 6502 CPUs are abundant and cheap, and produced by many manufacturers (Rockwell, UMC, Synertek, MOS, etc).

You can use a 65C02 or W65C02, but this is untested, and will cause compatibility issues with some software at the least, or not work at the worst.  
If using a WDC W65C02, you must cut jumper W.

Build instructions are on the back of the PCB. This document is for clarification if you find it unclear.

It may struggle to fit inside a C116 or Plus/4 due to height, so for these machines you should solder the 6502 directly to the module's PCB, or solder the module directly to the C116 or Plus/4 motherboard.  
For C16, height is not a problem.

It is tested to fit next to a PLA20V8 replacement in a 250407 board. Other oversized replacement boards may interfere and require installing the module in an extra socket to raise it up.

Status as of Rev1:
-

- 6510 config: :white_check_mark: Tested working in a C64.
- 6510T config: :grey_question: Not tested - I don't have a 1551.
- 8501 config: :white_check_mark: Tested working in a C16 and a Plus/4.
- 8502 config: :x: Works but has graphical glitches, likely due to a timing issue, so should only be built if you plan to help me diagnose this. For 8502, you must install a 2MHz-rated CPU (such as 6502A).

![alt text](https://github.com/monotech/MOS_CPU_Replacer/raw/main/Built%206510.jpg "Built in 6510 config")

Instructions:
-

1. Solder the solder-jumpers first (red dots).
1. Solder two 20-pin round-pin headers (cyan rectangles). (Not 21-pin!)
1. Solder the DIP-40 socket (yellow rectangles).
1. Install the 6502, and test the device.
    Don't install the device backwards or misaligned!

**The example picture below is for 8501 config (Jumpers: C, Headers: E). Steps 1 and 2 are different for the other three configs.**

![alt text](https://github.com/monotech/MOS_CPU_Replacer/raw/main/8501%20diagram.png "Diagram for 8501 config")

![alt text](https://github.com/monotech/MOS_CPU_Replacer/raw/main/Built%206510%20side.jpg "Built in 6510 config, side view")


**Troubleshooting**

- Double-check for shorts and that you soldered the correct solder jumpers.
- Crappy single-wipe IC sockets that Commodore used, can cause a lot of headache. Replace them.
- Your 6502 from Aliexpress/eBay may be fake, but I haven't encountered fake ones as of yet.
- Some models of 6502 may be incompatible - I haven't tested all of them.
- I haven't tested every combination of Commodore motherboard revision, PLA replacement, marginal IC, or timing-sensitive demo.
