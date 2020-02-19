## Alternative visual remote

In **Scratch visual remote** you made a Scratch based remote which turned the motors **on** and **off** momentarily. An alternative to this is a remote that turns the motors on until given another instruction. In other words, the motors will not turn off automatically.

You could do this by simply removing the `wait`{:class="block3control"} and `set gpio pins low`{:class="block3extensions"} from each of the direction sprites but just to shake things up a little, you're going to try something a little different here.

In this section, you'll set your direction sprites to activate whenever the mouse pointer is over them and create a new **stop** sprite to turn the motors off.

--- task ---

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

Next, let's look at the **forward** sprite.

The previous code turned the forward GPIO pins on, waited and then turned them off again using the sprite being clicked as the _event_.

![Forwards sprite](images/spriteIcon_forwards.png)

```blocks3
when this sprite clicked
set gpio (8 v) to output [high v] ::extension
set gpio (10 v) to output [high v] ::extension
wait (0.5) seconds
set gpio (8 v) to output [low v] ::extension
set gpio (10 v) to output [low v] ::extension

```

You'll change this to turn the motor forward GPIO pins on when the mouse pointer is _touching_ the forward sprite.

--- task ---

From the `events`{:class="block3events"} block palette, grab a `when space key presses`{:class="block3events"} block.

Add a block to `set the size to 200%`{:class="block3looks"} or whatever works for you.

![Forwards sprite](images/spriteIcon_forwards.png)

```blocks3
when [space v] key pressed
set size to (200) %
```

--- /task ---

--- task ---

Since you want the sprite to _always_ keep checking if the mouse pointer is touching the sprite, you'll need a `forever`{:class="block3control"} loop and a conditional `if... then...`{:class="block3control"} block.

![Forwards sprite](images/spriteIcon_forwards.png)

```blocks3
when [space v] key pressed
set size to (200) %
+ forever
    if () then
+ end
```

--- /task ---

--- task ---

Next, you'll add the _condition_ to be checked - Is the sprite touching the mouse pointer?

![Forwards sprite](images/spriteIcon_forwards.png)

```blocks3
when [space v] key pressed
set size to (200) %
forever
    if <touching (mouse-pointer v) ? :: sensing +> then    
 end
```

--- /task ---

--- task ---

Inside the conditional `if... then...`{:class="block3control"} block, place the `set gpio`{:class="block3extensions"} blocks to turn the forward motors high, or _on_.

![Forwards sprite](images/spriteIcon_forwards.png)

```blocks3
when [space v] key pressed
set size to (200) %
forever
    if <touching (mouse-pointer v) ?> then
+        set gpio (8 v) to output [high v] ::extension
+        set gpio (10 v) to output [high v] ::extension
 end
```

--- /task ---

Now, whenever the mouse pointer touches the sprite, the forward motors will turn on but there is no code to turn them off again. In other words, until they receive another instruction from another sprite, the robot buggy will continue moving forwards.

Since this rule will also apply to the other direction sprites, you will need to add code blocks to make sure any GPIO pins other than your **forwards** pins are turned off.

--- task ---

Add the `set gpio off`{:class="block3extensions"} blocks **before** the `set gpio on`{:class="block3extensions"} blocks just to make sure they are not all on at the same time.

![Forwards sprite](images/spriteIcon_forwards.png)

```blocks3
when [space v] key pressed
set size to (200) %
forever
    if <touching (mouse-pointer v) ?> then
+        set gpio (7 v) to output [low v] ::extension
+        set gpio (9 v) to output [low v] ::extension
        set gpio (8 v) to output [high v] ::extension
        set gpio (10 v) to output [high v] ::extension
 end
```

Test the code by moving the mouse pointer over the forward sprite and checking that the motors turn forwards. Remember that there is no code to turn the motors off, but you can press **q** to activate the _kill code_.

--- /task ---

--- task ---

Repeat this code for the backwards, right and left sprites, using the correct GPIO pins for each direction.

![Backwards sprite](images/spriteIcon_backwards.png)

```blocks3
when [space v] key pressed
set size to (200) %
forever
    if <touching (mouse-pointer v) ?> then
        set gpio (8 v) to output [low v] ::extension
        set gpio (10 v) to output [low v] ::extension
        set gpio (7 v) to output [high v] ::extension
        set gpio (9 v) to output [high v] ::extension
 end
```

![Right sprite](images/spriteIcon_right.png)

```blocks3
when [space v] key pressed
set size to (200) %
forever
    if <touching (mouse-pointer v) ?> then
        set gpio (8 v) to output [low v] ::extension
        set gpio (9 v) to output [low v] ::extension
        set gpio (7 v) to output [high v] ::extension
        set gpio (10 v) to output [high v] ::extension
 end
```

![Left sprite](images/spriteIcon_left.png)

```blocks3
when [space v] key pressed
set size to (200) %
forever
    if <touching (mouse-pointer v) ?> then
        set gpio (7 v) to output [low v] ::extension
        set gpio (10 v) to output [low v] ::extension
        set gpio (8 v) to output [high v] ::extension
        set gpio (9 v) to output [high v] ::extension
 end
```

--- /task ---



