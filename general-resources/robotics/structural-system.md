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

Standoff ends come in two different varieties, Male and Female. The male end screws into the female end.

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

-lmr

