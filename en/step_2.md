## Set up your motors

There are two common ways to connect a **motor controller** to your Rapsberry Pi 4:
+ Plug it straight onto the GPIO pins
+ Use jumper cables or wires to connect it

A common and very inexpensive motor controller is the L298N Dual H Bridge DC Stepper Motor Driver Controller Board, which is connected with jumper cables and wires. If you have this kind of controller, there are simple instructions on how to connect it in the [Build a robot buggy project](https://projects.raspberrypi.org/en/projects/build-a-buggy/2){:target="_blank"}.

![L298N dual H bridge motor controller](images/setup_L298N.png)

The instructions here are for a [CamJam EduKit 3 motor controller](https://thepihut.com/products/camjam-edukit-motor-controller){:target="_blank"} which simply fits straight on top of the Pi's GPIO pins.

![Motor controller on GPIO pins](images/setup_mcOnGPIO.png)

The controller fits to the end GPIO pins nearest the edge of the board; the body of the controller faces inwards over the Raspberry Pi.

Most _plug-on_ motor controller boards have a similar format with a **power-in** terminal, a **negative ground** terminal, and then a **positive** and **negative** terminal for each motor output. In most cases, the Pi still needs its own power supply and a battery pack is used to power the motors via the controller.

![Motor controller on GPIO pins closeup](images/setup_mcOnGPIOcloseup.png)

**Note:** It is important to get the battery pack polarity correct. However when connecting the motors, polarity is not essential, it simply affects which GPIO pin controls forwards or backwards.

It is usually easier and safer to connect your battery box and motors before you connect the motor controller board to the Pi.

--- task ---

Connect the positive (red) wire from the battery box to the positive terminal on the motor controller. On newer models of the CamJam motor controller, this is simply marked with a **+** symbol. On older versions (as in the picture) it is marked as VIN (voltage in).

To connect the wire, unscrew the terminal screw, insert the exposed wire (not the coloured insulation covering) and tighten the screw so that the terminal _clamps_ the wire in place.

![Connect battery box](images/setup_battBoxPos.png)

--- /task ---

--- task ---

Next, connect the negative (black) wire from the battery box to the negative terminal on the motor controller. On newer models of the CamJam motor controller this is marked with a **-** symbol. On the older versions it is marked as GND (ground).

![Connect battery box](images/setup_battBoxNeg.png)

--- /task ---

--- task ---

To connect the first motor, connect the two motor wires to the two terminals marked **Motor A**. It does not matter which way round the wires go at this stage.

![Connect motor 1](images/setup_motor1.png)

--- /task ---

--- task ---

Repeat the same process for the second motor and connect the second motor's wires to the two terminals marked **Motor B**. It does not matter which way round the wires go or that they match the order of the motor A wires.

![Connect motor 1](images/setup_motor2.png)

--- /task ---

--- task ---

Finally, you need to connect the motor controller to the Raspberry Pi GPIO pins. In this case, the controller goes over the outermost pins facing inwards over the Pi.

![Connect motor controller](images/setup_mcOn.png)

--- /task ---

--- task ---

If you have not already done so, put four AA batteries in the battery box.

--- /task ---

You've connected everything together. The next step is to start coding in Scratch 3 to get things on the move.
