__Debugging of the project 'Electronic juice vending machine'__

The web link of the project description: [Electronic juice vending machine](https://nevonprojects.com/android-powered-juice-vending-machine/)

__Debugging:__

The pipeline of this project is:

Coin module and pushbuttons => Microcontroller => Glass detection module => Microcontroller => Motor drivers, IR sensor module and LCD display

So this project is made up of 4 modules:

1. Input module (Coin module and pushbuttons)
2. Detector module (IR sensors used for glass presence detection and juice level detection)
3. Controller module (Microcontroller)
4. Output module (Motor drivers, IR sensors and LCD display)

More or less the debugging concept is same for all the modules except for a few nuances. the basic debugging is as follows:

________________________________________________________________________________________________________________________________________

__Circuit connections:__

First we must check whether the connections are proper without any short-circuits and all the components get the power. To do this, we can check the power LEDs. If they are not present, we can check whether power supply is proper using continuity testers and multimeters. If all connections are proper, then we can proceed. If not, then we must resolve those issues and then must proceed.

________________________________________________________________________________________________________________________________________

__Functionality of components:__

It may happen that the components which we may get maybe faulty or getting power beyond or below their prescribed ratings. This can be resolved by checking the behaviour of the components. If they get overheated, it means they get more power than needed. Similarly, if they don't function properly then it may happen that the power they are getting may be less. After resolving this issue, still if the component doesn,t function properly, it is faulty and hence, must be replaced. The commercial website links to buy electronic components are given below.

Functionality checks for each module:

1. Input module:

   We can manually check whether the coin detector module works properly by first prototyping it using a breadboard.
   Pushbuttons can also be checked by simply connecting them across a potential difference, an ammeter and a resistor. If the ammeter s    shows some value when the pushbutton is pressed, it means it is working.
   
2. Detector module:

   To verify the functionality of the IR sensor module, we can connect the IR sensors with an arduino and check whether they provide the    correct data.
   
3. Controller module:

   To test the controller, we can make some basic circuits out of it and can verify whether it provides the desired results based on the    code entered into it.
   
4. Output module:

    IR sensors are already tested.
    Motors and their drivers can be checked by making a simple circuit out of them and testing their behaviour.
    LCD can also be similarly verified. We can interface it with a controller and program it to display a small message. If the LCD         correctly displays it then it is a genuine component.
    
Once the individual components are tested for functionality, we can go for troubleshooting of the code.

________________________________________________________________________________________________________________________________________

__Troubleshooting the code:__

Coding is the most important part of any electronic circuit we make. If the code is wrong, then all the associated data and actions will become wrong. So ensuring the logic and functionality of the code will almost solve all the problems. First, we must check whether the required __libraries__ are present. Second, we must check whether the code we entered has the __logic and functionality__ we expected from the prototype. Once, these two conditions are satisfied, coding part is troubleshooted.

Once, all these three steps are done, the project must be ready and devoid of problems.
________________________________________________________________________________________________________________________________________

__PS:__ The above mentioned debugging tutorial is applicable when we create the prototype for first time out of scrath. This type of debugging allows us to identify the mistakes as and when we complete creating and wiring up a module. If the prototype is already done and it doesn't work properly, we must work backwards and reverse-engineer the project. First, we must check for any coding errors as it would solve most of the problems. Once they are solved and still the prototype behaves weird, we have to check whether the wiring is proper and sufficient power reaches the components (This process may involve some dismantling). Once these issues are resolved and still the circuit misbehaves, then for sure the problem is with the functionality of the components. This time we have to dismantle the circuit entirely and check the functionality of each component.

__Commercial websites to buy components:__

[Robokits India](https://robokits.co.in/)

[Robu electronics](https://robu.in/product-category/electronic-components/)

[Mouser electronics](https://www.mouser.in/)

   


