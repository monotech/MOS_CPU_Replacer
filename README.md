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

- : : 6510 config: Tested working in a C64 and C64C with a wide range of software. In one scenario, it was discovered that it causes graphical glitches when used in a C64 with a C0pperdragon video conversion device (which watches the VIC-II pins). This was on Rev1. It may or may not be resolved on Rev2.
- : : 6510T config: I don't have a 1551, but someone else has done some basic testing in their own, and it works.
- :x: 8501 config: Tested working in a C16 and a Plus/4, but it has been found that at least one program crashes on a 64K-modded C16, that doesn't crash with a real 8501.
- :x: 8502 config: Works but has graphical glitches, likely due to a timing issue, so should only be built if you plan to help me diagnose this. For 8502, you must install a 2MHz-rated CPU (such as 6502A).

Known issues:
-

- A local enthusiast has discovered that using this adapter in 8501 config in their 64K-modded C16, results in Slipstream (https://psytronik.itch.io/slipstream) hanging, and causing resets to stop working (need a power cycle). One other person has confirmed this, and confirmed it doesn't happen with a real 8501, so the issue is with the MOS CPU Replacer. I will look into possible causes and update this page if a solution is found. Testing the C64 version of Slipstream in a C64 works fine with either a real 6510 or the MOS CPU Replacer in 6510 config.
- One user reported that it causes graphical glitches when used in a C64 (6510 config) with a C0pperdragon video conversion device (which watches the VIC-II pins), but works well otherwise. This was on Rev1. It may or may not be resolved on Rev2.
- I am sometimes working on improving the device, and hopefully reaching 100% compatibility.


---
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

- See the Known Issues section above.
- Double-check for shorts and that you soldered the correct solder jumpers.
- Crappy single-wipe IC sockets that Commodore used, can cause a lot of headache. Replace them.
- Your 6502 from Aliexpress/eBay may be fake or faulty. Sometimes they are actually 65C02 that have been re-marked as 6502.
- Some models of 6502 may be incompatible - I haven't tested all of them.
- I haven't tested every combination of Commodore motherboard revision, PLA replacement, marginal IC, or timing-sensitive demo.

**Changelog**

- Rev 2: used an unused HCT126 gate to buffer the PHI2 output, improving compatibility. Only affects 6510 and 6510T configurations which actually have a PHI2 output.
- Rev 1: First version
