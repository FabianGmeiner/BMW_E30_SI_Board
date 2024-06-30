# About this Project

I'm currently working on a little project for all the early model E30 drivers with SI board trouble from leaky batteries or mechanical damage.

I am reverse engineering the early model SI board, in my case the VDO version (VDO and motometer are interchangeable)

This initial version is a 1:1 copy of the original design. The main microcontroller, the crystal oscillator and the large pin header need to be desoldered and taken over to the new board, but all other components are readily available and stocked parts.

This is mainly to understand the schematics and the workings of the circuit. In a second step I will design my own board with a modern microcontroller and non-volatile storage to work without batteries, with modern and way cheaper components (similar to the board offered by  [ProgRama](https://www.programainc.com/item_detail.aspx?idproduct=177&idcategory=49&sf=)). Also playing with the idea of integrating further functionality, like configurable shift lights on the little indicator board, as all the necessary signals are there anyway.

Warm regards from Germany!

## Current Status

2024/06/24 I received the initial batch of PCBs for testing. This includes the main SI boards as well as the pre-facelift LED board (9 LEDs).

I got all the necessary components from either Mouser or Reichelt (german vendor), but everything is available at Mouser. The [BOM](https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/BOM_SI_Board_Reman.xlsx "BOM_SI_Board_Reman.xlsx") contains all the part descriptions as well as relevant part numbers and the component identification and placement on the second sheet.

The facelift indicator boards (7 LEDs, 3 Bulbs) is based on photographs only, as such I could not yet verify the dimensions apart from measurements from images. 
If anybody has one of those boards laying around and could provide peasurements that would be highly appreciated.

### Testing status

#### Main SI board
2024/06/24 first board assembled ready for testing.
2024/06/30 first functional tests successful. All functions operate as they should, and current consumption is in a nominal range. I am currently building a little pulse generator to test the speed and rpm inputs and test if the oil service lights count down as expected. This will be combined with a long test with the board powered up to check the current consumption and temperatures over longer time. 

| **Test Description**                 | **Current Draw Board** | **Battery Current** | **Further Comments**                                    |
|--------------------------------------|------------------------|---------------------|---------------------------------------------------------|
| Initial Connection, T30 off, T15 off |                        | 9.2 µA              | Battery current measured between BAT_EN jumper          |
| T30 on, T15 off                      | 3.6 mA                 | 5.7 µA              | All lights stay off, battery current reduces.           |
| T30 on, T15 on                       | 145.9 mA               | 5.7 µA              | 5 green LEDs turn on, Inspection light turns on         |
| Activating T50 (starter signal)      |                        |                     | Relay clicks, pad indicator lights up                   |
| Releasing T50 (starter signal)       |                        |                     | Relay clicks, pad indicator turns off, LEDs turn off    |
| Reset Button Pressed                 | 30.4 mA                |                     | INSP light goes out after ~10s, all lights off          |
| T30 on, T15 off                      | 3.6 mA                 |                     | turning ignition off after reset                        |
| T30 on, T15 on                       | 89.4 mA                |                     | ignition back on, 5 green LEDs on, INSP light stays off |
| Activating and releasing T50         | 30.5 mA                |                     | Relay cycles, LEDs turn off. All lights off.            |
| T30 off, T15 off                     |                        | 9.2 µA              |                                                         |

#### Indicator board
2024/06/24 first board assembled. Electrical test ok. Mechanical fitment is off, the connector header needs to be moved up 2.5mm for the board to sit flush with the main PCB. 
2024/06/27 PCBs are corrected and updated files uploaded. Ordered a new batch of pre-facelift and facelift boards for testing

## Schematics

Current versions for the main SI board and the LED indicator board are V2 and can be found as .pdf ([2024_06_15_SI_Board_Schematic_V2.pdf](https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/2024_06_15_SI_Board_Schematic_V2.pdf "2024_06_15_SI_Board_Schematic_V2.pdf"), [2024_06_15_Indicator_Schematic_V2.pdf](https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/2024_06_15_Indicator_Schematic_V2.pdf "2024_06_15_Indicator_Schematic_V2.pdf")) or in the respective KiCad projects.

I also added an LED-only-version of the indicator board, replacing the bulbs with white 5mm LEDs and adding current limiting resistors. The resistors will have to be adapted to the LEDs you are using. 
The same goes for a facelift version of the indicator board, with 7 LEDs (one red) and three bulbs.


The schematics also include the pin assignments and routing of the whole instrument cluster (albeit in german), and should also come in as a handy reference for throubelshooting or repairing an original SI board, e.g. with corroded traces.

## Manufacturing files

Exported Gerbers for getting the boards manufactured are located in the respective KiCad project folders for a variety of different board houses. I ordered mine through JLCPCB. 

## Licensing 
LICENSE NOTE: The root license applies to all subfolders NOT containing their own LICENSE file. If a subfolder contains a different LICENSE file this different license applies to all subfolders below this LICENSE file.

I encourage everyone to get the boards manufactured yourself as the components are cheaply available and its a cool project to keep our old cars running nicely.
If you want to sell any hardware of this project yourself i would kindly ask you to get in contact with me.
