## Plant more trees

In the simulation we want to see the impact of planting trees at a faster or slower speed.

The speed will be stored in a variable.

--- task ---

Create a new `variable`{:class="block3variables"} by clicking on the `Variables`{:class="block3variables"} blocks menu.

Then click on the **Make a Variable** button.

You can give your `variable`{:class="block3variables"} a name. Call this variable `planting speed`.

--- /task ---

Your new variable is visible on the stage. Use a slider to control the speed in your simulation.

--- task ---

On the stage, right-click on the `planting speed`{:class="block3variables"} variable, and a menu will appear.

Select slider in the menu.

--- /task ---

At the moment the planting speed range is too wide.

--- task ---

On the stage, right-click on the `planting speed`{:class="block3variables"} slider and select **change slider range**.

Change the range to between `0` and `5`.

--- /task ---

Using our planting speed to grow the forest.

--- task ---

Add blocks to the end of the when flag clicked script so that new trees are planted forever.



```blocks3
when flag clicked
repeat (50)
go to [random position v]
create clone of [myself v]
end
+ forever
+ go to [random position v]
+ wait (1) seconds
+ create clone of [myself v]
+ end
```

--- /task ---

--- task ---

Task Text.

--- /task ---

--- task ---

Task Text.

--- /task ---
