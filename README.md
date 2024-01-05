# CYD-ESPHome-Sensors

**CYD Temperature and Air Quality Monitor for ESPHome**

![](RackMultipart20240105-1-e40uff_html_3a0e8b23453c45be.jpg)

1. **Set up your CYD in ESPHome as usual use this yaml (after editing it with your setup)**
2. **Create a folder named fonts in your ESPHome folder and copy the file fonts/lucon.ttf there.**
![Connections](https://github.com/gjashley/CYD-ESPHome-Sensors/assets/2442807/596ed6d1-4255-4f1f-9c25-c8e5e67d7e92)

Although we're using ESPHome to set-up, all the sensors are local, so it doesn't rely on any HA devices for data, it doesn't even pull the time from HA ... so it _should_ operate outside of your HA network. It _will_ appear as a device in Home Assistant with ALL the data, so you can create dashboards, charts etc to your heart's content.

**PARTS:**
These are the sensors I used, but you should be able to substitute any i2c sensor/device as long as it is supported in ESPHome and you use the appropriate configuration [https://esphome.io/components/sensor/](https://esphome.io/components/sensor/)
1. CYD ESP32-2432S028R - The base single USB unit, I didn't test it on any other variant.
2. BME680 i2c Temperature, Humidity, Pressure and Gas Sensor
    I used Adafruit's breakout board [https://www.adafruit.com/product/3660](https://www.adafruit.com/product/3660).
3. PMSA003i i2c Air Quality Sensor
    I used Adafruit's breakout board [https://www.adafruit.com/product/4632](https://www.adafruit.com/product/4632).
    Make sure you get the PMSA003_ **i** _, the _ **i** _ stands for i2c (other versions use UART)
4. SH1106 i2c 0.96" OLED Display (optional - I just wanted to see if it worked)
    These are very common, I think I got a bunch from our favorite overseas electronic supplier, they also have them at our favorite mega online store.
5. JST MX 1.2mm 4 pin male to female Dupont connector - like the one which came with your CYD
6. JST SH 4 pin 1.0mm 4 pin male (STEMMA QT) to male Dupont connector

    [CYD -\> F/M Dupont -> BME680 STEMMA QT in]
7. JST SH 4 pin 1.0mm 4 pin male (STEMMA QT) to JST SH 4 pin 1.0mm 4 pin male (STEMMA QT)

    [BME680 STEMMA QT out -> PMSA003i STEMMA QT in]
8. JST SH 4 pin 1.0mm 4 pin male (STEMMA QT) to female Dupont connector - my SH1106 had male headers already installed.

    [PMSA033i STEMMA QT -> SH1106]

NOTE: All my cables had the same color scheme, but that's not always the case, check all the pins match:
    
    VCC - **RED**
    GND - **BLACK**
    SCL - **YELLOW**
    SDA - **BLUE**

I haven't thought about a case, because I don't have a (functional) 3d printer, I'll probably just screw it together with layers of that acrylic 'case' that you sometimes get with the CYD. I may shorten, re-terminate or solder some of the connections, I have a non-stemma BME680 board which was cheaper lying around, you can get a bare PMSA003i, but it likes 5v and the Adafruit board has a boost converter

I'd like to try other sensors, and if I have time, I can look at adding display graphics … or maybe even graphs!

Any ideas or suggestions would be gratefully received,

OK, I think that's about it for now.

Boom Shanka

**Gareth**
![Screen_PMSA](https://github.com/gjashley/CYD-ESPHome-Sensors/assets/2442807/bed4efa7-0bdc-49e7-9334-100d35b80135)
![Screen_BME](https://github.com/gjashley/CYD-ESPHome-Sensors/assets/2442807/83643ad6-f2f3-45e0-b2a4-67fb0224b840)
![Screen_SH1106](https://github.com/gjashley/CYD-ESPHome-Sensors/assets/2442807/9deca067-4bd1-494e-9e47-9c7ccd14a0a8)
