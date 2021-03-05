[![MCHP](images/microchip.png)](https://www.microchip.com)

# Getting Started with Configurable Custom Logic (CCL) Examples (MPLAB® X)

This repository contains examples of MCC-generated source code for the Configurable Custom Logic (CCL) as described in the [TB3218-Getting Started with Configurable Custom Logic (CCL)](http://ww1.microchip.com/downloads/en/Appnotes/TB3218-Getting-Started-with-CCL-90003218A.pdf) document from Microchip. The repository contains three MPLAB® X projects inside:

* [<strong>Logic AND Gate:</strong>](Logic_AND_Gate) This use case shows how to configure and use the CCL peripheral to implement an AND gate with three inputs (for more details, see [<strong>Logic AND Gate</strong>](Logic_AND_Gate)).
* [<strong>State Decoder:</strong>](State_Decoder) This use case shows how to configure the CCL peripheral to decode the presence of the `b'10110` pattern on the input pins. A circuit composed of LUT0 and LUT1 is implemented to trigger its output when the inputs are in the form of the given pattern (for more details, see [<strong>State Decoder</strong>](State_Decoder)).
* [<strong>SR Latch:</strong>](SR_Latch) This use case shows how to use the CCL combinational and sequential logic to implement an SR latch. This functionality is obtained by using two adjacent LUTs connected through a sequential logic block (for more details, see [<strong>SR Latch</strong>](SR_Latch)).

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
