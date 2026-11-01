#ereader Enclosure
An expansion on [my ereader project](https://github.com/antelliJ/EPUB-Ereader) made using the arduino framework, and rendering using GxEPD2 on an ESP-32 S3



## Purpose
I found that my existing enclosure was just really bulky since it was all connected through jumper cables, and since I was using an old DVD player as the shell there was still lots of empty room. When I got my hands on a commercial ereader I realized that I could definitely make it smaller so it would be more comfortable to carry around


## Usage and info
Charging and data goes through a single usb c cable, an improvement frmo before where there was the port to charge, and 2 ports on the esp32 for jtag and usb. I guess those are still available, especially if you want jtag, you'd just need to remove the enclosure. But uploading and charging should be able to be done, this time also at the same time since it is using an MCP733871 which supports load sharing for powering the system and charging the battery

The schematic uses pin headers as placeholders for things like the switch and SPI sd card module, so ensure you choose what you need when designing it.

[![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?repo=https%3A%2F%2Fgithub.com%2FantelliJ%2FereadEnclosure%2Ftree%2Fmain%2FPCB)

### File structure
`\PCB\` includes files relevant for the PCB design and manufacturing. 
<br>
    `\PCB\production` are the files used for PCB manufacturing

`\3dModel\` is intended for all 3d printed related files.
<br>
    `\3dModel\editable` contains the editable files made in freecad for the enclosure

<br>
    `\3dModel\printable` contains the print ready files as a `.3mf` file


## Bill of Materials
A nicely formatted excel sheet is provided at `\PCB\production\Keychain-Bom.xlsx`
The below is just a static version of that...

COMING SOON