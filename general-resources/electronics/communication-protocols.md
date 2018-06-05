# Communication Protocols

So I'm not going to go into how com protocols actually work because they are relatively complicated and my ability to put idea into words is rather horrible, and it's kinda useless for what y'all'll \(that's definitely not a word but I'm sticking with it\) will be doing with it. If that's something that interests you, google it or talk to me.

I'm just going to go over these and what they are used for. I'm not going to go into how to implement them because usually there are arduino libraries to do it. Also coding is hard.

## $$I^2C$$ \(Pronounced eye - two - see or eye - squared - see\):

[I2C](https://learn.sparkfun.com/tutorials/i2c) \(which stands for inter-integrated circuits\) is a communication protocol which is commonly used in hobby electronics due to the fact that it is multi-master and multi-slave. To wire devices using I2C, attach all the 5V pins together, all the GND pins together, all the SCL \(clock\) pins together and all the SDA \(Data\) pins together. Many common boards use I2C to communicate \(as arduino and RPi's both have great support for I2C\) like Adafruit's IMU, GPS, and many of their shields/hats \(and many more\).

## [SPI](https://learn.sparkfun.com/tutorials/serial-peripheral-interface-spi)

SPI is a protocol that also occasionally shows up in hobby parts. It can do 10MHz up and down at the same time \(I think they call this like full duplex?\), but it also can only have one master and it uses more pins than I2C. Also it, like i2c, is syncronous \(it has a clock pin\) which prevents the need for a predefined baud rate.

## [Serial](https://learn.sparkfun.com/tutorials/serial-communication/all)

So serial is fairly common in consumer electronics. USB \(Universal Serial Bus\) uses Serial to communicate. This uses two pins TX and RX  \(and power and ground\). As it is asyncronous, it relies on the master and the slave having a similar clock, and a predefined rate of communication \(baud rate\)

## [CAN](https://en.wikipedia.org/wiki/CAN_bus)

Can is my absolute favorite. It's used in very high end robotics and also in many cars \(In the form of [OBDII](https://en.wikipedia.org/wiki/On-board_diagnostics)\)



## WIFI

WIFi. Our entire lives revolve around wifi, but integrating it into electronics isn't particularly simple. But some chips have made it easier. To use WIFI, either get a wifi board off of adafruit or sparkfun, or use an ESP8266.

## Bluetooth

There are two types of bluetooth, normal bluetooth and bluetooth low energy \(BLE\). Bluetooth is radio based, and is good for low range communication.

## Infrared

Don't use IR unless it's for a tv remote, then go right ahead.



-lmr

