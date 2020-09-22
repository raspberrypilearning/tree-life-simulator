## Grow more trees

In the simulation we want to see the impact of trees growing at a faster or slower speed. The speed at which a forest grows depends on a number of factors such as soil quality, disease, sunlight and water.

The growing speed will be stored in a variable called forest health.

--- task ---

Create a new `variable`{:class="block3variables"} by clicking on the `Variables`{:class="block3variables"} blocks menu.

Then click on the **Make a Variable** button.

You can give your `variable`{:class="block3variables"} a name. Call this variable `forest health`.

--- /task ---

Your new variable is visible on the stage. Use a slider to control the speed in your simulation.

--- task ---

On the stage, right-click on the `forest health`{:class="block3variables"} variable, and a menu will appear.

Select slider in the menu.

--- /task ---

At the moment the forest health range is too wide.

--- task ---

On the stage, right-click on the `forest health`{:class="block3variables"} slider and select **change slider range**.

Change the range to between `0` and `5`.

--- /task ---

Using `forest health`{:class="block3variables"} to grow the forest.

--- task ---

Add a `forever`{:class="block3control"} block to the end of the `when flag clicked script`{:class="block3events"} so that new trees are continuously planted. Within the `forever`{:class="block3control"} loop add a `go to mousepointer`{:class="block3motion"} block changing the value to `random position`. Next add a `wait 1 seconds`{:class="block3control"} block and a `create a clone of myself`{:class="block3control"} block to complete the loop.

```blocks3
when flag clicked
repeat (50)
go to [random position v]
create clone of [myself v]
end
+ forever
go to [random position v]
wait (1) seconds
create clone of [myself v]
end
```

--- /task ---

The slider will control the speed the trees grow but currently the code is set to always wait 1 seconds. Moving the slider to the right will speed up the growth whilst moving to the left will decrease the growth.

--- task ---

Add a `minus operator`{:class="block3operators"} entering the value `5` in the first circle. Drag a rounded `forest health`{:class="block3variables"} variable into the second circle. This means if `forest health`{:class="block3variables"} equals `4` the wait time will be 1 second but if `forest health`{:class="block3variables"} equals `2` the wait time will be slower at 3 seconds.

```blocks3
when flag clicked
repeat (50)
go to [random position v]
create clone of [myself v]
end
forever
go to [random position v]
+ wait ((5)-(forest health)) seconds
create clone of [myself v]
end
```

--- /task ---
