# CAD/CAM/CAE

So I'm not going to teach you how to use CAD/CAM/CAE is this section as it is an extraodinarily broad subject and get extremely complicated \(like graduate school level classes\) once you start getting in deep with what you can do.

So just to define these weird abbreviations:

##### CAD - Computer Aided Design

##### CAM - Computer Aided Manufacturing

##### CAE - Computer Aided Engineering

## CAD

Computer Aided Design is the process of designing something using a computer. This can either be 2D or 3D. Starting in 2018, full CAD models will be required in robotics team.

### CAD Packages

Here's a list of some CAD packages. There are many more, but I'll go over the main ones.I will not be including any organic modeling \(Blender, ZBrush\), because it's stupid, and for art people. Not engineers.

* SOLIDWORKS
* CATIA
* OnShape
* Autodesk Fusion360
* Autodesk Inventor
* Autodesk AutoCAD
* SiemensNX
* Sketchup
* OpenSCAD

#### SOLIDWORKS:

SOLIDWORKS is my current CAD package of choice. It is what many companies use \(Apple, GE, Samsung, Intel, etc...\) for designing components. It is not particularly beginner friendly but is one of the most powerful. The main issue with it \(which is why I can't recommend it\) is the price. It is a multi-thousand dollar piece of software, and if you're not willing to find alternative means of acquiring it, you probably shouldn't get it. It also has powerful CAM and CAE as well.

#### CATIA:

CATIA is another product from Dassault Systems \(the company that makes SOLIDWORKS\). It is another CAD package, but more focused on larger assemblies. One common explanation for distinguishing the two is that you design an engine in SOLIDWORKS, but you design a car in CATIA. It also has powerful CAM and CAE as well.Also super expensive.

#### OnShape:

OnShape is probably the cad package I recommend most to beginners. It is created by the founder of SOLIDWORKS, has a very similar layout, which allows an easy conversion down the line, and it is free. The only caveat is it does not have CAM or CAE and it is entirely web based, which is both a good thing and a bad thing.

#### Fusion360:

Fusion360 is the other cad package I recommend to beginners. It is made by autodesk \(a company I don't really like, but fusion is ok\), and also has a very good CAD/CAM/CAE workflow.

#### Inventor:

Inventor is Autodesk's flagship CAD package, but I've got to say I'm not a fan. Maybe because I'm used to SOLIDWORKS, but Inventor's weird and Autodesk is a pretty awful company. Also super expensive.

#### AutoCAD:

AutoCAD is also made by autodesk and is a popular 2D CAD program, but I use eDrawings which is made by Dassault Systems.Also super expensive.

#### SiemensNX:

SiemensNX is the CAD package with the best CAE, and is what SpaceX uses, but again is super expensive.

#### Sketchup:

Don't use it. Ever. It's horrible.

#### OpenSCAD:

OpenSCAD is weird. But I love it. I don't really use it anymore, but it's a way of writing code to make 3d objects.

## Resources:

Because I don't want to teach CAD, I'll put some resources here.

* [Lars Christensen](https://www.youtube.com/channel/UCo29kn3d9ziFUZGZ50VKvWA) is the best resource for fusion360.
* OnShape has good lessons/tutorials built into the site
* I'd mainly recommend just downloading a program and playing around with it until you figure it out, that's what I've done and I've got pretty good at CAD

## CAM

CAM is the process of using a computer to generate toolpaths for a CNC machine to make. I haven't done the CNC article yet, so I'm just going to put CAM in the CNC article.

## CAE

CAE is my favorite. It allows you to analyze parts designed in CAD. It is an engineers greatest tool and knowledge of CAE is invaluable. I'm not going to go into how to do each individual type, but talk to me if you want to talk about cae.

Here are the main CAE Methods:

* FEA
* CFD
* Durabilty and optimization
* MBD

## Finite Element Analysis:

Finite element analysis is used to study objects properties such as stress using structural analysis or other properties using techniques like heat transfer. FEA allows engineers to not have to incredibly complicated math and physics. For example if you're designing a coat hanger and it needs to support 100 pounds \(lot of coats\), you could run FEA to see how strong your design is with different materials.

![](/assets/FEA.png)

## Computational Fluid Dynamics:

My theory on CFD is that nobody actually knows how to do it. But CFD is what allows you to study how fluids move in relation to your design. This could be gasoline in pipes or it could be air. This is what is used to calculate lift of airplanes or the aerodynamics of a cow.

![](/assets/cowcfd.png)

## Multi-body dynamics:

MBD allows you to do motion studies and see how different motions affect others in a system. This allows you to see how good your suspension is or to do funky kinematics stuff.

![](/assets/mbd.png)

-lmr

