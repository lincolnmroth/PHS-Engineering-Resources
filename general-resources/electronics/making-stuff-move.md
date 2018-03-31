# Making stuff move

So making stuff move is my favorite part of robotics and is my main focus and is the area that I am the most knowledgable, so this will either be a very good article, or it will be horrible. My apologies in advance if it's completely unclear and discombobulated.

## Motors

* Standard Brushed DC Motor
* Hobby Servo
* Stepper motors
* BLDC Motors
* Industrial Servos

### Standard Brushed DC Motor

Standard dc motors are the simplest type of motor. They are the only type of motor that you can just plug into a battery and have it spin, which is why they are what you see in your physics class when learning basic e&m. They are very simple, cheap, and can be relatively powerful, but they do break more easily than other types of motors, and also have very low torque at low speeds, which can be a real pain sometimes.

#### How they work:

Brushed DC motors work by having an internal rotor with two Electromagnets, that is inside a casing that has 2 permanent magnets. The wires that carry DC current are attached to a commutator which pretty much \(not exactly but whatever\) turns the DC Current into AC \(Alternating current\). This has the two electromagnets switch polarity very quickly which allows the magnetic forces to force the rotor to spin. Because of this speed and torque are directly proportional, which can be rather problematic for certain applications.

#### How to control them:

There are many ways to control Brushed DC Motors, so I'll try and focus only on the important ones:

* Just plugging it in
* Potentiometer
* H-bridge
* High amperage motor drives \(The RageBridge is my favorite, so I'll talk about that one\)

One thing to never do is over volt your motors. Someone \(definitely not me\) did that two nights before a SciOly competition and blew up 3 motors, which was bad. very bad.

##### Just plugging it in

Brushed DC motors are nice since you can just plug them into a battery and they will spin, and if you switch the positive and negative leads they spin in the opposite direction. So if you only need one speed and one direction, you can just have an arduino power it \(probably through a MOSFET, but you get the point\)

##### Potentiometer

If you want to be able to control speed, all you need to do is change the voltage. You can do this using an analog output from an arduino \(It's not actually analog out, but its PWM, but I'll go over that later\), or you can have a constant power supply and change the resistance using something like a potentiometer.

##### H-Bridge

H bridges allow you to control the direction of a DC Motor. Usually you get them in packs of two \(called dual h-bridges\). Here is the pinout.

![](/assets/hbridghpinout.png)

This hbridge above can control two motors, but we'll only worry about one. To power the hbridge, it needs 3.3v to the Vss pin. Also the motors need separate power, which gets connected to Vs. All 4 GNDs get connected to both the ground of the mtor and the 3.3v supply\(which is probably an arduino\). The two motor leads go to Output 1 and Output 2. Input 1 and input 2 are you control the direction. Here are the results

| Input 1 | Input 2 | Result |
| :--- | :--- | :--- |
| 5v | 5v | Full Brake |
| 5v | 0v | Motor spins one way |
| 0v | 5v | Motor spins the other way |
| 0v | 0v | Coasting |

This allows you to change direction, and if you change the voltage to Vs, you can change the speed as well.

##### RageBridge

You can get fancier motor drives that can handle extremely large currents. The ragebridge, designed by the lord and savior of combat robotics, Charles Guan,  can handle up to 40A, which is absolutely crazy. It is an expensive driver \($200\), but is definitely what I would recommend for larger projects, like combat robotics, or something like that.

![](/assets/ragebridge.png)

#### Use cases:

Brushed DC Motors are used in a very wide variety of application. They are  used in everything from cordless drills, to Oppurtunity \(mars rover\). They are being used less and less due to BLDC motors, but they are still used in a variety of applications due to their low cost and ease of control. Also when paired with a quadrature encoder \(see [sensors](/general-resources/electronics/sensors.md) page\), they can be made to very accurate as well.



### Hobby Servo Motor

This section is going to be about servo motors meant for hobby use. Industrial servos are VERY different. I will go over them later.

A servo is a type of motor that \(usually\) has closed-loop control, which means they have a sensor to know about how far they've spun. This allows you to give them an angle to go to, and they will go to it. There are another type of hobby servo motor that are non-continuous, and quite frankly I'm not sure why they are called servos, except for the fact the the control signal is the same.

#### How they work:

##### Standard \(Non-continuous\):

Heres a picture of a taken-apart servo to help illustrate how they work:

![](/assets/servoteardown.png)

So basically there is a brushed dc motor \(see above\) with a gear box to increase torque and reduce the speed. This is controlled by a closed-loop motor controller that reads the angle that the output shaft is at. This allows the motor to go specific angles. The downside of this is these motors can rotate 180 degrees.

##### Continuous:

Continuous rotation servos are the same as before, except they don't have a potentiometer, so you can't specify angle, only direction and speed, which you could already do with an hbridge. 

#### How to control them:

Servos are controlled using a PWM signal. PWM \(Pulse Width Modulation\) is a square wave, I don't want to explain it so heres a picture and an [article](https://learn.sparkfun.com/tutorials/pulse-width-modulation).

![](/assets/pwm.png)

Servo's have 3 wires, a red one for power \(5-7.2 v usually\), a black one for ground, and a white one for the PWM signal.

#### Use cases:

Servo motors are used a lot in inexpensive projects. For example, they are used in rc planes to control the control surface \(see [flight](/general-resources/flight.md) section. Continuous rotation servos are used in cheap robots, but I try to never use them. 



### Stepper Motor

Stepper motors are motors that have pretty high torque and pretty low speed. What makes them special is their ability to "step". They step a certain fraction of a degree every time allowing them to be used when accuracy is needed. 

![](/assets/allthenemas.png)

#### How they work:

![](/assets/howstepperswork.gif)

[Heres](https://learn.adafruit.com/all-about-stepper-motors?) a good article on how steppers work

#### How to control them:

#### Use cases:



### BLDC Motor

#### How they work:

#### How to control them:

#### Use cases:



### Industrial Servos

#### How they work:

#### How to control them:

#### Use cases:

## Motor drivers

* H Bridghe
* Dual H-Bridge
* Stepper Drivers \(Pololu, Trinamic...\)
* ESCs

## Solenoid's

## Pneumatic/Hydraulic Actuators



