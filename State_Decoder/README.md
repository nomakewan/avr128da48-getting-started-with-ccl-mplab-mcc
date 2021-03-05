[![MCHP](./../images/microchip.png)](https://www.microchip.com)

# State Decoder

In this code example, the CCL's LUT0 and LUT1 are configured to decode the presence of the `b'10110` pattern on the input pins. A circuit composed of LUT0 and LUT1 is implemented to trigger its output when the inputs are in the form of the given pattern.

## Related Documentation
More details and code examples on the AVR128DA48 can be found at the following links:
- [TB3218-Getting Started with Configurable Custom Logic (CCL)](http://ww1.microchip.com/downloads/en/Appnotes/TB3218-Getting-Started-with-CCL-90003218A.pdf)
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
    -   LUT-IN0: IN0 selected
    -   LUT-IN1: IN1 selected
    -   LUT-IN2: LINK selected
    -   LUT Output enabled
    -   Truth table = 0x40
-   LUT1:
    -   LUT enabled
    -   LUT-IN0: IN0 selected
    -   LUT-IN1: IN1 selected
    -   LUT-IN2: IN2 selected
    -   Truth table = 0x20

| Pin |  Configuration    |
| :-: | :---------------: |
| PA0 (LUT0-IN0) |   Digital input  |
| PA1 (LUT0-IN1) |   Digital input  |
| PC0 (LUT1-IN0) |   Digital input  |
| PC1 (LUT1-IN1) |   Digital input  |
| PC2 (LUT1-IN2) |   Digital input  |
| PA3 (LUT0-OUT) |   Digital output  |

## Operation

1.  Connect the board to the PC.

2.  Open the State_Decoder.X project in MPLAB® X IDE.

3.  Set the State_Decoder.X project as main project. Right click on the project in the **Projects** tab and click **Set as Main Project**.

<br><img src="../images/Set_as_Main_Project.PNG" height="500">

4.  Clean and build the State_Decoder.X project. Right click on the **State_Decoder.X** project and select **Clean and Build**.

<br><img src="../images/Clean_and_Build.PNG" height="500">

5.  Select the **AVR128DA48 Curiosity Nano** in the Connected Hardware Tool section of the project settings:

- Right click on the project and click **Properties**
- Click on the arrow under the Connected Hardware Tool
- Select the **AVR128DA48 Curiosity Nano** (click on the **SN**), click **Apply** and then click **OK**:

<br><img src="../images/Tool_Selection.PNG" height="400">

6.  Program the project to the board. Right click on the project and click **Make and Program Device**.

<br><img src="../images/Make_and_Program_Device.PNG" height="500">

## Demo

The pattern that needs to be decoded is `b'10110`:

| Pin | Value |
| :-: | :-: |
| PC2 (LUT1_IN2) | `1` - HIGH |
| PC1 (LUT1_IN1) | `0` - LOW  |
| PC0 (LUT1_IN0) | `1` - HIGH |
| PA1 (LUT0_IN1) | `1` - HIGH |
| PA0 (LUT0_IN0) | `0` - LOW  |

The picture below shows how the output (PA3) goes high when the pattern is detected on the input pins.

<br><img src="images/demo.png" width ="600">

## Summary

This code example shows how to configure the CCL peripheral to implement a state decoder.
