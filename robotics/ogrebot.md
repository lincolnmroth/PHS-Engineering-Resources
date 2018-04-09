# Ogrebot 2017-18

Ogrebot was my robot for the Trinity International Robot Contest 2018. For Trinity, the goal of the robot is to navigate a maze, find, and then extinguish a candle. [Here](https://www.dropbox.com/sh/cdmub3uenwfiwm0/AACBgmRkPap07aON3aHTY9DSa?dl=0&preview=TCFFHRC2018RulesV1.04.pdf) is the link to the rules. The hardware was done exclusively by myself, and the software was done by cvxluo, Lachlan, and Stephane.

### Design:

I started designing this robot in May 2017 for a competition in April 2018. You may say this was excessive, but you will see later that it may not have been. During the end of the school year in 2017 \(march - june\), I probably changed the CAD program I used at least half a dozen times, but this robot got started when I was using [Fusion 360](https://www.autodesk.com/products/fusion-360/students-teachers-educators), which I still highly recommend, it's just not my favorite \(SOLIDWORKS master race\). When designing this, I wanted to spend a large amount of time making sure I had EVERYTHING planned out so we wouldn't run into an issues \(at least hardware related\) down the road, which proved to work very well.

I knew I wanted the robot to be modular, easy to repair, compact, have an accurate, relatively powerful drive system, and have all the sensors necessary to make the software as easy as possible.

To do this, I decided on a design with circular plates connected with standoffs, and as we were supposed to get a laser cutter, all the plates would be laser cut.

#### Drive System:

I was happy with the motors we used in the previous years robot, [Boxbot](/robotics/boxbot.md), so I decided to reuse them. They were the [Pololu 100:1 gearmotors](https://www.pololu.com/product/2826) that had built in quadtrature encoders. This allowed the motors to have very high torque, but also rather quick \(Faster than we ever could need\), but also the quadrature encoders would give us accurate positioning of the wheels down to 0.05510485229 degrees, which again would be more than we could ever need.

In boxbot, I used [stamped aluminum mounts](https://www.pololu.com/product/1084) for the motors, which worked fine, but were kinda flimsy, so I decided to beef it up with CNC'd [aluminum mounts](https://www.pololu.com/product/1995), which would be super rigid.

For the wheels, I initially wanted to some cool omnidirectional shit, but then I decided not to overcomplicate stuff for the~~ code monkeys~~ software developers. So as I wanted to use one of [Pololu's aluminum motor mounting hub](https://www.pololu.com/product/1083) to attach the wheels to the motors, it was a pretty easy decision to go with Pololus[ 90x100 wheels](https://www.pololu.com/product/1438). These wheels are nothing special, but are very solid and worked great for our task at hand.

Finally, as balancing  on two wheels is rather difficult, I needed a caster to support the weight. Boxbot used a pretty shitty caster, which stopped spinning within weeks, so I decided to get a nicer caster. [This caster](https://www.pololu.com/product/2692) was slightly larger, but I thought it would spin nicer \(which it did\), so I went with it. It did end up picking up a lot of dirt making it spin worse, but it still ended up being better than anything I had used before.

Here's a picture of the drive system.

![](/assets/Screen Shot 2018-04-09 at 5.24.28 PM.png)

I also added a cutout for wiring any sensors to the bottom of the robot, as I planned on putting a color sensor on the bottom to detect the change of rooms in the maze.



This is not the best drive system I have designed, but I was definitely satisfied with it, and it was pretty solid.

#### Sensor system:

Deciding on the sensors was one of the most difficult parts of this design, as it was one of the most important, and I did not want to fuck it up. I decided on using ultrasonic distance sensors for positioning. As I wanted 8 of them \(Front, Back, Left, Right, and at 45 degrees\), I decided to go with the [HC-SR04](https://www.sparkfun.com/products/13959) from sparkfun. I chose ultrasonic over alternatives such as infrared as they were more accurate, cheaper, and could be read easily by the Raspberry Pi. The issue, which I did not find out until the competition, was that the sensors at 45 degrees returned inaccurate readings due to the nature of sound bouncing away.

For addition sensory, I added a [BNO055](https://www.adafruit.com/product/2472), which had a 3 axis magnetometer, 3 axis accelerometer, and a 3 axis gyroscope. This was meant to be used for accurate turning and such.

Finally, the competition has white lines on the floor to be the difference between the hallway and the rooms, so I added a [color sensor](https://www.adafruit.com/product/1334) to the bottom of the robot.

Here's a picture of my main sensor layer:

![](/assets/Screen Shot 2018-04-09 at 5.43.22 PM.png)

I also had 2 [perma-proto](https://www.adafruit.com/product/571) boards which were used for the signal distribution.

#### Extinguishing System

The goal of the robot is to extinguish a candle, so the extinguishing system was very important. To detect the candle, I used a [flame sensor](https://www.robotshop.com/en/gravity-flame-sensor.html) that was basically just an IR LED, which we used the year before with Boxbot, and worked well. Actually extinguishing the candle was a challenge, but I had a pretty good system from the year before, so I stuck with that. I used an 8g [co2 puncture device](http://www.lelandltd.com/puncture_devices.htm) from Leland Ltd, attached via a 1/4" to 1/8" NPT pipe nipple to a [versa valve](http://www.trinityrobotcontest.org/versa-valve.html), provided by the contest, which allowed us to easily control the output of the co2.

#### Control System

Finally we needed to control everything, so we decided to go with a Raspberry Pi 3, which should have enough computational power to run everything. As I was doing all the wiring on the perma-proto boards on the 2nd layer, and the pi was on the 3rd layer, I decided to use an IDE cable with a [Pi Cobbler](https://www.adafruit.com/product/914), to transfer all the wiring down neatly.

Here is a picture of the control layer, I did not model the versa valve but the empty space next to the pi was where I put it.

![](/assets/Screen Shot 2018-04-09 at 7.13.02 PM.png)

#### Power system

For the power system, I used a 3s 2200 mAh battery for the motors, and a 2s 2200 mAh battery for everything else, which was attached to a UBEC to step down the voltage from 7.2 v to 5v.

#### Final Design

Quite frankly this is one of the most planned out designs I have worked on, which made everything else much easier. [Heres](http://a360.co/2nEkYam) a link the model. And [heres](https://docs.google.com/spreadsheets/d/1k7Kwv9mwXJr-ePa_V1eoIoQmc9S5nw2tfjbXv6IOHRE/edit?usp=sharing) a full parts list.

![](/assets/Screen Shot 2018-04-09 at 7.18.47 PM.png)

### Construction:

Construction on this robot was very easy as I had already planned everything out. Sadly the laser cutter did not come in time, so I ended up having to 3D Print all the layers. Another thing I realized later is that the ultrasonic sensors output a 5v signal, whereas the pi can only read 3v3, so I added a simple voltage divider to the sensors.

Here's most of the wiring diagram, it does not have the voltage dividers and the encoders are plugged into 5v instead of 3v3, but everything else is accurate.

![](/assets/ogrebot_wiringdiagram.png)

### Software:

This is where everything went to shit.

### The competition:

This competition was supposed to be the one where everything worked. I had started the project a year before. I had completely finished the hardware by early November. Yet, it managed to be one of the worst competitions I have ever been to. This was because all the issues we ran into were software related. This caused me extreme stress as there was nothing I could do about it as I'm not a software guy. We ran into many issues including the following:

* Having weird ultrasonic readings because of weird threading issues
* Having to make an encoder daemon because it required readings all the time
* PIDs getting messed up
* 
### What I/we learned:

* WORK ON SOFTWARE AHEAD OF TIME!!!!!!!!
* Do not use ultrasonic sensors at angles
*  Fully designing the robot in CAD was very useful
* Versa valve works great
* Pololu motors are nice
* Encoders should have a dedicated signal processor
* encoders are useful
* PIDS are great except when they dont work
* The BNO055 was not particularly accurate



-lmr



