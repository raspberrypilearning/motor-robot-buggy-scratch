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

```blocks3
define forwards
```

--- /task ---

--- task ---

Under the `Define forwards`{:class="block3myblocks"} block, add the two `set gpio`{:class="block3extensions"} blocks to turn the forward motors on.

```blocks3
define forwards
+ set gpio (8 v) to output [high v] ::extension
+ set gpio (10 v) to output [high v] ::extension
```

Nothing else is needed. No `wait`{:class="block3control"} or `set gpio low`{:class="block3extensions"}. This block is simply to _define_ what code makes the robot buggy go `forwards`{:class="block3myblocks"}.

--- /task ---

--- task ---

Now do the same for `backwards`{:class="block3myblocks"}, `right`{:class="block3myblocks"} and `left`{:class="block3myblocks"}.

```blocks3
define backwards
+ set gpio (7 v) to output [high v] ::extension
+ set gpio (9 v) to output [high v] ::extension

define right
+ set gpio (7 v) to output [high v] ::extension
+ set gpio (10 v) to output [high v] ::extension

define left
+ set gpio (8 v) to output [high v] ::extension
+ set gpio (9 v) to output [high v] ::extension
```

Note: It is not really necessary to make these `custom blocks`{:class="block3myblocks"} to make the code work, but it will make your code very easy to read and is a useful step before we move to the next section's **programmed maze journeys**.

--- /task ---

