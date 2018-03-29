# Sensors

Sensors are how your robot reads in the environment around it.

## Switches/buttons:

Switches and buttons are the simplest type of sensor. I'll first go over some general info about switches and buttons, and then go into detail about some of the more common types.

The only difference between a switch and a button is that if you actuate a switch it stays in the opposite position. They work identically, which is by making contact between conductors to open or close a circuit. Switches and buttons can either be Normally Open \(NO\) or Normally Closed \(NC\). If a switch is NO, the actuation of the switch/button closes a circuit, while a NC button/switch would be closed until actuated, which would open the circuit. Switches/buttons do have a max amperage they can carry before they blow up. Do not push this limit. I have tried in the past, and it ends rather poorly.

For future reference, when reading a button with a micro-controller, you read it as a digital value, and you need to either use the micro-controllers pull-up or implement a pull-up yourself.

### Breadboard button

![](/assets/breadboardbutton.png)

Breadboard buttons are just very basic buttons. They are NO, and they connect the left and the right side. For example in the blue button in the picture above the pins in rows 1 and 3 are normally not connected, but when the button is pressed, they connect.

These can not handle much current, and may blow up if you push them too far.

### Arcade button

Arcade buttons work identically to breadboard buttons except they look cooler.

![](/assets/arcadebutton.png)

### E Stop

I love e-stop switches, as they are satisfying to use, and usually are used in applications when something dangerous could happen. 

![](/assets/estopswitch.png)

To close the circuit, you rotate the big red button, and when something inevitably goes wrong, you hit the big red button and it disconnects the circuit immediately. e-stops are used frequently on the main power lines of a machine, so in the event of a failure, it is easy to safely disconnect power quickly.

### Key switch

Key switches are switches that require a key to close a circuit.

![](/assets/keyswitch.png)

### microswitch

Microswitches are switches that are very easy to actuate. They are frequently used in 3D printers when the printer homes its axis. They usually have 3 leads, one common, one NC, and one NO.

![](/assets/microswitch.png)

### dip switches

Dip switches are frequently used for representing binary numbers. They are an array of small switches.

![](/assets/dipswitch.png)

## Potentiometer

See [Basic Circuits](/general-resources/electronics/basic-circuits.md)

## Ultrasonic Ranger



## IR

## Photoresistor 

## Hall Sensor

## ir led

## encoder

## i2c devices:

## color

## imu

## adc

## cameras



