__Debugging of project 'Wireless auto power trip'__

The web link of project description: [Wireless auto power trip](http://www.ripublication.com/aeee/42_pp%20%20327-332.pdf)

__Debugging:__

The pipeline of this project is:

Gas sensor => Microcontroller => RF transmitter => RF reciever => Microcontroller => Relay tripper and GSM module
 
So basically the pipeline is made up of two modules:

1. Transmitter module
2. Receiver module

Hence, the problem must be in any of these modules and the data flows from the transmitter module to the receiver module. So lets analyse both of them in detail:
________________________________________________________________________________________________________________________________________

__Transmitter module:__

First we have to check whether the whole circuit is connected properly without any short-circuits. To verify that we must check whether the power LEDs are glowing. For example, we have to check whether the in-built LED in the arduino board is blinking as it ensures the circuit is getting power properly. And also, we must verify whether the peripherals, i.e, the gas sensor and the RF transmitter are properly wired to the microcontroller to ensure proper communication. 

If yes, we can move further. If not, then these loose connections must be taken care of and resolved.

Once we have ensured the connections and power supply are proper, we msut check for the functionality of the components. We have to check if any component bought is faulty or doesn't meet its requirements. For example, we have to check whether any IC is overheated or switches off after some time. Overheating indicates that the IC was getting too much power and hence, could've been destroyed. Sudden switch off may indicate less power. Once, faulty components and power value is taken care of, we can proceed further. If not, then those issues must be corrected. The commercial website links which are available to buy components are provided at the end.

Once we are at this stage, we can just review the circuit one more time. Later, we must not return to this module.

________________________________________________________________________________________________________________________________________

__Receiver module:__

The procedure is more or less the same. First we must check whether the connections and power supply are proper. To do so, we can check the power LEDs. Also, we must ensure that the components are getting the correct power values. For this, we have to manually check whether any component is overheated or faulty. For example, we have to check whether the RF receiver, relay switch and the GSM transmitter are connected properly and get suffiient power. Once the connections of the peripherals and validity of components used are reviewed, the circuital part of the project is done. 

As again, we can review the connections one more time but should not again return to this part later.

________________________________________________________________________________________________________________________________________

__Troubleshooting the code:__

Once, we are done with the physical debugging (proper connections, genuine components), the next part would be troubleshooting the code. It is very evident that improper coding could be a potential reason for loss of data. Hence, ensuring the code validity is very important. To check whether the data is properly obtained, processed and transmitted we need to dive into the coding part. Only using the code, we can say whether the gas sensor is obtaining valid result, whether the RF modules properly work, whether the relay works properly  and whether the GSM transmitter sends the messages correctly. Even though the peripherals may get sufficeint power and are all properly connected, they may not provide the correct results due to some internal errors. These errors can be identified only when we code them and test the prototype for the first time.

For example, this is the code to check whether the MQ-6 gas sensor gets the data correctly:

```
int gasconc = 0;

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);

  pinMode(11, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(7, OUTPUT);
}

void loop()
{
  gasconc = map(analogRead(A0), 0, 1023, 0, 1000);
  // The output 10 bit signal is scaled to a range of
  // 0-1000.
  // We are assuming the threshold in this scale is
  // 100
  Serial.print("Gas concentration:");
  Serial.println(gasconc);
  if (gasconc <= 100) {
    digitalWrite(11, HIGH);
    digitalWrite(12, LOW);
    noTone(7);
  } else {
    digitalWrite(12, HIGH);
    digitalWrite(11, LOW);
    tone(7, 1.992476322042289e+26, 250); // play tone 1000 (E83 = 1.992476322042289e+26 Hz)
    delay(1); // Wait for 1 millisecond(s)
  }
}
```

Once we program this code into the arduino and switch on the circuit, we can check the values which the sensor sends on a serial monitor. By comparing it with the threshold, we can check whether the circuit takes the correct decision like switching on a speaker as an alert if the gas conc. excceds the safe level. Even if it exceeds the safe level and still the speaker is not switched on, there is a possibility that the sensor may have some fault or the circuit may not be proper. Hence, only after coding, we can verify whether the peripherals have any internal calibration errors as these errors normally won't show up due to less power. Specifically, they can be called as run-time errors which can be identified only when we activate and run the prototype.

________________________________________________________________________________________________________________________________________

__Commercial websites:__

[Robokits India](https://robokits.co.in/)

[Robu electronics](https://robu.in/product-category/electronic-components/)

[Mouser electronics](https://www.mouser.in/)

__PS:__ This above mentioned debugging tutorial can be followed when we create the prototype for the first time. This flow of debugging is sort of interpreter-like troubleshooting. We check the connections and validity of components as and when we complete the wiring of a particular module circuit. But, if we already have the prototype ready and now it is not working properly, we must backtrack the problem. First, we have to start with the possible errors that would've been in the code. Once, we troubleshoot those errors and still the prototype fails, we have to go to the next level, i.e., proper wiring and finally functionality of components.

