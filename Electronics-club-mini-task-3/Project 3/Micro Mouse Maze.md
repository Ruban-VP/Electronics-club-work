__Project 3: Micro Mouse Maze:__

__Problem statement:__
To come up with a small bot which autonomously navigates itself in a maze and reaches its destination.

__Design:__
The bot is mounted on a rectangular board with two-wheel control and a castor wheel in the front for stability purposes. The steering is controlled by rotating the wheels in opposite directions whereas linear motion is enabled by rotating them in the same direction. The wheels are motor controlled which are connected as output pins in a microcontroller. Also, three obstacle detection sensors are placed (one in front and other two on the sides) to enable navigation. Their output pins are connected as input pins to the microcontroller. It is programmed according to the user's needs.

I chose the following components:

__Arduino nano__

__HC-SR04 ultrasonic rangefinder__

__LM35 temperature sensor__

__Flipkart smartbuy LiPo credit card sized power bank__

__N20 6V 100RPM dc motor with encoder__

Having the size constraints in mind, I chose an Arduino nano as the microcontroller since it not only exactly mimics the Arduino UNO but also smaller in size. It can be easily programmed using the Arduino IDE and also has libraries for HC-SR04.

Arduino nano datasheet: [Pin configuration link](https://components101.com/microcontrollers/arduino-nano)

![img](https://joelektron.com/190-large_default/arduino-nano-compatible-board.jpg)

I chose an HC-SR04 instead of a US-100 because both of them has the same practical measuring range and operating voltage (5v) but a HC-SR04 is way cheaper than a US-100. But, US-100 has temperature compensation of distance, thanks to an in-built temperature sensor. But this can be easily overcome by connecting a LM35 temperature sensor and making appropriate changes in the code. Also, the LM35 is very small and cheap and hence, __HC-SR04 + LM35__ is used instead of __US-100__.

Ultrasonic rangefinder datasheet: [HC-SR04](https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf)

![img](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRTDvzHSJVXAIOxcrLKuVIqSudYDjfa-nPFVu4mVqomIdIRbq26&usqp=CAU)

Temperature sensor datasheet: [LM35](http://www.ti.com/lit/ds/symlink/lm35.pdf)

A Flipkart smartbuy LiPo battery power bank is used. This particular power bank has a battery life of 5000 mAH, meaning for a current of 2000 mA, it can last for 2.5 hrs which is enough for this competition. It also has safety mechanisms against several threats like over-voltage, over-current and short circuiting.

Power bank link: [Flipkart smartbuy PB](https://www.flipkart.com/flipkart-smartbuy-5000-mah-power-bank-fast-charging-10-w/p/itmffmnx2vxsefsy?pid=PWBFFMNXGDPWHWYA&lid=LSTPWBFFMNXGDPWHWYAUHRTGG&marketplace=FLIPKART&srno=b_1_1&otracker=browse&fm=organic&iid=e4ed338b-618d-4154-add0-7e4d028efbfc.PWBFFMNXGDPWHWYA.SEARCH&ssid=f3l60bt1vk0000001589297332797)

For the wheel part, a N20 6v motor is used. This particular model runs at operating voltage in the range of 3.3-5v. Also, it has an in-built encoder for providing feedback signals. In this competition, size is an important constarint. Hence, even a small change in the required speed may lead to the bot hitting the wall. Hence, encoders must be present to control the stability of the speed.

DC motor datasheet: [N20 6v 100RPM dc motor](https://www.handsontec.com/dataspecs/GA12-N20.pdf)

References:

[Comparison of Ultrasonic sensors](https://ijarcce.com/wp-content/uploads/2019/12/IJARCCE.2019.81120.pdf)

[Interfacing HC-SR04 with arduino](https://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/)


