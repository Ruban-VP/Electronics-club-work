__Project 1: Green lantern ring__

__Problem statement:__
To design a simple ring which emits green light when worn and doesn't when not worn.

__Design:__
The basic mechanism must be a trigger, i.e., some sort of an interaction is induced when worn. So I thought of using a touch sensor IC for this purpose. The IC is connected to a sense elctrode which is embedded on the inner surface of the ring. Hence, when the ring is worn, the electrode senses the touch and accordingly a signal is generated in the IC. The IC processes it and blinks the green LED placed on the ring. 

The IC also has a low-power mode and hence, we can reduce power consumption by a huge scale. In this mode, the IC takes scan of the state of the electrode every 800 milli seconds and hence, the average scanning energy per cycle is also less.

The components used are:

1. __2 10k ohms resistors__

2. __1 1k ohm resistor__

3. __1 4.7k ohms resistor__

4. __1 0.1 uf capacitor__

5. __Trimpot for checking the required sensitivity__

6. __3v coin battery__

7. __3mm small green LED__

IC datasheet: [MTCH101](http://ww1.microchip.com/downloads/en/DeviceDoc/40001664B.pdf)


