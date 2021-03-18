[![MCHP](./../images/microchip.png)](https://www.microchip.com)

# SR Latch

In this code example, the Configurable Custom Logic (CCL) is used to implement an SR latch. This functionality is created by using two adjacent LUTs (LUT0 and LUT1 for this example) connected through a sequential logic block. For the Set and Reset signals, two GPIO pins are used as inputs for the LUTs.
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

CCL:
-   CCL enabled
-   LUT0:
    -   LUT enabled
    -   LUT-IN0: Masked
    -   LUT-IN1: IN1 selected
    -   LUT-IN2: Masked
    -   LUT Output enabled
    -   Filter enabled
    -   Truth table = 0x01
-   LUT1:
    -   LUT enabled
    -   LUT-IN0: Masked
    -   LUT-IN1: IN1 selected
    -   LUT-IN2: Masked
    -   Filter enabled
    -   Truth table = 0x01
-   Sequencer: RS

| Pin |  Configuration    |
| :-: | :---------------: |
| PA1 (LUT0-IN1) |   Digital input  |
| PC1 (LUT1-IN1) |   Digital input  |
| PA3 (LUT0-OUT) |   Digital output |

## Operation

1.  Connect the board to the PC.

2.  Open the SR_Latch.X project in MPLAB® X IDE.

3.  Set the SR_Latch.X project as main project. Right click on the project in the **Projects** tab and click **Set as Main Project**.

<br><img src="../images/Set_as_Main_Project.PNG" height="500">

4.  Clean and build the SR_Latch.X project. Right click on the **SR_Latch.X** project and select **Clean and Build**.

<br><img src="../images/Clean_and_Build.PNG" height="500">

5.  Select the **AVR128DA48 Curiosity Nano** in the Connected Hardware Tool section of the project settings:

- Right click on the project and click **Properties**
- Click on the arrow under the Connected Hardware Tool
- Select the **AVR128DA48 Curiosity Nano** (click on the **SN**), click **Apply** and then click **OK**:

<br><img src="../images/Tool_Selection.PNG" height="400">

6.  Program the project to the board. Right click on the project and click **Make and Program Device**.

<br><img src="../images/Make_and_Program_Device.PNG" height="500">

## Demo

In this example, an active-low SR latch was implemented, having the following truth table:

| Set | Reset | Output
| :-: | :-: | :-: |
| `HIGH`  | `HIGH`  | `Hold State`      |
| `HIGH`  | `LOW`   | `Clear`           |
| `LOW`   | `HIGH`  | `Set`             |
| `LOW`   | `LOW`   | `Forbidden State` |

The picture below shows how the output of the sequencer (PA3) changes according to the active-low SR latch behaviour.

<br><img src="images/demo.png" width = "600">

## Summary

This code example shows how to configure the CCL peripheral to implement an SR latch.
