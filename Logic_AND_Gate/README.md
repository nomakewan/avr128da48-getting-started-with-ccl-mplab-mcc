[![MCHP](./../images/microchip.png)](https://www.microchip.com)

# Logic AND Gate

This code example shows how to configure the Configurable Custom Logic (CCL) peripheral to implement an AND gate with three inputs. The output of the look-up table is routed to an external pin.

## Related Documentation
More details and code examples on the AVR128DA48 can be found at the following links:
- [TB3218-Getting Started with Configurable Custom Logic (CCL)](https://ww1.microchip.com/downloads/en/Appnotes/TB3218-Getting-Started-with-CCL-DS90003218.pdf)
- [AVR128DA48 Product Page](https://www.microchip.com/wwwproducts/en/AVR128DA48)
- [AVR128DA48 Code Examples on GitHub](https://github.com/microchip-pic-avr-examples?q=avr128da48)
- [AVR128DA48 Project Examples in START](https://start.atmel.com/#examples/AVR128DA48CuriosityNano)


## Software Used
- MPLAB® X IDE 5.40 or newer [(microchip.com/mplab/mplab-x-ide)](http://www.microchip.com/mplab/mplab-x-ide)
- MPLAB® XC8 2.30 or a newer compiler [(microchip.com/mplab/compilers)](http://www.microchip.com/mplab/compilers)
- MPLAB® Code Configurator (MCC) 4.0.1 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- MPLAB® Code Configurator (MCC) Device Libraries 8-bit AVR MCUs 2.5.0 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- AVR-Dx 1.6.88 or newer Device Pack


## Hardware Used
- AVR128DA48 Curiosity Nano [(DM164151)](https://www.microchip.com/Developmenttools/ProductDetails/DM164151)

## Setup

The AVR128DA48 Curiosity Nano Development Board is used as test platform.

<br><img src="../images/AVR128DA48_CNANO_instructions.PNG" width="500">

The following configurations must be made for this project:

System clock: 3.33 MHz

CCL - LUT1:
-   LUT enabled
-   LUT-IN0: IN0 selected
-   LUT-IN1: IN1 selected
-   LUT-IN2: IN2 selected
-   LUT Output enabled
-   Truth table = 0x80
-   CCL enabled

| Pin |  Configuration    |
| :-: | :---------------: |
| PC0 (LUT1-IN0) |   Digital input  |
| PC1 (LUT1-IN1) |   Digital input  |
| PC2 (LUT1-IN2) |   Digital input  |
| PC3 (LUT1-OUT) |   Digital output  |

## Operation

1.  Connect the board to the PC.

2.  Open the Logic_AND_Gate.X project in MPLAB® X IDE.

3.  Set the Logic_AND_Gate.X project as main project. Right click on the project in the **Projects** tab and click **Set as Main Project**.

<br><img src="../images/Set_as_Main_Project.PNG" height="500">

4.  Clean and build the Logic_AND_Gate.X project. Right click on the **Logic_AND_Gate.X** project and select **Clean and Build**.

<br><img src="../images/Clean_and_Build.PNG" height="500">

5.  Select the **AVR128DA48 Curiosity Nano** in the Connected Hardware Tool section of the project settings:

- Right click on the project and click **Properties**
- Click on the arrow under the Connected Hardware Tool
- Select the **AVR128DA48 Curiosity Nano** (click on the **SN**), click **Apply** and then click **OK**:

<br><img src="../images/Tool_Selection.PNG" height="400">

6.  Program the project to the board. Right click on the project and click **Make and Program Device**.

<br><img src="../images/Make_and_Program_Device.PNG" height="500">

## Demo

The table below presents the truth table for an AND gate with three inputs:

| IN0 | IN1 | IN2 | OUT |
| :-: | :-: | :-: | :-: |
| `LOW`  | `LOW`  | `LOW`  | `LOW`  |
| `LOW`  | `LOW`  | `HIGH` | `LOW`  |
| `LOW`  | `HIGH` | `LOW`  | `LOW`  |
| `LOW`  | `HIGH` | `HIGH` | `LOW`  |
| `HIGH` | `LOW`  | `LOW`  | `LOW`  |
| `HIGH` | `LOW`  | `HIGH` | `LOW`  |
| `HIGH` | `HIGH` | `LOW`  | `LOW`  |
| `HIGH` | `HIGH` | `HIGH` | `HIGH` |

The picture below shows how the output (PC3) changes according to the gate inputs (PC0, PC1 and PC2).

<br><img src="images/demo.png">

## Summary

This code example shows how to configure the CCL peripheral to implement a logic AND gate with three inputs.