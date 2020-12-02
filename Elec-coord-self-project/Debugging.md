## Debugging the project 'Automatic billing trolley'

We all know that things won't work correctly for the first time always. Especially, if we are involved in practical work like electronics and other stuff, the debugging time may be a lot since we don't know where the problem is. To solve these problems, we need to adopt a systematic strategy to solve problem in their various hierarchial levels sequentially. Let us look into the debugging tutorial of the project 'Automatic billing trolley'.

The pipeline is:

Mastercard for initialisation => RFID reader => RFID tags from items => RFID reader => Microcontroller => LCD display => Mastercard for finalising => RFID reader => Microcontroller => LCD (displays total bill).

__Disclaimer:__
Being the electronics designer, we can only debug the module which is related to our porject and associated electronics. We cannot solve problems that arise due to the database errors of the supermarket. 

Keeping those things aside, let us assume the prototype is in the process of creation. We can see it is made up of three modules:

Microcontroller ESP32
RFID reader module EM-18
LCD display

Let us look at the debugging steps sequentially:

__1. Short circuits and power supply review:__
The basic step when it comes to debugging is checking whether all components are correctly wired and powered up. It may happen that some components may be wired incorrect and that may cause a lot of problems. So once we complete wiring up the prototype on a breadboard, we can check whether it is working correctly. To do this, we cna see whether the power LEDs (if any) are lighting up.  Only after checking its correctness on a breadboard, we can actually solder the wires on a suitable PCB. Also, it may happen that the components may get abnormal power beyond or below thier raings. We can quickly check this by checking whether any component has got over-heated or switches off after a few seconds. Once these issues arise, we must fix them by providing adequate power and regulate them using voltage regulators.

__2. Functionality of components review:__
The second step of debugging is to check whether any components are faulty. There are a lot of reasons due to which a component may be faulty:

It could have been over-heated in first step.
It could have been calibrated improperly during its manufacture.
It could have some other internal circuitry problems.

Hence, we must take care of these issues first:

1. We can check the correctness of ESP32 by making some simple circuits out of it and checking the results for a given input.
   Also, we can make circuits that involve Wi-Fi communication to check whether the Wi-Fi module of the ESP32 is genuine.
   
2. Once, we verify that the microcontroller is genuine, we cna check whether the RFID reader is functioning properly by inserting it in    any of the sample circuits we made. We can read the output from the RFID reader and cross-check it with the actual RFID tag that was    scanned.

3. Similarly, we can check the functionality of the LCD display by coding the ESP32 to print some values on it. If it displays those        values correctly then the LCD is genuine.

__3. Coding:__
This is the final part of the debugging tutorial. Even though the circuit may be correct and the components may be genuine, the values read, compared and displayed may be wrong due to the possible errors in the code. Hence, we must check whether the code entered in the microcontroller is correct. If any errors (syntax or semantic) are present, we have to resolve those errors. Once, all these errors are reviewed and resolved, the prototype is ready for usage.

__Note:__ The above debugging sequence is useful only when you, as the project designer, develop the prototype for the first time from scratch. This type of debugging allows you to quickly verify the functionality of a module as soon as you create it by soldering the wires. If already the protoytpe is ready and now it is not working properly, then you must backtrack the problem. First check for coding errors as it would solve most of the problem. Still if some problems exist, check for the connectivity of wires and power supply ratings. Once you resolve those issues and still problems exist, then for sure the problem is with the components. Check for faulty components and replace them.

Some commercial electronic components retailers (online):

[Robokits India](https://robokits.co.in/)

[Robu electronics](https://robu.in/product-category/electronic-components/)

[Mouser electronics](https://www.mouser.in/)
