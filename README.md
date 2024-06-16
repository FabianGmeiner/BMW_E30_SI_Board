# About this Project

I'm currently working on a little project for all the early model E30 drivers with SI board trouble from leaky batteries or mechanical damage.

I am reverse engineering the early model SI board, in my case the VDO version (VDO and motometer are interchangeable)

This initial version is a 1:1 copy of the original design. The main microcontroller, the crystal oscillator and the large pin header need to be desoldered and taken over to the new board, but all other components are readily available and stocked parts.

This is mainly to understand the schematics and the workings of the circuit. In a second step I will design my own board with a modern microcontroller and non-volatile storage to work without batteries, with modern and way cheaper components (similar to the board offered by  [ProgRama](https://www.programainc.com/item_detail.aspx?idproduct=177&idcategory=49&sf=)). Also playing with the idea of integrating further functionality, like configurable shift lights on the little indicator board, as all the necessary signals are there anyway.

Warm regards from Germany!

## Current Status

As of now, an initial batch of boards is on the way from JLCPCB to me for assembly and testing. The design is still **untested!**

I got all the necessary components from either Mouser or Reichelt (german vendor), but everything is available at mouser. The [BOM](https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/BOM_SI_Board_Reman.xlsx "BOM_SI_Board_Reman.xlsx") contains all the part descriptions as well as relevant part numbers and the component identification and placement on the second sheet.

## Schematics

Current versions for the main SI board and the LED indicator board are V2 and can be found as .pdf ([2024_06_15_SI_Board_Schematic_V2.pdf](https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/2024_06_15_SI_Board_Schematic_V2.pdf "2024_06_15_SI_Board_Schematic_V2.pdf"), [2024_06_15_Indicator_Schematic_V2.pdf](https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/2024_06_15_Indicator_Schematic_V2.pdf "2024_06_15_Indicator_Schematic_V2.pdf")) or in the respective KiCad projects

## Manufacturing files

Exported Gerbers for getting the boards manufactured are located in the respective KiCad project folders

