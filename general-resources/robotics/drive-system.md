### Drive System:

This is how a robot moves, and can be one of the most difficult parts of building a robot. I'll try and go through the types of drive systems, compare them, and point out what to look out for when using them.

I'm going to try and keep it concise as I could talk for years about drive systems as they are my are of expertise\(speciality?  i feel kinda weird saying those as a hs student but whatver\).

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

-lmr

