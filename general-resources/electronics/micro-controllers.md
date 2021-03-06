# Microcontrollers

Ok, so that was kinda a misleading title, as we'll go over microcontrollers but also other controller types.

Also this may be pretty long, since I'll be going over controllers which is a very broad topic.

## Types of Controllers we will go over:

Here are the types of controllers we will go over. I will focus mainly on arduinos , but I will go over as many different controllers as possible.

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

IOREF - IOREF is the reference voltage for the digital IO \(input output\). You will probably never use this, as it is so 3rd party hardware knows whether your arduino is running at 3v3 \(3.3 volts\) or 5v.

RESET - When the reset pin is shorted to ground, it resets the arduino

3V3 - Is a 3.3 v regulated supply

5V - Is a 5v regulated supply

GND - Is ground

VIN - VIN is used for externally powering the arduino, it can accept 7-12 volts

A0-A5 - Analog pins allow you to read voltage. they return a value between 0 and 1023 where 0 is 0 volts and 1023 is 5 v

AREF - AREF is similar to IOREF, but for analog pins

GND - also a ground

D0-D13 - Digital pins can read and write digital signals. Digital means that they work binarily \(is that even a word, I mean that it uses binary\).  They either read HIGH \(5v\) or LOW \(0 V\), and can output either HIGH or LOW as well. This can be used for something like a button. D13 is attached to an LED on the board, which is very useful for debugging purposes.

PWM - Outputting an analog voltage is much harder. So the way this is done is actually using digital pins. The pins with the squiggles can use PWM \(Pulse Width Modulation\) to emulate an analog signal. PWM works by rapidly pulsing the pin so that it is only high for a small amount of time, which is similar enough to analog values for most applications.![](/assets/pwmexample.png)

Interrupts - pins marked as interrupts can be accessed incredibly quickly, where you have code that on a state change of the pin \(High to low, or low to high\), the code stops what it is doing and immediately runs the code associated with the pin. These are really useful.

SDA + SCL - SDA and SCL are used for i2c devices. I will go over this more in [Communication protocols](/general-resources/electronics/communication-protocols.md)

TX + RX - TX  and RX are used for serial devices. I will go over this more in [Communication protocols](/general-resources/electronics/communication-protocols.md)

#### Software

Here comes the fun part. I really have not found any good resources for learning Arduino programming, so I'm going to try and teach as much as possible, but as I'm not a software guy, I'll try my best and see what happens. Also I will be assuming you know some of a C based language \(C, C++, Java, ....\), if you don't, you might have to do a bit of extra googling.

The first step is to download the [arduino IDE.](https://www.arduino.cc/en/Main/Software)

We'll first go over the general structure of arduino code and the arduino IDE.

Here are the two necessary parts of any arduino sketch \(sketch is what arduino calls programs\).

```cpp
void setup() {
  // put your setup code here, to run once:

}

void loop() {
  // put your main code here, to run repeatedly:

}
```

The setup function is used for setting up the program, so everything in it gets run once at the beginning of the program. The loop function gets run after the setup and runs repeatedly until the arduino gets resets or loses power.

What this would kinda look like in pseudocode is

```
program()
    setup()
    while True:
        loop()
```

The "Hello World!" equivilient in Arduino is called blink. You can open it by going to File --&gt; Examples --&gt; Basics --&gt; Blink, or by copying it from here.

```java
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.

  This example code is in the public domain.
 */

// Pin 13 has an LED connected on most Arduino boards.
// Pin 11 has the LED on Teensy 2.0
// Pin 6  has the LED on Teensy++ 2.0
// Pin 13 has the LED on Teensy 3.0
// give it a name:
int led = 13;

// the setup routine runs once when you press reset:
void setup() {                
  // initialize the digital pin as an output.
  pinMode(led, OUTPUT);     
}

// the loop routine runs over and over again forever:
void loop() {
  digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);               // wait for a second
  digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);               // wait for a second
}
```

Let's walk through the code, and then go over how to put it onto an arduino.

The first dozen or so lines \(until int led =13\) are comments, which does not affect your program, but does not mean you shouldn't use them. Documenting you code is very important.

So now lets look at the first line of code:

```
int led = 13
```

This creates a variable called led that is an integer and has a value of 13.

Next in the setup function we see pinMode\(led, OUTPUT\)

This tells the arduino that we want the digital led pin \(D13\) to be used as an output device, not an input device.

Then we see the loop\(\) which is the part of the program that does the blink. First it uses writes the value of HIGH \(5v\) to the led pin \(13\) which turns the LED on, and then delays \(imagine thread.sleep or something like that\) for 1000 milliseconds, or 1 second. Then it turns the led off using the digital write command, and waits another second. This repeats indefinitely, leaving the LED blinking every second.

Uploading code to the arduino can be a huge pita, but there are two main problems that I see that are very easy fixes. First you need to tell the IDE what board type you are uploading to. You select this in Tools --&gt; Boards. Secondly you need to tell the IDE which port you are uploading to, which can be found in Tools --&gt; Port. Once this is correct, if you hit upload \(and have the arduino plugged into your computer via a USB A - USB B cable\) the onboard LED should start to blink.

Digital write is how you output digital signals from the arduino. This can be used for LEDs, motors, and much more, as long as it only needs to be on or off.

Now let's figure out how to print \(because Hello World! is in fact mandatory, even when dealing with hardware\)

To print, we have to send the data from the arduino to the computer and have the computer display the information. The was we do this is with Serial communication. I'll explain how it works in the [Communication protocols](/general-resources/electronics/communication-protocols.md) article.But here is an example program of how to print to the console.

```
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.

  This example code is in the public domain.
 */

// Pin 13 has an LED connected on most Arduino boards.
// Pin 11 has the LED on Teensy 2.0
// Pin 6  has the LED on Teensy++ 2.0
// Pin 13 has the LED on Teensy 3.0
// give it a name:
int led = 13;

// the setup routine runs once when you press reset:
void setup() {                
  // initialize the digital pin as an output.
  Serial.begin(9600);
  Serial.println("Hello World!");
  pinMode(led, OUTPUT);     
}

// the loop routine runs over and over again forever:
void loop() {
  digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
  Serial.println("LED is on!");
  delay(1000);               // wait for a second
  digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
  Serial.println("LED is off!");
  delay(1000);               // wait for a second
}
```

The two commands used are Serial.begin and Serial.println. Serial.println is the same as say System.out.println in java. Serial.begin\(9600\) is starting the serial communication at a baud rate of 9600. Baud rate is the rate at which bits are communicated. 9600 baud is actually really slow, but way better than you'll probably ever need. To view the output, when your code is running, hit the magnifying glass in the top right corner to open the Serial Monitor.

Next we'll learn how to get input from the real world, both using analog and digital.

We'll start by learning how to read from a button, which is digital. BUT, this is NOT how you should read from buttons. You should use interrupts, which I'll go over in a bit.

```
const int buttonPin = 9;

void setup() {
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);      
  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT_PULLUP);     
}

void loop(){
  // read the state of the pushbutton value:
  int buttonState = digitalRead(buttonPin);

  // check if the pushbutton is pressed.
  // if it is, the buttonState is HIGH:
  if (buttonState == HIGH) {     
    // turn LED on:    
    digitalWrite(ledPin, HIGH);  
  } 
  else {
    // turn LED off:
    digitalWrite(ledPin, LOW); 
  }
}
```

What this code does is it reads the state of buttonPin, and if it is high, turns an led on, and turns the led off if the state is low. \(I understand you can just throw a button in series with an led, this is just for demonstrational purposes.Here are a few things to take note of: digitalRead returns HIGH or LOW, but you could also use 1 or 0, or true or false. Secondly, we use Input\_pullup, because it allows us to not need resistor with the button.

Now we're going to read an analog signal. As we don't know how to output analog signals \(yet\), we'll just use serial to print out the reading, but we'll do it as a percent to make it more interesting.

```
const int analogPin = A0;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  reading = analogRead(analogPin);
  percentage = map(0, 1023, 0, 100, reading);
  Serial.print(percantage);
  Serial.println("%");
}
```

We are using [map](https://www.arduino.cc/reference/en/language/functions/math/map/) which allows us to map the range 0-1023 to 0-100. analogRead always returns a value between 0 and 1023. This code could be used for reading an infrared distance sensor or something like that.

Now we'll finally learn how to do analog output using PWM.

There are actually a few ways of doing this depending on your use case.

We'll go over two ways, the analogWrite method and the Servo library. The analog write is used for outputing a constant voltage. The servo library is for controlling servos \(duh\).

We'll start with analogWrite

In my example, I'll use it dim an LED based off an analog input.

Another thing to mention is that even though it would make sense that only analog pins can do analogWrite, that is NOT the case.  Because it uses PWM, only PWM enabled pins can use it \(PWM pins are marked with a tilda usually\)

```cpp
int inputPin = A0;
int ledPin = 9;

void setup() {
  // put your setup code here, to run once:
  pinMode(ledPin, OUTPUT)
}

void loop() {
  // put your main code here, to run repeatedly:
  inp = analogRead(inputPin);
  out = map(0, 1023, 0, 256, inp);
  analogWrite(ledPin, out);
}
```

As analogWrite takes a value between 0 and 256, which is we need to map the input value.

Now lets make a servo move in accordance to an analog input.

```
#include <Servo.h>

int inputPin = A0;
Servo motor;

void setup() {
  // put your setup code here, to run once:
  pinMode(ledPin, OUTPUT)
  motor.attach(9);
}

void loop() {
  // put your main code here, to run repeatedly:
  inp = analogRead(inputPin);
  out = map(0, 1023, 1000, 2000, inp);
  motor.writeMicroseconds(out);
}
```

There's a fair bit of new stuff in here, so let's go over it.

The first line is how we import the servo library

The third line is creating an instance of the Servo object

The attach line is telling the servo object which pin to use.

The motor.writeMicroseconds takes a value between 1000 and 2000, you can see my [Making stuff move](/general-resources/electronics/making-stuff-move.md) article on why that is.

That's most of the basic arduino stuff, so I'm just going to give you some code examples for commonly used components.

I am working \(kinda almost started\) a robotics Arduino/RPi library for y'all to use. If you ask me about it, it's more likely I"ll actually do it.

Ultrasonic Distance Rangers

```
*
* Ultrasonic Sensor HC-SR04 and Arduino Tutorial
*
* by Dejan Nedelkovski,
* www.HowToMechatronics.com
*
*/
// defines pins numbers
const int trigPin = 9;
const int echoPin = 10;
// defines variables
long duration;
int distance;

void setup() {
    pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
    pinMode(echoPin, INPUT); // Sets the echoPin as an Input
    Serial.begin(9600); // Starts the serial communication
}

void loop() {
    // Clears the trigPin
    digitalWrite(trigPin, LOW);
    delayMicroseconds(2);
    // Sets the trigPin on HIGH state for 10 micro seconds
    digitalWrite(trigPin, HIGH);
    delayMicroseconds(10);
    digitalWrite(trigPin, LOW);
    // Reads the echoPin, returns the sound wave travel time in microseconds
    duration = pulseIn(echoPin, HIGH);
    // Calculating the distance
    distance= duration*0.034/2;
    // Prints the distance on the Serial Monitor
    Serial.print("Distance: ");
    Serial.println(distance);
}
```

## Small Computers

* Raspberry Pi
* Jetson TK1

If you need more power than an arduino you can go to a controller that has an OS \(operating system\) and all that. We use the Raspberry Pi a lot, but I've always wanted to try a Jetson TK1 as they are much more powerful, but they are also much pricier.

As I've never actually used a Jetson \(pls get me one to play with\), I'm not going to explain how to use it, since I don't know how.

### RPi:

#### Hardware:

for a nice pinout of the raspberry pi, I highly recommend [http://pinout.xyz](http://pinout.xyz)

![](/assets/rpi.png)

#### Software:

So the RPi is a full blown computer and usually runs a linux distro. If you are bad with bash, learn that.

Usually we code our Pi's with Python and the [RPi.GPIO](https://pypi.org/project/RPi.GPIO/) library, but recently I've been messing with ROS and cpp, so that might change in the near future.

## Computers

* PC's 

You can use full blown computers as robot controllers, but it's unlikely you'll ever do this \(I've only done it once\). If you are using a computer you should either be good enough at coding to figure everything out yourself, OR you should use ROS \(Robot Operating System\), which I will probably go over in a software article.

If you do use a PC, the Intel NUC's are a popular choice

-lmr

