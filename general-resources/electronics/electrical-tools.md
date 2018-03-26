# Electrical Tools and Skills

## Hardware tools/skills:

### Soldering Iron

Soldering is the art of melting metal to join two other metals together. I'm only going to go over electrical soldering in this section. I will go over other types \(like for plumbing and whatever\) in the Construction Skills article.

First thing you need to solder is a soldering iron. Soldering irons are pen-shaped objects that get very hot \(500-800ish Farenheit\).

At PHS, we have a Hakko FX-888D and a Weller WES51, both of which are fairly high quality irons, so treat them both with care. If you want to get your own, the TS100 is a very popular low cost soldering iron.

![](/assets/hakko.png)

![](/assets/wellerwes51.png)

Next you need solder. There are two main types of solder, lead solder and lead-free solder. Lead solder is easier to work with, as it melts at a lower temperature. But lead is carcinogenic, so you need to make sure you have proper exhaust and you wash your hands immediately after soldering. Lead free solder is what we have at school, which can be slightly more difficult to work with, but is safer.

When setting the soldering iron temperature, I usually like to choose a value around 650-700, but if you are soldering very thick wires, you may want to bump that up.

The first thing you want to do is clean the tip and then tin it. To clean the tip, you move the tip around in the brass wire mesh. Then you apply a small amount of solder to the tip to tin it.

Explaining how to actually solder is rather difficult, so I'll have my [Colin](https://www.youtube.com/watch?v=QKbJxytERvg) explain it for you.

When soldering wire to wire, I recommend the Linesman splice, as it makes a very strong joint.

![](/assets/linesman.png)

### Soldering Accessories

Sometimes certain solder joints can be difficult for a variety of reasons, but there is usually a tool to fix that for you.

Helping hands are super useful for soldering, they help hold what you are soldering in place so you can focus on soldering. I learned how to solder without helping hands, and the first time I used them was magical.

![](/assets/helpinghands.png)

If you are soldering to a PCB, you'll want to use a PCB vice to hold it in place.

![](/assets/pcbvice.png)

Also tweezers/pliers can be used to hold things in place.

Sometimes when soldering you make a mistake and need to desolder it.

There are two tools used for that a solder pump and solder wick.

[Colin](https://www.youtube.com/watch?v=N_dvf45hN6Y) also has a good video on that.

### Multimeter

Multimeters are a fantastic tool for debugging electronics.

This multimeter is pretty dinky, but that's besides the point.

![](/assets/multimeter.png)

Multimeters can have anywhere from just a couple of functions to literally hundreds. I'll go over the main ones and how to use them.

#### Voltage

To measure the voltage, you need to choose DCV of ACV. I have never used ACV because I very rarely do anything with alternating current, and you really shouldn't either. With most multimeters, you need to select a range of voltages for it to be in. On the multimeter above there are 5 options from 200 millivolts to 1000 volts. So if you are measuring a 9v battery, you select the 20v range.  
When measuring voltage, you measure in parallel, not in series.

#### Amperage

Measuring amperage is the same thing but you select DCA measure in series, not in parallel.

#### Resistance

To measure the resistance you measure in the section with the Omega. If you want to measure continuity \(if two things are connected\) select the option with the buzzer symbol and the diode symbol. It will beep if the probes are connected.

![](/assets/beepermultimeter.png)

### Crimper

Crimpers are a way of attaching connectors to wires. As there are many types of connectors, there are multiple differnt types of crimpers. I'll go over the three most common types, rj45, terminal connectors, and pin connectors.

#### RJ45

If you want to make your own ethernet cables, you need to crimp rj45 connectors onto cat5 cable. This is the tool you want to use.[Heres](https://www.youtube.com/watch?v=ORZYBASS9zw) a video on how to crimp the connectors on.

![](/assets/rj45crimper.png)

#### Terminal Connectors

![](/assets/terminalconnectors.png)

Terminal connectors are the easiest to crimp. Many pairs of wire strippers have terminal crimpers built in.

![](/assets/terminalcrimper.png)Crimping is very simple. First you strip the end of the wire, slightly less than the insulated part of the connector. Then you insert the wire, and crimp the connector onto it with the crimping device.

#### Pin Connectors

Pin connectors are rather finicky to deal with, but they are probably the connector I crimp the most, so it's a very useful skill to have. [Heres](http://www.instructables.com/id/Dupont-Crimp-Tool-Tutorial/) an instructables on how to do it.

![](/assets/dupontcrimper.png)

### Cutters/strippers

Flush cutters and wire strippers are one of the most commonly used electronic tools. Wire strippers allow you to strip off the insulation of wire to expose the conductor\(s\).

![](/assets/wirestrippers.png)Flush cuts allow you to easily cut wires and leads of electric components flush against a surface. Flush cuts are meant for cutting soft metals like copper NOT hard wires. If you are cutting something like piano wire DO NOT USE FLUSH CUTS, use knipex cutters or maybe even tin snips.

![](/assets/flushcuts.png)

### Oscilloscope

Oscilloscopes are another great tool for debugging electronics. Oscilloscopes show a visual representation of electrical values.

Oscilloscopes can be very complicated and have a lot of features, so I'll let you read this [article](https://learn.sparkfun.com/tutorials/how-to-use-an-oscilloscope).

### Variable Power Supply

Variable power supplies are great for working with electronics. They allow you to set the voltage and amperage output of the supply.

![](/assets/variablepsu.png)

### Function Generator

Function generators allow you to create a waveform. This is useful for example when controlling servos, which require a PWM signal to control. I'll go more into PWM in the making stuff move article.

![](/assets/functiongenerator.png)

## Software tools/skills:

Software tools are extremely helpful for designing circuits beforehand. I'll go over the following tools from most beginner friendly to most advanced.

### [Tinkercad circuits](https://www.tinkercad.com/circuits)

I'm not really sure what my thoughts are on tinkercad circuits. I don't recommend using it for anything more than the most simple circuits, but it really is a great tool for learning electronics. It also has a pretty good simulator for simulating what your circuit will do without having to implement which is pretty cool. 

### [Fritzing](http://fritzing.org/home/)

I much prefer fritzing for making stuff like wiring diagrams. It functions similar to tinkercad circuits, but has an extremely large database of parts.

### [EagleCAD](https://www.autodesk.com/products/eagle/overview)

eagleCAD is a paid piece of software, but if you are a student you can get it for free. eagleCAD allows you to make professional schematics, but it's main feature is PCB design. PCBs, or printed circuit boards, are extremely useful when making complicated circuits. To design them, you do need a fair bit of knowledge, but sparkfun does have some good tutorials [here](https://learn.sparkfun.com/tutorials/tags/eagle). 

### [SOLIDWORKS PCB](http://smart.solidworks.com/electronics-design.html)

SOLIDWORKS PCB is the best design software, but unless you are willing to "find it on the interwebs", it costs thousands of dollars, so I can't really recommend it.

### 



