__Ideation of the project 'Wireless auto power trip'__

The web link to the project description: [Wireless auto power trip](http://www.ripublication.com/aeee/42_pp%20%20327-332.pdf)

__Problem statement:__
To create an automatic gas leak detector and power tripper which detects the presence of a gas leak and if any is present, will automatically shut down the power and also activate an alarm.

__Ideation phase:__
The basic mechanism of this project is simple:

Gas sensor => Transmission end microcontroller => WC transmitter module => WC receiver module => Receiver end microcontroller => Alarm system and Tripper switch

In the given link, they have used:

MQ-6 gas sensor

RF communication module for wireless communication

Suggested PIC16F877A or Intel 8051 microcontrollers

| Component | Feasibility | Advantages | Disadvantages |
|-----------|-------------|------------|---------------|
|Microcontroller|Quite easy if familiar with its basics| Our solution could be even more versatile if we can hack on the microcontroller|Usually tough to start with since they are PLDs basically and demand some programming skills beforehand|
|Wireless communication module|Tough to start with and demand some dedicated components|Learning outcomes are high|Require some money as components may be costly|

The solution given in the project is good. But a few changes can make it more user effective. We can use an Arduino instead of an 8051 microcontroller since it has its own programming IDE and hence, programming it would be easier. Also, an arduino costs much lesser than an 8051 microcontroller. This allows us to also have a GSM module at the receiver end to send an SMS to the residents of the home in case they have gone out. Also, arduino has an in-built ADC whereas an 8051 microcontroller requires an external ADC converter which again adds on to the cost. Hence, the overall cost can be reduced and also communication to the user via SMS is enabled.

[Do 8051 microcontrollers have in-built ADC?](https://www.quora.com/Do-8051-microcontrollers-have-in-built-ADC)

[Difference between Arduino and 8051](http://www.differencebetween.net/technology/difference-between-arduino-and-8051-microcontroller/)
