**Monotech PCs - MOS CPU Replacer – replace rare/expensive/unreliable MOS CPUs**  
6510/8500 *(C64)*  
6510T *(1551 floppy drive)*  
7501/8501 *(C16, C116, Plus/4)*  
8502 *(C128)*

A standard 6502 is required. These are abundant and cheap, and produced by many manufacturers (Rockwell, UMC, Synertek, MOS, etc). You also need some round-pin headers.

You can use a 65C02 or W65C02, but this is untested, and will cause compatibility issues with some software at the least.  
For WDC W65C02 only, cut jumper W.

Build instructions are on the back of the PCB. This document is for clarification if you find it unclear.

Status as of Rev1:
-

- 6510 config: :white_check_mark: Tested working in a C64.
- 6510T config: :grey_question: Not tested - I don't have a 1551.
- 8501 config: :white_check_mark: Tested working in a C16 and a Plus/4.
- 8502 config: :x: Works but has graphical glitches, likely due to a timing issue, so should only be built if you plan to help me diagnose this. For 8502, you must install a 2MHz-rated CPU (such as 6502A).

Instructions:
-

1. Solder the solder-jumpers first (red dots).
1. Solder two 20-pin round-pin headers (cyan rectangles).
1. Solder the DIP-40 socket (yellow rectangles).
1. Install the 6502, and test the device.

**The example picture below is for 8501 config. Steps 1 and 2 are different for the other three configs.**

