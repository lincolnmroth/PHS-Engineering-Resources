# 3D Printing

Yeah, so I'm not sure I can do this. I have no idea even where to start. I have spent wayyy too much of my life learning about 3d printing, it would be impossible to write it all down.

Well I'm going to try anyway.

I'm going to start with how to use the printers, then go to how printers work, then go to printer maintenance, then go to printer design.

# Printer usage:

Here are the steps for using the printers. Make sure you follow all the steps or things won't work.

1. Get an .STL file. 
2. Ask Lincoln if you are allowed to print. If yes, continue to next steps. If no, do not push it, he holds grudges and won't let you print anything for a long time \(ask stonny if you don't believe me\).
3. Open Slic3r and load the object
4. Set print settings
5. Slice the object
6. Load .gcode file onto SD Card
7. Print from SD Card

## Get .STL File

To get an .STL file, you either download it from the internet or make it yourself. Making it yourself is better and Lincoln \(next step\) is much more likely to let you print. Most CAD programs have an export as .stl option or saving as .stl is part of the save as menu. Also you can download .stls from Thingiverse or myminifactory or some site like that.

## Ask Lincoln if you can print

Do not forget this step. Do not try and circumvent Lincoln \(also do not pass go, or collect $200\). As of the 2018-19 school year, he has authority over all of the the 3D Printers. If you do not want to ask him, you can ask Mrs. Elia, and she will ask him for you. He will likely just print the model for you, but the point of this article is to teach you about 3D Printers, so I'll go over it all.

## Open Slic3r

Slic3r PE is the slicing program we usually use \(unless you're using one of the makerbots which are very yuck\). It can be downloaded from prusas website, [https://www.prusa3d.com/drivers/](https://www.prusa3d.com/drivers/). Unzip the folder and put it into your applications folder. Then open up Slic3r. When first opening it will ask which printer configs you want. Currently \(as of July 2018\), we have a Prusa i3 MK2, MK2 MMU, and a MK3 \(and like 3 broken makerbots which may or may not ever get fixed\), all with .4mm nozzles. I do not see us getting a new printer any time soon, but getting new nozzles is completely within the realm of possibility.

To load objects, click add in the top left corner and select the object from your file system.

![](/assets/Screen Shot 2018-07-22 at 10.58.50 PM.png)Once the object is load, you can use all the options next to it to to manipulate the object \(increase copies of it, rotate it, translate it\)

![](/assets/Screen Shot 2018-07-22 at 11.00.49 PM.png)

## Set print settings

Getting print setting right is an art. Luckily most setting have already been taken care of by Prusa. I will go over all the ones you will ever need to change and some of the other important ones.

* Material
* Infill
* Layer Height
* Support structures
* Adhesion extras \(Rafts, brims, skirts\)
* Temperatures
* Filament size
* Cooling
* Perimeters
* Seam Position
* Custom GCODE

### Material:

3D printers can print with a variety of different materials.

Here are the main ones:

* PLA
* ABS
* PETG
* Flex \(Multiple varities\)
* Nylon
* Polycarbonate
* ASA
* HIPS
* PVA
* Filled/composites

I'll go over the properties of the various materials and then explain how to set the printer to the desired material.

#### PLA:

PLA \(Polylactic acid\) is the most common \(these days, back in the early reprap era, ABS was more popular do to the fact that nobody had thought of using pla in 3d printers\) 3d printing material. It is usually the cheapest and what we use most in 242. Additionally t is very rigid and kinda brittle, but is very easy to print which is the reason for it's popularity. Plus it's biodegradable.

Printing notes:

Hotend temp should be between 150 and 200

Bed temp should be between 0 and 60

Prints great on PEI \(bed we have\). If there are any problems with adhesion, a layer of gluestick makes it stick super well.

#### ABS:

ABS \(Acrylonitrile butadiene styrene\) is probably \(I'm just guessing\) the most commonly used plastic in the world. It is almost always the material used in injection molded products. For example, ABS is the material used in LEGO. ABS is more flexible than PLA which makes it more impact resistant. This is the material we use \(used\) with our makerbots.

Printing notes:

Hotend temp should be between 200 and 230

Bed temp should be between 60 and 130

Prints terrible on everything that is not a heated chamber. Will warp. Always. Glue stick or buildtak helps but ABS is always a pain to print with.

#### PETG

PETG is relatively new to the 3D Printing landscape. It prints similarly to PLA and has properties similar to ABS. PET is what those plastic water bottles are made of

Printing notes.

Hotend temps 235 and 250°C.

ALWAYS use a fan with PETG as it tends to cool the filament in the hot end and help with retractions.

Bed temperature should be between 80-100°C .

USE GLUE ON PEI, if not it will stick so bad it will rip a chunk out of the PEI.

#### Flex

There are also flexible 3d printing materials. There are many different types with a range of flexibilities. All the flexibles are hard to print but they all have very different settings

#### Nylon

Nylon is my favorite material, but sadly we don't have any filament :\(. It's a very strong material, but is extremely annoying to print with. It is very hydrophilic so it needs to be kept in an airtight container with desiccant in it.

#### PC

Polycarbonate is probably the hardest material to print. It needs to be printed in an enclosure with a special hotend becuase it needs to be printed at such high temperatures.

#### ASA

Nobody uses asa

#### HIPS

HIPS is a material that prints at a similar temperature to ABS which is why it is sometimes used a dissolvable support material for ABS because it dissolves in Limonene \(not lemonade\)

#### PVA

PVA is a water soluble material. It is used a dissolvable support material for PLA

#### Filled/composites

Manufactures like adding random particles into materials for stupid properties \(glow in the dark, appearance\), but sometimes they put carbon fiber into materials to give it added strength. When printing with composite, you NEED a hardened steel nozzle or else your brass nozzle will get destroyed.

### Infill

3D prints are not 100% solid. Instead there is what is called an infill pattern. This is an internal structure that keeps as much structural integrity as possible while reducing material cost and print time.

There are different shapes of structures. Here are a few:

![](/assets/infillpatterns.png)

However I don't use any of these. I am a big fan of cubic infill which is 3 dimensional and is a bunch of cubes \(duh\).

![](/assets/cubicInfill)

Here is where you can change the infill structure:

![](/assets/Screen Shot 2018-07-24 at 11.09.57 PM.png)

Additionally if you want more or less strength in a part \(in exchange for more material and longer print times\) you can change the infill percentage either from the print settings tab as before, or directly from the plater tab:

![](/assets/Screen Shot 2018-07-24 at 11.09.51 PM.png)

You should almost never go below 20% or it will get spongy, and going over 50% is usually a waste of material. But there are always exceptions and I've had to do everything from 0% to 100%.

### Layer height

### Support

### Adhesion extras

### Temperatures

### Filament size

### Cooling

### Perimeters

### Seam Position

### Custom GCODE

## Slice the object

## Load .gcode file onto SD card

## Print from SD Card

-lmr

