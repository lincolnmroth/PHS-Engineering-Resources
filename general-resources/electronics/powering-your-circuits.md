# Powering your circuits

Watt is power.

Now that I'm done with terrible puns, let's actually do this.

There are four main sections I will go over.

* Batteries
* Battery Regulation
* Power Distribution
* Wall Power

## Batteries:

I already went over batteries in the [Power System](/general-resources/robotics/power-system.md) article.

## Battery regulation:

Sometimes the batteries you get are not at the voltage you want. When this is the case you have a few options:

* Get a battery the correct voltage
* Use a voltage divider
* Use a buck converter 

The first one is pretty self explanatory, so I'm not going to go over that.

### Voltage Divider:

A voltage divider is really never the best option, but it works in a pinch. Basically you just use 2 resistors to lower the voltage, but at the cost of the extra power being wasted as heat.

### Buck Converter:

A [buck converter](https://en.wikipedia.org/wiki/Buck_converter) allows you to conserve power when stepping down the voltage. Ones that are programmable and fancy can be very expensive, but since usually people need 5v or 12 v, it is pretty easy to find UBEC's \(Universal Battery Eliminator Circuit\) to step down voltages to 5 or 12 volts. Also many brushless ESC's have built in 5v BEC's, which is really useful, but if you forget that it is outputting voltage, it is possible to blow up arduinos or your computer \(I have most definitely never done this\).

## Power distribution:

Distributing power requires no electronics \(except wires and metal\), but can be very complicated, and is always different depending on the application, and can get especially annoying if emi ever becomes a problem. 

The main rule of thumb is to centralize as much as possible. Have a single bus to distribute power if possible.

## AC Power

Basically don't. AC sucks. High voltage hurts. Don't unless you absolutely have to, and if you do, please be very carful.

