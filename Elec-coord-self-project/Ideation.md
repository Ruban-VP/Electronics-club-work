## Ideation of the project 'Automatic billing trolley'

The project 'Automatic billing trolley' is a good project. It is a really innovative solution to reduce time of billing and to enhance customer satisfaction. But the proposed solution can be made better in my opinion. 

Project description link: [Automatic billing trolley](https://nevonprojects.com/auto-billing-mall-shopping-cart-8051/)

The pipeline is:

Mastercard for initialisation => RFID reader => RFID tags from items => RFID reader => Microcontroller => LCD display => Mastercard for finalising => RFID reader => Microcontroller => LCD (displays total bill).

The pipeline can be even more enhanced. Particularly in the current solution, each RFID tag must be configured into the microcontroller by individually configuring them. This becomes a very tedious task for the shop staff. Instead, I felt we can configure the tags for the first time in a computer database and wirelessly connect all the trolley microcontrollers to the computer. To do this, we can use microcontrollers like ESP32 which has in-built Wi-Fi module. Hence, now configuring the items once in the central workstation will enable its identification for all microcontrollers (Trolleys). 

ESP32 pinout diagram:

![img](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/08/ESP32-DOIT-DEVKIT-V1-Board-Pinout-36-GPIOs-updated.jpg?ssl=1)

The main logic is an item is taken if it is scanned odd number of times by a particular master card holder(customer). We can use this logic to make the database preserve the count of items. For example, let us assume the databse contains count of all brushes with unique RFID tags on them. If a particular brush is taken, the count is reduced in the database and also that particular RFID tag is made free for new brushes. But this is temporary as the user may again put the brush back. This reduction in count will only be considered when the mastercard is again swiped for finalising the bill. After the finalisation is done, the RFID tags of purchased items are free and can be used for new items.  

If the star topology method of connecting trolleys with the computer seems a bad idea (owing to the high wireless load to the computer), we can follow a FIFO topology to reduce the load. This may seem illogical since the whole idea of the project is to not form a customer queue. But at least now, we can avoid the manual billing process. Now, the computer would be connected to the first 'N' devices and processes their bills first. These first 'N' devices will be determined by the first 'N' mastercard finalisation swipes. We can have multiple computers to divide the load. Also, the queue is now virtual (depends on the order of finalisation swipes) and not the physical queue.

Another main doubt is regarding possible "Legal thefts" that may happen in this project. If a customer buys some 50 items, he can even add some 2 or 3 costly items without scanning them. Also, in the bill-paying counter, he can just show the bill for 50 items and cheat the cashier. But, remember this project is made only to ease out the billing process. It is estimated that an average shopper spends 43 minutes in the store. The billing may typically involve near 5-7 minutes depending on the number of products bought. Still the security lies at the hands of the cashier. Anyway, the customer must approach the cashier to pay and get his things packaged in a cover or a carton. During that time, the cashier can quickly cross-check the actual item list with that of the one generated in his computer. Still, I feel it is quicker than scanning the barcode on the items one-by-one, entering their amount in the computer and generating the bill.

The components are also available in commercial sites such as [Robu.in](https://robu.in/product-category/electronic-components/) and [Mouser.in](https://www.mouser.in/).

[EM-18 RFID reader](https://bm-es.com/product/em18-rfid-reader/?gclid=EAIaIQobChMIyMfX9J696QIVR6qWCh0ThAdTEAYYAiABEgItFvD_BwE)

[ESP32](https://robokits.co.in/iot-internet-of-things/esp32-development-board-wifi-bluetooth?gclid=EAIaIQobChMImae_lZ-96QIVCsEWBR0hlwSwEAYYAyABEgLKz_D_BwE)

[LCD 20x04 display](https://robu.in/product/lcd-20x4-5v-green-screen-lcd2004-display-lcd-module-arduino/?gclid=EAIaIQobChMIl97o0p696QIVxBwrCh1YFAt7EAYYASABEgIjUfD_BwE)

________________________________________________________________________________________________________________________________________
__References:__

[Connecting ESP32 to Wi-Fi](https://www.megunolink.com/articles/wireless/how-do-i-connect-to-a-wireless-network-with-the-esp32/)

[ESP32 vs 8051](https://www.quora.com/Should-I-work-on-a-microcontroller-8051-or-any-advanced-microcontroller-I-am-in-the-3rd-semester)
(Refer answers of the first two authors, i.e., Allan Schwartz and Allan Mellor.)

[IOT retail](https://www.linkedin.com/pulse/iot-retail-approach-reduce-billing-time-swati-bansal)
(Refer the penultimate paragraph for reduction in billing time and anti-theft protection).
