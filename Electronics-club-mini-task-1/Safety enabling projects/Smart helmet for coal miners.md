__Project 19: Smart helmet for coal miners__

__Description:__
This helmet is integrated with a simple circuit which detects the presence of any harmful gases, temperature and humidity in an area and alerts its user based on the data recieved. A microcontroller and a Zigbee module are used to process and monitor the data. Zigbee is used since it is ideal for wireless PAN networks.

The main components are the microcontroller LPC2138 and the zigbee module. The microcontroller recieves the data from various sensors and based on the threshold values, it will take decisions. A green LED is blinked by default to denote that the conditions are safe. Also, LEDs of different colours are used for different parameters. If a parameter is more than the safe threshold value, the corresponding LED blinks and a buzzer is also activated. Also, data is passed on to a computer through the zigbee module.

The web link for the detailed description of the project: [Smart helmet for coal miners](http://www.onlinejournal.in/IJIRV2I6/145.pdf)

The web link for the description of the microcontroller: [LPC2138](https://www.alldatasheet.com/view.jsp?Searchword=Lpc2138%20datasheet&gclid=EAIaIQobChMI6Kyk382G6QIVzBWPCh3ykAPREAAYASAAEgLImPD_BwE)

The web link for the description of the zigbee module: [XBEE and XBEE Pro](https://www.sparkfun.com/datasheets/Wireless/Zigbee/XBee-Datasheet.pdf)
