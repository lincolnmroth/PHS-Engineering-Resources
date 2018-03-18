# Robotics

So robotics is a pretty broad topic and there's a lot of information, so I'll try to focus on more general topics.

Also, I'm not going to try and explain physics, since my physics knowledge is rather limited. If you want to learn physics, go watch walter lewin on youtube, his lectures are straight up magic.

### Anatomy of a robot:

So robots have a few main systems that together make the entire robot.

I will go through all of the systems in more depth later on.

#### Drive System:

The drive system is how the robot moves itself. Some robots are stationary, but many robots can move. Here are the main types of ways robots can move:

* Wheels
* Treads
* Walking
* Flying \(Propellers\)

#### Motion System:

The motion system is how the robot moves to interact with the world. For example, an arm or grabber. There are so many different types of motion system, I won't try and name all of them, but just think of any way robots can move and that is part of the motion system.

#### Structural System:

The structural system is how everything attaches and is supported in the bot.

#### Sensing System:

The sensing system is how a robot get information about the environment it's in. There are infinitely many ways of sensing the environment, but here are a few:

* Knowing where objects are around the robot \(walls, humans, anything\)
* Detecting obstruction
* Knowing direction
* Knowing GPS location

#### Control System:

The control system is the brain of a robot and the software to control it, which interacts with all of the other parts of the robot. Here are some examples of common controllers used in robotic, from least powerful to most powerful:

* Arduino
* Teensy
* Beaglebone
* Raspberry Pi
* NVIDIA Tegra
* Full Computer

#### Power System:

The power system is how every part of the robot gets power. Usually robots are powered by batteries, but some have alternative power sources.

#### Communication System \(the nervous system\):

The communication system is how everything communicates within a robot. This may seem as simple as just plugging wires together, but choosing what type of wire and how to route it is no easy task.

### Drive System:

This is how a robot moves, and can be one of the most difficult parts of building a robot. I'll try and go through the types of drive systems, compare them, and point out what to look out for when using them.

[Here's a powerpoint](https://www.simbotics.org/files/pdf/mobility.pdf) that talks about drive systems.

[Heres](http://first.wpi.edu/Images/CMS/First/2007CON_Drive_Systems_Copioli.pdf) another one

[Heres](http://cyborgeagles.weebly.com/uploads/2/1/8/1/21816346/robot__drive_systems.pdf) a third one

[Heres](http://www.roboticsbible.com/robot-drive-systems.html) an article

[Heres](http://www.robotbasics.com/robot-drive-system) another artivle

#### Wheels:

Wheels are the most common way of moving robots. When choosing wheels the main choices to make are size and material. The larger the wheel, the faster it will go, and the smaller the wheel, the more torque. Material will change depending on what material you plan on driving on, but usually a standard rubber wheel is fine. Another thing to keep in mind is how the wheel will attach to your motor. You want a very rigid way of attaching your wheel to the motor, or else you will lose a lot of accuracy in movement.

Here are some of my favorite wheels:

* [Banebots](http://banebots.com/) makes the best robot wheels by far. They aren't cheap, but they are very high quality, and have many great options for mounting. They also have really nice gearboxes that go great with their motors. 
* [Pololu](https://www.pololu.com/) also makes nice wheels, that work well with their motors and motor hubs. They are pretty good wheels, and are reasonably priced.They also have nice hubs to go with their wheels.
* [Servocity](https://www.servocity.com/) also makes good wheels. They have a pretty wide variety.

Another option for wheels is to use omnidirectional wheels, which you can get from servocity, which allow the robot to not only move forward and backward but left and right as well.![](/assets/import.png)

#### Treads:

Treads give you high torque and good traction on all surfaces. They are also not particularly fast. I would not recommend treads for any non-professional project because it is very difficult to get parts for treads, and you have to make almost all of them yourself.

#### Walkers:

Walkers are one of the slowest way of moving a robot, but they are also more dexterous and can handle very rough terrain, and can do stuff like climb stairs. Also, they require the most complex software to control.

![](/assets/import2.png)

Walkers don't have to be bipedal, they could have any number of legs. I would not recommend building a bipedal robot, unless you know what you are doing as balancing them can be difficult. I would recommend building a quadrapod or a hexapod.

For more information on the inverse kinematics of a hexapod, look [here](http://toglefritz.com/hexapod-inverse-kinematics-equations/).

[Lynxmotion](http://www.lynxmotion.com/) has a lot of information and kits relating walking robots \(I DO NOT CONDONE THE USE OF KITS. KITS ARE TERRIBLE, DESIGN EVERYTHING YOURSELF!!!!!\).

#### Flight:

I will have an entire article on flight, so stay tuned for that.

#### Choosing motors for your drive system.

Choosing motors for your robot can be rather difficult as there are so many different options.

##### Hobby Servo Motors

The easiest option to use is hobby servo motors:

[Heres](https://www.ez-robot.com/Tutorials/Lesson/48) a good article on them

These are very easy to control, you can control speed and direction using PWM \(Pulse Width Modulation, I'll go over that in the electronics article\), They are pretty slow and have pretty low torque, but they are pretty cheap. One thing to keep in mind is to make sure you get the continuous rotation variety or else it will not work.![](/assets/import3.png)

##### DC Motors:

DC Motors come in all shapes and sizes. They are just controlled by voltage, so you need a driver to control them. The cheapest variety of drivers are hbridges but they cannot handle much amperage. DC Motors can be very fast, but have very little torque, so when using dc motors, you almost always need to have a gearbox on the end.

You can have smaller ones like this one:

![](/assets/import4.png)

Or bigger ones like this:

![](/assets/import5.png)

There are many different varieties but they are all controlled the same way.

[Heres a guide on choosing motors](http://www.servomagazine.com/index.php/magazine/article/tips_for_selecting_dc_motors_for_your_mobile_robot)

##### BLDC Motors:

The last option I'll touch on are BLDC, or Brushless DC Motors. These are the best motors to use, but they are also the most expensive. Also they need expensive drivers, ESC's \(Electronic Speed Controllers\), to control them. They are pretty torquey but are insanely fast \(Hundreds of thousands of rpm\), so when used for drive systems, they are frequently faired with a gearbox.

![](/assets/import6.png)These are used in applications such as electric skateboards, drones, and rc planes, as well as many industrial applications.

[Heres how they work](https://www.youtube.com/watch?v=bCEiOnuODac)

[Heres an article on them](https://www.roboticstomorrow.com/article/2016/10/brushless-motors-whats-the-big-difference/9025/)

### Motion Systems:

Motion systems are, in my opinion, the most important part of a robot. They are what will make your robot special and be able to interact with the real world.

#### Actuators:

Motions systems clearly have to move, or else they wouldn't be motion systems, so they need actuators of some sort. Actuators are just anything that can be controlled to move.

The four main type of actuators are electric, pneumatic, hydraulic, and combustion.

##### Electric:

I briefly went over some different types of electric motors above, but there are many more. I'll try and cover some of the popular ones that I did not mention above.

* Stepper motors
* Non-continous rotation servos
* Linear motors

###### Stepper Motors:

![](/assets/steppers.png)

* Stepper motors are very slow, have high torque and have accurate positioning.[ Heres](https://www.youtube.com/watch?v=bkqoKWP4Oy4) how they work.
* They are frequently used in CNC \(Computer Numerical Control, I'll go more into that in another article\) Machines like 3D Printers, laser cutters, or CNC Mills. 
* Frequently come in .9 or 1.8 degree varieties.
* Frequently use the NEMA standard, which tells you the dimensions of the front plate. Many 3d printers use NEMA 17, while bigger machines like CNC Mills will use much beefier motors.

###### Non-continuous rotation servos:

![](/assets/servo1.png)

![](/assets/servohowworks.png)

* Non-continuos servos can only rotate 180 degrees, but can be told what angle to go to
* They could be used in very cheap robot arms, or used to control flaps on an airplane.

###### Linear Motors:

![](/assets/linearmotor.png)

Linear motors are kinda weird. They work as if you cut a motor and unraveled it to make it straight. These are very expensive, and I will reccomend some other easier ways of getting linear motion later on.

##### Pneumatic:

Pneumatic actuators do not use electric power, they use a compressed gas, \(typically co2 or n2\). Pneumatici actuators can either be linear or rotary. They are much more expensive to use, and they require a compressor to power them, but they are extremely quick, and also have a lot of power. These are used a lot in high performance robots, like the ones from Boston Dynamics.

#### ![](/assets/pneumatic.png)

##### Hydraulic:

Hydraulic actuators are similar to pneumatics except they use a liquid instead of a gas. These are how things like bulldozers move their armatures.

![](/assets/hydraulics.png)

##### Combustion:

Combustion engines are what are used in cars/lawnmotors and that kinda stuff. Don't use them in robotics. Ever. It's not 1980, use one of the other types I've mentioned.

#### Transmission:

This is how the power from your actuators get tranferred, or transmitted, to other parts of your robots.

Here are some of the most common types of transmission:

* Gears
* Belts
* Chains
* Linkages
* Crank
* Cams

##### Gears:

[Heres](http://khkgears.net/new/gear_knowledge/introduction_to_gears/types_of_gears.html) a list of gear types, but I'll go over the main ones.





