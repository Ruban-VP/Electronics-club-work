__Project 9: Wireless auto power trip__

__Description:__
This project implements the prevention of fire due to electricity when a gas leakage happens. A gas sensor is used to detect the leakage of gas and the data sensed by it is processed by a microcontroller. This controller sends the processed data in an USART encoded form to a RF transmitter. On the receiver end, an RF receiver sends the recieved signal and passes it to a decoder. The decoded signal is sent to another microcontroller which processes it and takes a decision based on that. If the leak is below safety levels, the controller doesn't change anything whereas if it is hazardous it switches on the alarm system (comprising of LED, LCD and a buzzer). Also, it relay trips the power supply to prevent any fire due to passage of electricity. Microcontrollers belonging to the Arduino, Atmel or Intel 8051 families could be used. 

The web link for the detailed project description: [Wireless auto power trip](http://www.ripublication.com/aeee/42_pp%20%20327-332.pdf)


