## Home automation using Wi-Fi communication

What if we are able to switch on the lights and fans in our room without even touching the switches? What if all those actions can be done using an app in our mobile? This project exactly enables those actions. It is a simple project where we can control our lights and fans using a microcontroller, Wi-Fi and an app in our mobile.

The components used are:

* NodeMCU microcontroller
* 4 channel relay

__NodeMCU:__
It is a small microcontroller which has an ESP8266 module as its core. This module allows it to connect to Wi-Fi module via the TCP/IP protocol. It also has a USB socket and hence, can be powered using any modern mobile phone charger. Also, the Arduino IDE has dedicated libraries for this microcontroller. Hence, we can also code this microcontroller according to our requirements.

Microcontroller datasheet: [NodeMCU](https://components101.com/development-boards/nodemcu-esp8266-pinout-features-and-datasheet)

Pinout diagram:

![img](https://components101.com/sites/default/files/component_pin/NodeMCU-ESP8266-Pinout.jpg)

__4 channel relay:__
Relay is an electromechanical switch which has an electromagnet and a contact arm. When the relay is energised or powered, the magnet gets magnetised and hence, pulls the contact arm towards it. This establishes a connection between the phase and neutral wires and hence, the current passes through the load(Fans, lights, etc.). Any mechanical switch controlled appliance like fan, mixer, tubelight, CFCs can be relay controlled.

Link to know about relay working mechanism: [How relays work](https://www.galco.com/comp/prod/relay.htm)

Relay working diagram:

![img](https://www.galco.com/images/moreinfo/relay_diagram.gif)

Relay datasheet: [Link](https://www.handsontec.com/dataspecs/4Ch-relay.pdf)

### Design:
The relays are connected to the NodeMCU module. The common phase line is connected to the relay module and the individual relay output lines are connected to various appliances. Based on the commands obtained from the app, the microcontroller will switch on the corresponding relay and hence, the appliance will be switched on. 

Block diagram:

![img](https://www.pantechsolutions.net/media/wysiwyg/ML/android_controlled_home_automation_using_nodemcu_via_wifi.jpg)

Component diagram:

![img](https://www.factoryforward.com/wp-content/uploads/2018/03/Home-Automation-with-NodeMCU_v2-1024x702.png)

Tutorial link: [Home automation with NodeMCU and Blynk](https://www.factoryforward.com/iot-home-automation-using-blynk-nodemcu/)

### Cost of deployment:

The physical components such as NodeMCU and the 4 channel relay may together cost nearly 450 INR. IF we want a bluetooth connection as well, a normal HC-05 bluetooth model will cost around 280 INR. The app required to control this circuit must be developed from scratch. There are a number of platforms like MIT app inventor and Blynk for this purpose. While MIT app inventor is free, Blynk is a paid software. So, the cost changes depending on the resource used. Assuming the free software is used and bluetooth module is not used, the typical cost for deploying the physical model will be around 500-600 INR including the wires, power supply chargers and other components.

________________________________________________________________________________________________________________________________________

__Sites to buy components:__

[Relay in Robokits India](https://robokits.co.in/control-boards/interface-boards/opto-isolated-4-channel-5v-10a-relay-board?gclid=EAIaIQobChMIyMud6_7C6QIV0LWWCh249wirEAQYAiABEgJG-fD_BwE)

[NodeMCU in B.M. Embedded solutions](https://bm-es.com/product/esp8266-nodemcu-wifi-module/?gclid=EAIaIQobChMIu9C6r__C6QIVDGoqCh1j4AjvEAYYASABEgJe2vD_BwE)

__Helpful resources:__

[Blink a bulb using Arduino and bluetooth](https://www.youtube.com/watch?v=q5I68DFNelA)

[Build an Android app to control Wi-Fi enabled Arduino](https://www.youtube.com/watch?v=ZH7ufemP8e0)

[Getting started with Blynk for IOT apps](https://www.youtube.com/watch?v=RLKuIHaraKs)

[Voice commands controlled home appliances app](https://appinventor.mit.edu/explore/stories/voice-controlled-arduino-beginners.html)
(Useful resource if you want to add a voice command feature to your automation project).
