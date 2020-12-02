__Project 2: Hexapod__

__Problem statement:__
To develop a visual representation of a 18 DOF hexapod on a computer screen using the data obtained from the sensors attached on it.

__Design:__
In order to create a visual representation of the bot on a computer screen, we need some modelling software like AutoCAD or Fusion 360. This computer model should have 18 different-yet-connected parts that together make the Hexapod. Each part must be attached to a 6DOF IMU sensor in the physical model. Using some software, the computer generated 3D model must be programmed exactly to mimic the motion of the physical model. For this purpose, the data obtained from the IMU sensors must be integrated via a microcontroller and must sent to the computer using a serial port or even by wireless technology. This is the basic idea. The pipeline is:

Data from IMU sensors => Microcontroller => Computer's microprocessor => 3D model moving according to the data acquired and the code programmed into it

Pipeline flowchart:

![flow](https://github.com/Ruban-VP/Electronics-club-mini-task-3/blob/master/Project%202/Data%20from%20IMU-page0001.jpg)

Among this pipeleine, the only area where we have to think about using the wiring and hardware is the __'Data from IMU to microcontroller'__ part since in other areas, the wiring is internal (already present within computer) and hence, in those areas of the pipeline, the major task would be proper coding. This is the only area where we must think about proper wiring and hardware design and also how to code the microcontroller.

* __Basics of the sensor and microcontroller:__

  So our first task would be to choose the IMU sensor and the microcontroller board. I chose:

  __MPU6050 6DOF sensor__

  __Arduino UNO__

  The main reasons are: 

  1. MPU6050 is comparitively less expensive and also has better performance than other 6DOF sensors.

  2. Has I2C communication interface compatible with arduino and various other external devices like 3DOF magnetometers

  3. Has an in-built temperature sensor and DMP (Digital motion processor)

  4. 6DOF sensor is enough since we need to track only the motion and the exact coordinates aren't needed

  5. Arduino UNO is used since it supports I2C protocol and also, has its own programming IDE.

  6. A library is also present in arduino exclusively for MPU6050
  
  Interfacing MPU6050 with arduino:
  
  ![tmp](https://components101.com/sites/default/files/inline-images/Arduino-MPU6050-Circuit.png)

  Refer this tutorial: [Connecting MPU6050 with Arduino UNO](http://www-robotics.cs.umass.edu/~grupen/503/Projects/ArduinoMPU6050-Tutorial.pdf)

* __Address of the MPU6050 and integrating all sensors with the Arduino:__

  The MPU6050 sensor has an AD0 pin, which is known as its address pin. It can be made high or low. Depending on this pin's value, it     can have two addresses {either 0x68 or 0x69). But we have to integrate 19 IMU sensors in our model. Hence, 2 addresses won't be enough   to distinguish all 19. Instead, we can assign one address to one of the IMU sensor and assign the other address to all the other     s   sensors. There are many ways to do it:

  1. Using decoders to make all address pins but one
  
  2. Using GPIO expanders to do the same
  
  But in all those cases, the master serial clock pin (SCL) and master serial data pin (SDA) will be connected to all the 19 sensors at   all time meaning the load is high. A I2C interface can support 128 slave devices theoretically but can only have 8 slave devices in     practice, owing to the high load. So, in order to connect all, we need a switching device that connects only one slave at a time and     disconnects the other slaves. Fortunately, there is an IC for this purpose. The IC __TCA9548A__ is a 1-8 swiching multiplexer which     helps a master I2C device to be connected to 8 slave devices and will activate connection for only one device at a time based on the     address programmed into it. It has an 8-bit control register meaning 8 distinct slave devices can be connected to it (A channel will     be enabled only if the corresponding control register bit is logic HIGH and is followed by a STOP condition. For more details, refer     the datasheet). It also has 3 programmable address bits meaning we can connect these ICs to themselves as downstream channels with   8   different addresses.
  
  Using this technique, we can connect all 19 devices to a single arduino controller with switching action. So we will need 3 TCA9548A     ICs. All 3 will be connected in parallel to the master bus (Arduino) I2C pins (A4 and A5). Hence, we have 24 channels out of which the   first 19 channels can be used.
  
  The main advantage of this IC is it has an enable option. This is a very much useful property since it ensures only one device is       connected to the master bus at a time. For eg., if we wnat the 4th channel data, we have to enable the first IC, select channel 4 and   disable the other 2 ICs. Similarly, for channel 15, enable 2nd IC, select its 7th channel and disable the 1st and 3rd ICs.
  
  1-8 fan-out of the IC:
  
  ![tmp](https://mindbleach.com/words/wp-content/uploads/2012/10/single.png)
  
  Even though these ICs have so much advantages, they don't have a 1-8 fan-out of interrupt line. So the interrupt line of the master     I2C bus (Arduino digital pin 2) must be connetected externally to all these devices. 
  
  References:
  
  [Basics of I2C protocol](https://mindbleach.com/words/2012/10/23/i2c-and-device-limits/)
  
  [I2C bus device limit explained](https://www.bluedot.space/tutorials/how-many-devices-can-you-connect-on-i2c-bus/)
  
  [TCA9458A datasheet](www.ti.com/lit/ds/symlink/tca9548a.pdf?&ts=1589020393368)
  
  [TCA9458A online purchase site](https://robu.in/product/cjmcu-tca9548a-i2c-8-channel-multiple-extensions-development-board/?gclid=CjwKCAjwqdn1BRBREiwAEbZcR0SE2WfNGwql-okai2mo6TpLHpar7hQKXGhtXBbQ1cr-zQCDdRh8JBoCMYoQAvD_BwE)

