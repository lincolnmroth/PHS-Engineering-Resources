# Sensors

Sensors are how your robot reads in the environment around it.

## Switches/buttons:

Switches and buttons are the simplest type of sensor. I'll first go over some general info about switches and buttons, and then go into detail about some of the more common types.

The only difference between a switch and a button is that if you actuate a switch it stays in the opposite position. They work identically, which is by making contact between conductors to open or close a circuit. Switches and buttons can either be Normally Open \(NO\) or Normally Closed \(NC\). If a switch is NO, the actuation of the switch/button closes a circuit, while a NC button/switch would be closed until actuated, which would open the circuit. Switches/buttons do have a max amperage they can carry before they blow up. Do not push this limit. I have tried in the past, and it ends rather poorly.

For future reference, when reading a button with a micro-controller, you read it as a digital value, and you need to either use the micro-controllers pull-up or implement a pull-up yourself.

### Breadboard button

![](/assets/breadboardbutton.png)

Breadboard buttons are just very basic buttons. They are NO, and they connect the left and the right side. For example in the blue button in the picture above the pins in rows 1 and 3 are normally not connected, but when the button is pressed, they connect.

These can not handle much current, and may blow up if you push them too far.

### Arcade button

Arcade buttons work identically to breadboard buttons except they look cooler.

![](/assets/arcadebutton.png)

### E Stop

I love e-stop switches, as they are satisfying to use, and usually are used in applications when something dangerous could happen.

![](/assets/estopswitch.png)

To close the circuit, you rotate the big red button, and when something inevitably goes wrong, you hit the big red button and it disconnects the circuit immediately. e-stops are used frequently on the main power lines of a machine, so in the event of a failure, it is easy to safely disconnect power quickly.

### Key switch

Key switches are switches that require a key to close a circuit.

![](/assets/keyswitch.png)

### microswitch

Microswitches are switches that are very easy to actuate. They are frequently used in 3D printers when the printer homes its axis. They usually have 3 leads, one common, one NC, and one NO.

![](/assets/microswitch.png)

### dip switches

Dip switches are frequently used for representing binary numbers. They are an array of small switches.

![](/assets/dipswitch.png)

## Potentiometer

See [Basic Circuits](/general-resources/electronics/basic-circuits.md)

## Ultrasonic Ranger

![](/assets/hcsr04.png)

Ultrasonic rangers are sensors that can measure distance to an object using a technique similar to echolocation as used by bats. I'm going to mainly talk about the HC-SR04 variety which are extremely common, fairly reliable/accurate, and really cheap \(like cents\). There are fancier, more expensive kinds, but they are fairly unnecessary for hobby use.

One thing to always look for when using any sensor is the [datasheet](https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf). Looking at the datasheet, According to the electrical specs, it takes in 5v and outputs 5v. Therefore if you are running a device that uses 3v3 logic \(like Raspberry PI!!\), you will need a voltage [divider](https://en.wikipedia.org/wiki/Voltage_divider) to step down the output voltage. Another very important part of the datasheet is the Timing diagram. The diagram tells us exactly how to get information from the sensor. I'll outline the steps here,

1. send a 10 microsecond pulse to the trigger pin. You do this by giving the trigger pin 5v.
2. You read the the pulse width from the echo pin, you can use the pulseIn function in arduino.
3. Take that value in microseconds and divide it by 58 to get the distance in centimeters

![](/assets/Screen Shot 2018-03-30 at 12.05.51 AM.png)

## IR

Infrared sensors are used to measure infrared light. This can be useful for detecting fire. IR sensors just look like opaque, black LEDs like this:

![](/assets/flameled.png)

These work by having the increase in ir light decrease the resistance. You can measure the amount of ir light sensed by applying a voltage, and reading the output voltage.

Another really cool application of these is to be used as distance sensors similar to the ultrasonics above. [Here's](http://education.rec.ri.cmu.edu/content/electronics/boe/ir_sensor/4.html) how they work. These also have an analog output, which means they change the voltage based on the distance. The main issue with these sensors is this; the output function is not a function. If you graph distance over analog voltage, instead of how the graph below does it, you see that it is not a function. This means if an object gets too close, it will read the same as if it is further away.

![](/assets/irgraph.png)

## Photoresistor

Photoresistors are very simple as well. They are variable resistors that instead of being based on position like a potentiometer, the resistance is based off of light intesity.

![](/assets/photoresistor.png)

## Hall Sensor

Hall sensors are sensor capable of measuring magnetic field.

## Rotary Encoder

![](/assets/crapyencoder.png)

![](/assets/fancy encoder.png)

Rotary Encoders a way of measuring how far something has rotated. There are two types, absolute and incremental. I don't really like absolute, so I rarely use them. I use incremental encoders all the time, and I absolutely love them, they are one of my favorite types of sensors.

There are the crappy encoders that are used as dials on like the front of 3d printers or on radios or whatever, with their little clicky wheels. These are dirt cheap and useful for those types of applications, but it starts to get fun once we start getting into the nice high quality quadrature encoders. Quadrature encoders have a spinning disk with perforations in the side. [Here's](https://www.pjrc.com/teensy/td_libs_Encoder.html) a good page on how encoders work. There is a little animation thing that is really great for understanding how they work.

![](/assets/Screen Shot 2018-03-30 at 9.28.24 PM.png)

## Color sensors

Color sensors are sensors that measure color. I'll talk about both grayscale sensors and full color sensors.

### Grayscale

To measure grayscale, it is actually rather simple. You just need an led and a photoresistor, and you can measure how much light is reflected. Easy as that.

![](/assets/grayscale.png)

### Full Color

Measuring full color is a lot harder. You need a fairly complicated sensor, but luckily awesome companies like Adafruit and Sparkfun have made boards that make them really easy to use. These boards read the sensors and then can communicate the readings over i2c \(Inter-integrated circuits\), which is easy for arduinos or raspberry pis to use.

![](/assets/colorsensor.png)

## IMUs

IMUs, or Inertial Measurement Units, are another one of my favorite sensors. They measure specific force, angular rate, and sometimes magnetic field. Basically they can measure acceleration, both linear and angular, angular velocity, and orientation. They do this by having \(at least\) a 3 axis accelerometer, gyroscope, and magnetometer. If you are looking for one for your robot, I recommend the BNO055, which also uses i2c.

![](/assets/bno55.png)

But IMUs are found on many other things such as rockets, airplanes, and helicopter.

## Lidar

Yet another type of distance sensor, LIDAR is the most accurate and best but also the most expensive. LIDAR is what is used on autonomous vehicles and those kinda things. As they have an extremely high refresh rate \(1khz or even more\) Many lidar sensors are attached to spinny things which allow them to 3 dimensionally map a space using only 1 sensor.

## Cameras

Probably the most powerful sensor, but hardest to use is the camera. Y'all already know what a camera is, but using it as a sensor is very difficult. This is because you need to use computer vision. If you are doing this, I highly reccomend OpenCV, a python library for computer vision.

-lmr

