## Testing the motors with Scratch

Any motor controller for two motors will use four GPIO pins to send signals to the motors.
+ Motor A clockwise
+ Motor A counter-clockwise
+ Motor B clockwise
+ Motor B counter-clockwise

For the CamJam EduKit motor in these instructions, the GPIO pin numbers are 9 and 10 for motor A, and 7 and 8 for motor B.

### Stop all motors!

You're going to write some simple code to test that everything is working and test which pin makes each wheel go in each direction, but first of all, you're going to write a software _kill code_ script to stop all the motors.

--- task ---

Open Scratch 3 and load the **Raspberry Pi GPIO** extension.

To do this, click on the add an extension button and choose the `Raspberry Pi GPIO` extension.

![Add the Raspberry Pi GPIO extension](images/testing_GPIOextension.png)

--- /task ---

--- task ---

Grab a `when space key pressed`{:class="block3events"} event block and change the event key to **q**.

```blocks3
when [q v] key pressed
```

--- /task ---

--- task ---

from the Raspberry Pi GPIO block palette, add a block that says `set gpio 7 to output low`{:class="block3extensions"}.

```blocks3
when [q v] key pressed
+ set gpio (7 v) to output [low v] ::extension
```

--- /task ---

This will turn GPIO pin 7 low (off) and keep it off. Now you need more of these blocks for pins 8, 9 and 10.

--- task ---

```blocks3
when [q v] key pressed
set gpio (7 v) to output [low v] ::extension
+ set gpio (8 v) to output [low v] ::extension
+ set gpio (9 v) to output [low v] ::extension
+ set gpio (10 v) to output [low v] ::extension
```

--- /task ---

--- task ---

Finally, add a block from the control block palette to `stop all`{:class="block3control"} to ensure the motors don't start again until you want them to.

```blocks3
when [q v] key pressed
set gpio (7 v) to output [low v] ::extension
set gpio (8 v) to output [low v] ::extension
set gpio (9 v) to output [low v] ::extension
set gpio (10 v) to output [low v] ::extension
+ stop [all v]
```

--- /task ---

That's the completed _kill switch_ that will turn off all the motors. Press the *q* key if ever you need to stop everything in a hurry. This is really useful if you have a motor wrapping inself round a wire!

### Test codes

The next step is to write a snippet of code for each motor that will tell you what that motor does.

--- task ---

Add a new `event`{:class="block3events"} block for the *7* key.

```blocks3
when [7 v] key pressed
```

--- /task ---

--- task ---

Under that, place a block to turn GPIO pin 7 on (high).

```blocks3
when [7 v] key pressed
+   set gpio (7 v) to output [high v] ::extension
```

This will turn GPIO pin 7 **on**, making one motor turn in either backwards or forwards. You don't want to leave it on though!

--- /task ---

--- task ---

To turn the motor off again, add a tiny `wait`{:class="block3control"} and another block to turn GPIO pin 7 off (low).

```blocks3
when [7 v] key pressed
set gpio (7 v) to output [high v] ::extension
+   wait (0.1) seconds
+   set gpio (7 v) to output [low v] ::extension
```

Now the motor will turn on, showing which motor and which direction, then quickly turn off again. Press the **7** key to test it.

--- /task ---

--- task ---

Now repeat that code for each of your GPIO pins 8, 9 and 10.

```blocks3
when [8 v] key pressed
set gpio (8 v) to output [high v] ::extension
wait (0.1) seconds
set gpio (8 v) to output [low v] ::extension

when [9 v] key pressed
set gpio (9 v) to output [high v] ::extension
wait (0.1) seconds
set gpio (9 v) to output [low v] ::extension
```

Since there is no **10** key, use `when 0 key pressed`{:class="block3events"} for GPIO pin 10.

```blocks3
when [0 v] key pressed
set gpio (10 v) to output [high v] ::extension
wait (0.1) seconds
set gpio (10 v) to output [low v] ::extension
```

**NOTE:** You could get away with making these blocks for pins 7 and 9 only, since pin 8 move the same motor as pin 7 but in the opposite direction and the same goes for pins 9 and 10.

Press the **8**, **9** and **10** keys in turn to see what each does.

--- /task ---