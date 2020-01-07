## Testing the motors with Scratch

Any motor controller for two motors will use four GPIO pins to send signals to the motors.
+ Motor A clockwise
+ Motor A counter-clockwise
+ Motor B clockwise
+ Motor B counter-clockwise

For the CamJam EduKit motor in these instructions, the GPIO pin numbers are 7 and 8 for motor A, and 9 and 10 for motor B.

Let's write some simple code to test that everything is working and which pin makes each wheel go in each direction.

--- task ---

Open Scratch 3 and load the **Raspberry Pi GPIO** extension.

To do this, click on the add an extension button and choose the `Raspberry Pi GPIO` extension.

![Add nthe Raspberry Pi GPIO extension](images/testing_GPIOextension.png)

--- /task ---


