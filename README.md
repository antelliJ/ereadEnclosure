#ereader Enclosure
An expansion on [my ereader project](https://github.com/antelliJ/EPUB-Ereader) made using the arduino framework, and rendering using GxEPD2 on an ESP-32 S3

<img width="339" height="193" alt="Screenshot 2026-11-01 192144" src="https://github.com/user-attachments/assets/d7a369c4-2a89-4849-8b95-47265f1eaa66" />


## Purpose
I found that my existing enclosure was just really bulky since it was all connected through jumper cables, and since I was using an old DVD player as the shell there was still lots of empty room. When I got my hands on a commercial ereader I realized that I could definitely make it smaller so it would be more comfortable to carry around


## Usage and info
Charging and data goes through a single usb c cable, an improvement frmo before where there was the port to charge, and 2 ports on the esp32 for jtag and usb. I guess those are still available, especially if you want jtag, you'd just need to remove the enclosure. But uploading and charging should be able to be done, this time also at the same time since it is using an MCP733871 which supports load sharing for powering the system and charging the battery

The schematic uses pin headers as placeholders for things like the switch and SPI sd card module, so ensure you choose what you need when designing it.

[![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?repo=https%3A%2F%2Fgithub.com%2FantelliJ%2FereadEnclosure%2Ftree%2Fmain%2FPCB)
<img width="526" height="418" alt="Screenshot 2026-11-01 194429" src="https://github.com/user-attachments/assets/12c62f89-4b3e-4850-b5e1-f8bc8bca0363" />

<img width="722" height="677" alt="Screenshot 2026-11-01 194445" src="https://github.com/user-attachments/assets/b37eb141-a059-41cd-b788-a3673929ef86" />

### File structure
`\PCB\` includes files relevant for the schematic, PCB design, and manufacturing. 
<br></br>
    `\PCB\production\` are the files used for PCB manufacturing
<img width="3508" height="2480" alt="schematic v2" src="https://github.com/user-attachments/assets/38882b63-2ebc-4dbc-b288-1006230479c2" />


`\3dModel\` is intended for all 3d printed related files.
<br></br>
    `\3dModel\editable\` contains the editable files made in freecad for the enclosure

<br></br>
    `\3dModel\printable\` contains the print ready files as a `.3mf` file


`\Code\` Is a copy of the original repository. 
you can learn more about it [here](https://github.com/antelliJ/EPUB-Ereader)

It uses the GxEPD2 library to drive the display using SPI, using the arduino framework since that is what I am most comfortable with.

## Bill of Materials
A nicely formatted excel sheet is provided at `\PCB\production\ereader-bom.xlsx` with a few more comments. 
The below is just a static version of that...

| Designator | Footprint                                        | Quantity | Value                       | LCSC Part # | Alt Site                                                                                                       |
| ---------- | ------------------------------------------------ | -------- | --------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------- |
| J1         | PinHeader_2x04_P2.54mm_Vertical                  | 1        | EPD-4.2in - 2x04            | C55829516   |                                                                                                                |
| J2         | Molex_PicoBlade_53047-0810_1x08_P1.25mm_Vertical | 1        | Remote Communication                      | C240845     |                                                                                                                |
| J3         | USB_C_Receptacle_GCT_USB4085                     | 1        | USB_C_Receptacle_USB2.0_14P | C2765186    |                                                                                                                |
| J4         | SPI-microsd-1x06                                 | 1        | SPI Micro SD card slot      |             | [https://www.aliexpress.com/item/1005008633757049.html](https://www.aliexpress.com/item/1005008633757049.html) |
| R1, R2     | 603                                              | 2        | 5.1k                        | C23186      |                                                                                                                |
| SW1        | PinHeader_1x03_P2.54mm_Horizontal                | 1        | SW_SPDT                     | FILLER      |                                                                                                                |
| U1         | ESP32-S3-DevKitC                                 | 1        | ESP32-S3-DevKitC            |             | https://www.aliexpress.com/item/1005007319706057.html                                                          |
| U2         | MCP73871                                         | 1        | MCP73871                    |             | https://www.aliexpress.com/item/32779467674.html                                                               |
| U3         | Buck Boost 3v3                                   | 1        | Buck Boost Converter        |             | https://www.aliexpress.com/item/1005006289357253.html                                                          |


A 10k thermistor is also used by the MCP73871 alongside a capacitor, which is usually given with the module.

## References
A lot of things were picked up on the way of creating this project spontaneously

used [Table to Markdown](https://tabletomarkdown.com/convert-spreadsheet-to-markdown/) to make the above BOM in the readme

There is some AI usage in the original E-reader project code, as follows:
- Code autocomplete and debugging
- AI explanations for unfamiliar C++ concepts
- Drafting PlatformIO calls for building
