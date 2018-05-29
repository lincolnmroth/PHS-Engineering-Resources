# Microcontrollers

Ok, so that was kinda a misleading title, as we'll go over microcontrollers but also other controller types.

Also this may be pretty long, since I'll be going over controllers which is a very broad topic.

## Types of Controllers we will go over:

Here are the types of controllers we will go over. I will focus mainly on arduinos and Pi's, but I will go over as many different controllers as possible.

* Micro-controllers
* Small computers \(RPi, JETSON TK1\)
* Computers \(PC's, NUCs\)

## Microcontrollers

All the micro-controllers I will go over will be arduino compatible, which means you can program them with the Arduino IDE.

* Arduinos, these are a family of microcontroller that have a great ecosystem around them
* Teensy, These are a variation of arduino but are AVR based and much more powerful
* Other, there are other non-arduino compatible microcontrollers, but I won't go over them

### Arduino:

Arduino is a open-source electronic prototyping platform. There are also many different types of arduinos with a wide variety of features \(everything from wifi to LoRa to GPS\), but I will explaining how to use the most basic one, the Arduino Uno, which should be applicable to every other arduino.

I will start with the hardware part and then go onto the software

#### Hardware:

Arduinos allow you to write code to interact with hardware. 

Here are a few general warning:

Do not draw more than 40 mA from a pin, and 200 mA from the whole board, or else things may go kaplooie



The way the arduino can interact with hardware is via GPIO \(General Purpose Input Output\)

![](/assets/arduinounopinout.png)

I'll go through all the different types of pins and explain what they can and can't be used for

I'll start on the left and go down and then do the right side, followed by the middle of the board.

IOREF

RESET

3V3

5V

GND

VIN

A0-A5

AREF

GND

D0-D13

#### Software

## Small Computers

* Raspberry Pi
* Jetson TK1

### RPi:

#### Hardware:

#### Software:

## Computers

* PC's \(Nucs\)

-lmr

