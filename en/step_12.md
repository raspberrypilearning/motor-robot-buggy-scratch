## Programmed maze journeys

In this section you will adapt your custom `My Blocks`{:class="block3myblocks"} and then use them to pre-program your robot buggy to navigate through a maze or some other obstacle course that you make.

--- task ---

Starting with the code you had for **Scratch keyboard remote**, keep your _kill code_, and `custom movement blocks`{:class="block3myblocks"} for `forwards`{:class="block3myblocks"}, `backwards`{:class="block3myblocks"}, `right`{:class="block3myblocks"} and `left`{:class="block3myblocks"}.

You will not need and of the code in you `forever`{:class="block3control"} loop or the `stop`{:class="block3myblocks"} block, so throw those away.

--- /task ---

Now, you're going to add to your `custom movement blocks`{:class="block3myblocks"} so that each `sets gpio pins high`{:class="block3extensions"}, `waits`{:class="block3control"} and then `sets gpio pins low`{:class="block3extensions"} again.

The clever coding here is building the `wait time`{:class="block3control"} into the `custom blocks`{:class="block3myblocks"}.

Let's start with the `define forwards`{:class="block3myblocks"} block.

--- task ---

Under the `set gpio high`{:class="block3extensions"} blocks, add a `wait`{:class="block3control"} block.

Beneath that, add `set gpio low`{:class="block3extensions"} blocks for the same GPIO pins that you just turned high.

```blocks3
define forwards
set gpio (8 v) to output [high v] ::extension
set gpio (10 v) to output [high v] ::extension
+ wait (1) seconds
+ set gpio (8 v) to output [low v] ::extension
+ set gpio (10 v) to output [low v] ::extension
```

--- /task ---

Now for the clever part.

--- task ---

Right-click on the `define forwards`{:class="block3myblocks"} block and choose `edit`.

In the dialogue box that opens, click on the `Add an input: number or text` button.

A new input entry will appear in the `forwards`{:class="block3myblocks"} block above. Give this input entry the name **time** and click `OK`.

From your `define forwards`{:class="block3myblocks"} block, which now reads `define forwards (time)`{:class="block3myblocks"} drag the round `time`{:class="block3myblocks"} bubble into the `wait`{:class="block3control"} block's input bubble.


```blocks3
define forwards (time :: custom +) :: custom
set gpio (8 v) to output [high v] ::extension
set gpio (10 v) to output [high v] ::extension
wait (time :: custom +) seconds
set gpio (8 v) to output [low v] ::extension
set gpio (10 v) to output [low v] ::extension
```

--- /task ---

Have a look at how this has changed the `forwards`{:class="block3myblocks"} block in the `My Blocks`{:class="block3myblocks"} block palette.

```blocks3
forwards () :: custom
```

The `forwards`{:class="block3myblocks"} block now has a new input field in which you can enter the amount of time that the GPIO pins will wait until turning off.

```blocks3
forwards (0.5) :: custom
```

`forwards 0.5`{:class="block3myblocks"} tells the robot buggy to go forwards for 0.5 seconds.

--- task ---

Repeat the last step, adding a `time`{:class="block3myblocks"} input for the `time`{:class="block3myblocks"}, `time`{:class="block3myblocks"} and `time`{:class="block3myblocks"} custom blocks.


```blocks3
define forwards (time +) :: custom 
set gpio (8 v) to output [high v] ::extension
set gpio (10 v) to output [high v] ::extension
wait (time :: custom +) seconds
set gpio (8 v) to output [low v] ::extension
set gpio (10 v) to output [low v] ::extension
```

--- /task ---


