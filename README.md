polargraph_server_a1
====================

Modified for MarkBs Eggbot/Polargraph v2.2 or newer Arduino Nano control board. See www.sub-design.co.uk or http://www.makebournemouth.com/?p=340 or github.com/markjb for details. 

Update (14/02/2016): Tested extensivley with the v2.2 boards and it is rock solid. Note: This code will not work with boards prior to v2.2 as the pinout was extensivley modified.

Note: Firmware compiles with SD card but not tested... Yeah - SD card support is looking pretty pointless as the code to do Norwegian Pixel makes the firmware about 50k which aint gonna fit in the 328... So its either use a Mega or port to Teensy and given the cost of a Mega clone vs a Teensy, the only benifit of a Teensy would be the small size.

====================

Polargraph Server for Arduino UNO and MEGA compatible boards using Adafruit motorshields,
serial stepper drivers (eg Easy Drivers, stepsticks etc) or signal amplifiers (eg ULN2003s).

It is called *_a1* because it is the version for the first arduino (ie Uno, or Duemilanove).  
Bit obtuse that, I know.

For convenience, I have pre-compiled and included two hex files:

1. **polargraph_server_a1_adafruit_v1.cpp.hex** - Is for motorshield v1.
2. **polargraph_server_a1_adafruit_v2.cpp.hex** - Is for the new motorshield v2.

Motor driver:
-------------

This firmware works for:

1. Adafruit Motorshield v1 that uses AFMotor as it's software driver
2. Adafruit Motorshield v2 that uses Adafruit_MotorShield as it's software driver
3. Generic serial stepper drivers, eg Stepsticks or Easy Drivers
4. Four-wire signal amplifier, eg UNL2003

To switch between the different drivers, and to configure a few other bits and pieces,
comment out some lines near the beginning of polargraph_server_a1.ino.


There are five config sections:

1. Specify what kind of controller board you are using
2. Add some libraries if you have a MEGA
3. Specify what kind of motor driver you are using:
  1. Adafruit Motorshield v1
  2. Adafruit Motorshield v2
  3. Discrete stepper drivers (eg EasyDriver, stepstick, Pololu gear).*
  4. Signal amplifier like a UNL2003*
4.  Turn on some debugging code
5.  Disable program features if you need to free up space

* For motor drivers iii and iv, you will need to change the values in
  configuration.ino to set the exact pins the drivers are wired up to.


The program has a core part that consists of the following files that are common to all Polargraph Server versions:

- comms.ino
- configuration.ino
- eeprom.ino
- exec.ino
- penlift.ino
- pixel.ino
- util.ino

and 
- polargraph_server_a1.ino

which is named for the project.


Polargraph
----------

Polargraph is the name of the project, and is a portmanteau word invented by the writer
solely for this purpose. Any machine that runs the Polargraph software is technically a 
polargraph machine. I usually reserve the big-P "Polargraph" for things made by
The Polargraph Company, including the Polargraph software and PolargraphSD machine.

Other hanging-v plotters are probably compatible with Polargraph software, but unless
they run it, they are not even polargraphs with a small P.

Project and software written by Sandy Noble.

Released under GNU License version 3.

http://www.polargraph.co.uk

https://github.com/euphy/polargraph_server_a1
