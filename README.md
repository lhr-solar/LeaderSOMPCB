# LeaderSOM
Author: Pratyush Patra, Jacob Pustilnik, and Tianda Huang

This board is the Leader System-On-Module (SOM), a multifunction board with an STM32 MCU that is adaptible to the applications of each subsystem. The hardware and software on this board are responsible
for the processing, communication, and data collection tasks required for the car's subsystems.

## BOM
[**Interactive BOM (Must download and open in browser)**](bom/ibom.html)

[**Mouser Cart**]

## Connectors
| # | Name | Type | Ideal Voltage | Notes |
| -  | - | - | - | - |
| J1 | SWD | PinHeader_1x04_P2.54mm_Vertical | - | - |
| J2 | USB_B_Micro | USB_Micro-B_Molex-105017-0001 | - | - |
| J4 | Micro_SD_Card_Det | microSD_HC_Hirose_DM3AT-SF-PEJM5 | - | - |
| J5 | CAN_In2 | Molex_MicroFit3.0_1x4xP3.00mm_PolarizingPeg_Vertical | - | - |
| J6 | CAN_Out2 | Molex_MicroFit3.0_1x4xP3.00mm_PolarizingPeg_Vertical | - | - |
| J7 | CarPowerConnector | Molex_MicroFit3.0_1x2xP3.00mm_PolarizingPeg_Vertical | - | - |
| J9 | SOMConnector | Molex_52465-2070 | - | - |
| J10 | SOMConnector | Molex_52465-2070 | - | - |
| J11 | CAN_Int | Molex_MicroFit3.0_1x4xP3.00mm_PolarizingPeg_Vertical | - | - |


## PCB
![LeaderSOM-Layout](LeaderSOM-Layout.png)

## Schematic
![LeaderSOM-Schem](LeaderSOM-Schem.png)

## Additional Notes
Below is a link to the pinout document for the board.
https://utexas.sharepoint.com/:x:/r/sites/ENGR-LonghornRacing/_layouts/15/Doc.aspx?sourcedoc=%7B1ce08b10-b376-4beb-83e4-bc72f106b36f%7D&action=edit&wdPreviousSession=fb9a9e6e-1c87-4462-82e8-13c90a4a025d

CAN Power Distribution Notes-
https://utexas.sharepoint.com/sites/ENGR-LonghornRacing/_layouts/15/Doc.aspx?sourcedoc={eecd0eaf-8548-469a-8a85-a697763538be}&action=edit&wd=target%28Power%20Systems.one%7Ca8fe7a0e-1efe-448f-99f4-a73d3ece124b%2FCAN%20Power%20Distribution%20Decisions%7C2f16c7d1-6e30-43a6-9fd0-a8fcac87f4cb%2F%29&wdorigin=NavigationUrl

## Power Distribution
12V_In(from Car power connector) -> Power protection -> 12V+
12V+ -> DCDC Converter(Unisolated) -> 5V+
5V+ -> Capacitance Multiplier for filtering -> LDO -> 3.3V+

CAN Power(Internal CAN)-
5V+ -> Filtering and Regulator(Isolated) -> V_CAN+

CAN Power(CAR CAN)-
Need to design external board to interface with one of the LeaderSOM's to power our CarCAN

## Current Board Concerns(12.2.2023)
