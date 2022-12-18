# freertos-msp430fr2355
A port of FreeRTOS for the MSP430FR2355 microcontroller, created as part of an undergraduate embedded systems project (Magic Wifi). This port was created in November 2022.

Our project can be found [here](https://github.com/bluebandit21/magic-wifi). Note, this port of FreeRTOS was not actually used in the final version of the product.

## What's in this repository?
This repository includes a Texas Instruments CCS project that demonstrates deferred interrupts on the MSP430FR2355. On the development board for this chip, P1.0 and P6.6 are hooked up to RED and GREEN LEDs respectively, and P4.1 is wired to a button on the left side of the board. 

The example program, 'deferred interrupt', has two tasks - a main task and a deferred task. The main task uses the left LED (RED) and runs periodically with a high priority, while the deferred task (GREEN LED) has a low priority and waits on a semaphore given by the ISR triggered by the button. The tasks when active toggles their respective LED (so that it is half-brightness when executing but could be either fully on or off when not executing).

## How to use
Clone this repository, and download Texas Instruments' CCS editor.

Import this project from disk by doing File > Open Projects From File System... and hit `Directory...` for the import source.

This version definitely works for a TI CCS compiler version of 16.9.11LTS. To install this, go to Help > Install New Software... > install TI Compiler Updates > ARM Compiler Tools, version 16.9.11.

## Disclaimer
This repository is not kept up to date to any newer releases of FreeRTOS. While I will try to pay attention to this from time to time, we did end up not using this port of FreeRTOS in our project, and there is no purpose other than giving back to the community to upload this project. Feel free to fork this or refer to it according to your purposes, but no guarantees are made other than this port working for the provided example.

## Acknowledgements and Credits
This version of FreeRTOS was ported from two main sources; all the initial files were taken from the main [FreeRTOS repository](https://github.com/FreeRTOS/FreeRTOS), but the port I have made takes major notes from Nikola, whose post on the Texas Instruments forum [here](https://e2e.ti.com/support/microcontrollers/msp-low-power-microcontrollers-group/msp430/f/msp-low-power-microcontroller-forum/807043/freertos-on-msp430fr2355-launchpad-example-port) we heavily referenced. He gave permission over email to use his work linked in the forum post, and I give him my utmost thanks for allowing our use of his work.

