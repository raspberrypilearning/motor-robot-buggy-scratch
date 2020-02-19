## Scratch keyboard remote

In this section you will overcome the issue of looking at the screen and trying to see what your robot buggy is doing at the same time by creating a keyboard remote control.

--- task ---

As usual, you will need to start with the motor _kill code_ that we have used in all our projects.

Create this code or start from a project that already has it leaving just a single sprite on which all your code will go.

![Cat sprite](images/spriteIcon_cat.png)

```blocks3
when [q v] key pressed
set gpio (7 v) to output [low v] ::extension
set gpio (8 v) to output [low v] ::extension
set gpio (9 v) to output [low v] ::extension
set gpio (10 v) to output [low v] ::extension
stop [all v]
```

--- /task ---

The easiest way to code the keyboard remote would be to use `when key pressed`{:class="block3events"} events to trigger code that turns the motor GPIO pins on then off in a very similar way to the **Scratch visual remote** section, but you're about to use a way that is more complicated but far more responsive in use.

The first step is to make new Scratch blocks that define moving in each direction.

--- task ---

Go to the `My Blocks`{:class="block3myblocks"} block palette and click on the `Make a Block` button. Give the new block the name **forwards** and click **ok**.

A new event style block, `Define forwards`{:class="block3myblocks"} will appear in the red `My Blocks`{:class="block3myblocks"} colour.

![Cat sprite](images/spriteIcon_cat.png)

```blocks3
define [forwards]
```

--- /task ---





Starting where you left off from the last **visual remote**, move the cat sprite out of the way and down to a corner to make way for a central **stop** sprite.

You can set the size in the sprite informtion box at the top of the sprite window.

![Sprite information box](images/altVisualRemote_spriteInformation.png)

It is good practice, however, and a good habit to get used to, to use code to set the size and other details.

For remote controls it is sometimes useful to stick to keyboard commands, so instead of using the green flag as an event, try using something else. The `SPACE` key is ideal being so easy to find.

Add a block from the looks block palette to `set the size to 50%`{:class="block3looks"}

![Cat sprite](images/spriteIcon_cat.png)

```blocks3
when [space v] key pressed
set size to (50) %
```

NOTE: Your cat sprite should still have the _kill code_ that stops all motors.

--- /task ---