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
