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

Also there are solenoids which aren't motors, but whatever.

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

###### Solenoids:

solenoids are just electromagnets, which can be used for many applications. They are frequently used to change state of a system. For example, they can be used to make an electrical connection, or as a valve for liquid or gas.

![](/assets/solenoid.png)

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
* Screws
* Linkages
* Crank
* Cams
* DIfferentials

##### Gears:

One thing to keep into consideration when choosing gears is the material. If you have two gears, it is a good idea to make the cheaper/easier to replace gear out of a softer material, so that if there is any grinding or slipping, it is not impossible to replace your damaged gears.

Also never design your own gears, all reasonable CAD programs have gear functionality built in.

[Heres](http://khkgears.net/new/gear_knowledge/introduction_to_gears/types_of_gears.html) a list of gear types, but I'll go over the main ones.

##### Spur gears:

Spur gears are your most standard type of gear, and they are used for changing speed and torque.

![](/assets/spur.png)

If you want to increase the speed output, attach a large gear to your motor, and then engage that with a smaller gear. Do that the opposite way to increase torque.

##### Bevel gears:

![](/assets/bevel.png)

Bevel gears change the direction of your output, and if you use different sizes, they can have the same effect as spur gears.

##### Screw gears:

![](/assets/screwgear.png)

Screw gears also change direction like bevel, but one very important feature of screw gears is that they can only be driven in one way. This makes it very good for certain applications. Also screw gears slow down the output and increase torque.

##### Rack and Pinion gears:

Rack and pinions convert rotary motion into linear or vice-versa.![](/assets/rackandpinion.png)

##### Planetary gears:

Planetary gears are a great way have a large gear reduction in a very compact area.

![](/assets/planetary.png)

They are used in drills, for example.

##### Helical gears:

Helical gears are just a subset of any other gear type.

![](/assets/helicalgears.png)

If you have the choice, always go with helical gears, as they can handle much more torque than standard gears.

##### Belts:

Belts are pretty much just flexible rack and pinion gears, that sometimes don't have teeth.They can be used in a spur gear like fasion, or to translate rotary motion into linear motion.

Belts can be toothed or un-toothed, toothed do not allow for slipping, while un-toothed allow for slipping. So if you wanted to use belts in a precise application like a 3d printer, you would want the toothed variety. The un-toothed variety would work better in something like a combat robot where things get hit around, and slipping is okay.

Here is a belt used in a spur like configuration:

![](/assets/beltgear.png)

Here is a linear belt configuration:

![](/assets/beltactuator.png)

##### The name for circles in the diagram above are timing pulleys, they are what the belts go around.

When dealing with belts, one very important thing to take note of is tension. If the belt is too loose, it will slip, but a too tight belt will cause issues as well.

Belts are frequently used to drive lightweight objects \(like a 3d printer or a camera slider\), or when slipping is necessary \(combat robotics\)

The most common type of belt used in 3D Printers are GT2 belts, which have a 2mm pitch \(thickness\). But even within GT2, there are different types of belts. Most belts are rubber, but they are usually reinforced with either fiberglass or steel strands. Fiberglass reinforced allows for a more flexible belt, but steel core belts don't stretch as much.

##### Chains:

Chains are similar to toothed belts, except that they are metal and can handle much more torque.

If you are curious about chain nomenclature, [heres](http://www.martinsprocket.com/docs/nomenclature/nomenclature/sprocket.pdf) a nice cheatsheet.

![](/assets/twochains.png)

##### Screws:

Screws are another way of transmiting rotational motion into linear motion. Here are the 3 main types of screw drives.

[Heres an article about screw drives.](http://reprap.org/wiki/Threaded_rod)

###### Threaded Rod and nut:

Don't. Use. These. Ever. I'll explain them anyway.

Threaded rods are the most basic type of screw drive, they have one helix around the outside of a rod, and the accompanying nut has one helical cutaway.

![](/assets/threadedrod.png)

###### Trapezoidal Rod and nut:

Trapezoidal rods are much much better. First they have a leading edge to make engaging with a nut easier, and also they have 4 helixes instead of one.  
One downside they have \(threaded rods have it, just much worse\) is backlash. I'm not sure how to explain backlash, so I'll let [this guy](http://www.liutaiomottola.com/Tools/Backlash.htm#mozTocId246078) do it.

###### Ball Screw:

Ball screws are amazing, and the best screws. They are kinda expensive though. It's hard to explain how they work without a picture, so here's a picture:![](/assets/ballscrew.png)

They have recurculating balls which allow for no backlash. One thing to make sure you never do is take the nut off the screw or you'll have a few hundred balls on the floor.

##### Linkages:

Linkage is a very broad term, so here's how [wikipedia](https://en.wikipedia.org/wiki/Linkage_%28mechanical%29) describes it: A mechanical linkage is an assembly of bodies connected to manage forces and movement. Basically, linkages are a way of linking objects together.

Here is a really cool use of linkages. It's called a strandbeest, It was created by a guy named Theo Janson \(I think\) out of pvc, duct tape and glue.

![](/assets/strandbeest.png)

One type of linkage to be aware of are ball linkages, which allow linear motion to be transmited without a rigid angle.

![](/assets/balllinkage.png)  
These are used in 3d printers that use the delta kinematics system \(I'll go over this in the 3d printing article\)

##### Crank:

Cranks are another way of translating rotational motion into linear. These are very frequetly used in everything from fishing rods to car engines.

![](/assets/crank.png)

Cranks have the shaft, called the crankshaft, which is attached at an offset to a linear rod, which is then moved back and forth.

##### Cams:

Cams are similar to cranks, except they are not attacked to the linear portion, they kinda just push the linear portion when rotating:

![](/assets/cam.png)

##### Differentials:

Differentials allow for cars to turn because it allows the inner wheels to spin slower than the outer.

Differentials are super cool. I'm not going to explain gear differentials since [this video](https://www.youtube.com/watch?v=yYAw79386WI) which looks like it was made 50 years ago is amazing.

There are also ball differentials, which are kinda weird. [Here's](https://en.wikipedia.org/wiki/Ball_differential) the wikipedia article on them. I would not recommend, since they are very difficult, and gear differentials are much better.

##### Structural System:

The structural system is very important, it's what keeps everything together, and all other systems are built upon it. There are two main parts of the structural system, the static portion and the kinetic portion. I'll start with the static part, then go through the kinetic.

###### T-Slot Aluminum Extrusions

T-slot extrusions are a great way to have a very modular, rigid structure. T slot extrusions come in various sizes and lengths. The sides are ususallly made in multiples of 10mm, \(2020, 3030, 4040 ,2040\) You can get any length you want really, and if not you can easily cut it down to size \(I'd recommmend a chop saw with a metal cutting  blad if you have one, but if not a hand saw with a metal cutting blade also works fine.\)  
Tslot in itself is rather useless, but when used with tnuts, they become amazing.

![](/assets/4040.png)

T-nuts work by sliding into the slots which then allow a screw to attach to the extrusion at any point:

![](/assets/tnuts.png)

There is a whole host of other accessories \(can't think of a better word\) for tslot extrusions like this corner brace:

![](/assets/tslotanglebrace.png)This allows you to build cool stuff like this:

![](/assets/tslot structure.png)

I actually recommend going with vslot, which I'll go into later, which is a modified tslot profile.

###### Screws/nuts+bolts

Screws are almost always the best way to hold everything together.

[Here](http://www.metrication.com/engineering/fastener.html) is a great site with information about screw sizes.  
Also when buying screws, I highly recommend McMaster Carr

Whenever you get to choose your screw/bolt size, please, please use metric, imperial units are dumb, you should never use them. Metric screws/bolts are pretty simple. the number next to the M \(M3, M4, M5...\) is the diameter in mm, and then the number after is the length. For example, a M3 x 30 is 3 mm in diameter and 30mm long. There are also different types of screw/bolt heads.

![](/assets/boltheadtypes.png)

I usually use cap head screws because they can easily be countersunk with just a standard drill bit, but if you cannot have that extra space, a countersunk head is recommended. 

In robotics, you almost always use bolts instead of screws, which is why I often refer to nuts as screws, but here is some info about screw types.

![](/assets/screwtypes.png)

One frequent issue with nuts is that vibrations and impacts can make them loose. Loctite is what is used to prevent this. There are two different types, blue and red. Blue loctite is temporary while red is permanent. The other option are locknuts, which are standard nuts, but they have a nylon insert which adds more grip. 

![](/assets/locknut.png)

###### standoffs

Standoffs are another way of adding structure to your robots.  
![](/assets/standoffs.png)They are used in robots like these \(what a great looking robot!\):

![](/assets/Screen Shot 2017-09-25 at 3.19.10 PM.png)

Standoff ends come in two different varieties, Male and Female. The male end screws into the female end \(I assume you can figure out the reason for the nomenclature\).

###### Aluminum Channel

[Actobotics](https://www.servocity.com/structural-components/channel/standard-channel) aluminum channel is an alternative to t-slot extrusions, and I've heard good things about it, but have never actually used it. 

![](/assets/actoboticschannel.png)

###### FEA

FEA, finite element analysis, is a way to make sure your robots are strong enough. I'll talk about it a lot more in the CAD section.

![](/assets/fea.png)

###### Bearings

There are two main types of bearings, roller and linear

I'd also recommend McMaster for getting bearings

[Heres](https://www.youtube.com/watch?v=5Dkruh8NO9E) a video about bearings

The job of bearings is to reduce friction. They do this by having little bearing balls roll around.

![](/assets/rollerbearingcutaway.png)

Bearings are often used for supporting rods/axles so that there is not torque on the axle. 

For example this load-bearing servo has a bearing pillow block, which allows it to support against much larger forces:

![](/assets/pillowblock.png)

Linear bearings are used on rods to reduce sliding friction:

![](/assets/linearbearing.png)

###### Bushings

Bushings are used in the same way as bearings. The difference is that bushings are just a low friction material, and do not have any balls in them. Nylon and teflon are frequently used as bushings.

Igus makes nice bushings.

###### V-Slot

V-slot extrusion is an evolution upon T-slot extrusion made by [openbuilds](http://openbuildspartstore.com/).

![](/assets/vslot.png)

Vslot has a v shaped profile on the edges which allows self-centering roller bearing wheels to ride smoothly on them.

This allows for platforms that are meant to move to be attached to vslot extrusion:

![](/assets/vslot2.png)

To ensure that the wheels are making good contact, they have to be at the right tension to the rail. To make this easily adjustable, use eccentric nuts, which allow slight rotations of the screw to make incremental adjustments in the height of the wheels.

![](/assets/eccentricnuts.png)

###### Linear Rail

Linear rail is amazing, but kinda expensive. The good stuff is made by Hiwin. 

Linear rail is the best way to have linear motion, it is super rigid and has minimal slop.

![](/assets/linearrails.png)

They are also very easy to use and attach stuff to. Just make sure you don't remove the bearing blocks from the rail or else you'll have a lot of balls on the floor.

![](/assets/linearrailbearing.png)

###### Rods and Linear Bearings

Rods and linear bearings are the most common to support linear motion, and are used extensively in consumer 3d printers and similar machines.

Misumi makes the nicest rods and bearings.

![](/assets/linearrodsystem.png)

![](/assets/linearrods.png)

Usually you use 8mm rods and bearings, unless you will be dealing with a lot of forces, then you sometimes use 12mm.

###### building with threaded rods is what people did in the stone age

Don't do this. It's what people did back in the early reprap days. 

Threaded rods were used as structural support in the early 3d printing days. They are a huge pain, so don't ever use them.

![](/assets/reprapdarwin.png)

##### Sensing System:

Without knowledge of their surrounding, robots are usually pretty useless \(not always\). I'm not going to go too in depth here, since I'll go very into depth in the electronics article.

###### Distance:

Knowing distance to objects is very important. The three main ways of doing this are using infrared sensors, ultrasonic sensors, and LIDAR Sensors.

###### encoders

Encoders measure how much rotation has happened on a shaft. [PJRC](https://www.pjrc.com/teensy/td_libs_Encoder.html) has a good site on them.

###### cameras

Cameras can also be used for a lot of purposes, it just requires very complicated code to understand the data.

###### IMU

IMUs or Inertial Measurement Units measure  body's specific force, angular rate, and sometimes the magnetic field surrounding the body

###### GPS

GPS measures position relative to the earth

###### Color Sensor

Color sensors measure colors

###### Tactile, resistive, capacitive physical

Knowing if the robot is being touched in any way is useful for knowing if it hit something or not. 



Apologies for this section being pretty dinky, but I'll go into more detail in the electronics article.

##### Control System:

Choosing a controller for your robot is a pretty simple task. If you do not need a full operating system, you go with arduino. If you need an OS, but you do not need a particularly power processor, you use a raspberry pi. If you need a lot of power, you go with something fancy like a full blown computer or a NVIDIA Jetson TK1. I'll go into more detail about the pros and cons in the electronics doc. 

[Arduino](https://www.arduino.cc/)

[Raspberry Pi](https://www.raspberrypi.org/)

[tegra/jetson tk1](http://www.nvidia.com/object/jetson-tk1-embedded-dev-kit.html)

computer

##### Power System:

Your robot needs power somehow, so you need a power system.

###### Batteries, lipo, nimh, sla, lifepo4

Batteries are the most common ways to power robots. The best choice of battery is usually LiPo. It allows for very high amp draw and lasts a long time.

Lipo batteries come with a certain number of cells, each of which is 3.7v but is usually charged to 4.2. For example a 3s \(s is for cell\) lipo is rated at 11.1v, but can be charged to 12.6v. Lipos can be dangerous. If they are shorted, they will blow up. [Heres](https://rogershobbycenter.com/lipoguide/) an article about lipos.

![](/assets/lipo.png)

SLA, sealed lead acid, batteries have very high capacity, and an extremely high momentary amp draw, but a very low continuous amp draw, which is why they are used to start cars.

![](/assets/slabattery.png)

NiMH batteries are getting kind of out of date these days, so only use them if a competiton \(\*cough\* Scioly \*cough\*\) disallows both lithium and lead batteries.

![](/assets/nimh.png)

Lithium Iron Phosphate, LiFePo4 batteries are pretty hipster these days, not many people have actually used them, they're just talked about a lot, so they have the potential to be pretty good.

![](/assets/lifepo4.png)

###### bec, regulators

Sometimes you need a different voltage that your battery puts out, which means you need a regulator. BEC, or battery eliminator circuit's are a good way of stepping down any voltage form 7-24 V to 5V. If you need something else, you will need a buck converter.

![](/assets/bec.png)

###### wall power

I do not recommend using wall power, it is dangerous, and difficult to use. If you do, use a PSU, and probably one from a reputable brand like Meanwell.

###### Connectors

Connectors to your batteries are useful so you can easily remove them when you want, but also they don't come unplugged accidentally.

XT-60 is my reccomended battery connector for anything decently sized. JST is acceptable for smaller sizes, but XT-60 is always a good option.

![](/assets/xt60.png)

##### Communication System

All the different parts of your robot need a way to talk to each other, and that is the job of the communications system.

###### cable, cat5, ide

Using wires is fine, except sometimes they can create a huge mess. That is why using cables such as cat5 \(ethernet\) wire or IDE cables \(Old hard drive cables\) can be useful.

![](/assets/cat5.png)

###### Breakout Boards

Making breakout boards is a very good idea, they allow a large organized bundle of wire to be distributed cleanly to all the needed places.

![](/assets/breakout.png)

###### sliprings

Sliprings allow wiring to go through a roational joint.

![](/assets/slipring.png)
