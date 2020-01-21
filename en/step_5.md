## Challenge: Adapting your motor project

This is a very open challenge with enormous room for freedom in what you do. 

Take your project from the lest section, or another if you like, and turn it into something else, adapt it, improve it in some way you had not originally thought of!

The changes could involve more making, more coding or both! There is no right or wrong. You are the judge of whether the change is an improvement or not.

If you feel a bit overwhelmed by open possibilities, how about turning your creation into a _crazy golf_ obstacle where you have to try and get a ball past your moving obstacle?

The crazy golf idea doesn't need to end there. You could have a moving obstacle to try and get a remote control buggy past, or something else, like a Sphero. Use whatever you can get your hands on!

--- no-print ---

![A crazy golf windmill](images/adaptation_windmill.gif)

--- /no-print ---

--- print-only ---

![A crazy golf windmill](images/adaptation_windmill.png)

--- /print-only ---

### Crazy golf

What you will need to do for a crazy golf project:
+ have a target or destination for the ball (or robot) to get to
+ code your obstacle to move in a way that makes getting past possible, but not too easy

For the example windmill, a hole has been cut in the front of the mill and the **target** is getting a ball **inside** the windmill itself!

You'll probably come across unexpected issues as you go. The Raspberry Pi and battery box used to sit at the bottom of the windmill, so they needed to find a new home.

--- task ---

Adapt your project model so that there is space for the Raspberry Pi, battery box, etc. to be stored, and so that there is a target for the ball. 

**Note:** the target does not have to be a part of your original project model. The target could be somewhere _beyond_ your obstacle where the ball needs to pass your obstacle safely.

In the example project, a shelf was needed to the electronics.

![A shelf for the Pi](images/adaptation_shelf.png)

A hole in the front of the tower created the target destination inside the windmill.

![Doorway to target](images/adaptation_hole.png)

--- /task ---

--- task ---

Next, you will need to adapt your code for this new purpose.

In this example, we'll start with the code from the last section for the windmill.

```blocks3
when flag clicked
forever
set gpio (7 v) to output [high v] ::extension
wait (pick random (1) to (3) :: operators +) seconds
set gpio (7 v) to output [low v] ::extension
wait (pick random (3) to (15) :: operators +) seconds
end
```

How will you change this code to make a fun crazy golf obstacle?

--- /task ---

--- hints ---

--- hint ---

To make the challenge hard, which also makes it fun, you will need to:

+ turn the windmill off only for a very short time
+ make it hard to predict when the windmill will start and stop

--- /hint ---

--- hint ---

Making it hard to predict when the windmill will start and stop is easy. Just keep the random wait blocks.

The biggest change is to make the numbers much lower. You will need to experiment to see what works best in your project but the windmill example used `wait`{:class="block3control"} times between `0.1`{:class="block3control"} and `1.5 seconds`{:class="block3control"} only!

--- /hint ---

--- hint ---

The code below worked for the windmill example crazy golf obstacle but you'll have to play with the numbers to find what works best for you and your project.

```blocks3
when flag clicked
forever
set gpio (7 v) to output [high v] ::extension
wait (pick random (0.1) to (1.5) :: operators +) seconds
set gpio (7 v) to output [low v] ::extension
wait (pick random (0.3) to (1.2) :: operators +) seconds
end
```

--- /hint ---

--- /hints ---
