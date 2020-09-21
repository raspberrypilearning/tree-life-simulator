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

The slider will control the speed the trees are planted but currently the code is set to always wait 1 seconds. Moving the slider to the right will speed up the planting whilst moving to the left will decrease the speed.

Add a minus operator entering the value `5` in the first circle. Drag a rounded `planting speed` variable into the second circle. This means if `planting speed` equals `4` the wait time will be 1 second but if the `planting speed` equals `2` the wait time will be slower at 3 seconds.

```blocks3
when flag clicked
repeat (50)
go to [random position v]
create clone of [myself v]
end
forever
go to [random position v]
+ wait ((5)-(planting speed)) seconds
create clone of [myself v]
end
```

--- /task ---

Scientists monitor trees and wildlife. They record the cover (size), variety and health of the forests. By doing this they can see the true impact of deforestation. Observations are taken from planes and satellites in the air as well as sensors and people on the ground.

--- task ---

Create a new variable to store the number of trees. Call this variable `trees`.

--- /task ---

When the simulation begins the number of trees will be `0` and every time a new tree grows this will change by `1`.

--- task ---

To reset the number of trees when the simulation starts, go to your `when flag clicked`{:class="block3events"} script and insert a `set (trees) to (0)`{:class="block3variables"} block underneath the first block.

```blocks3
when flag clicked
+ set (trees) to (0)
repeat (50)
go to [random position v]
create clone of [myself v]
end
forever
go to [random position v]
wait ((5)-(planting speed)) seconds
create clone of [myself v]
end
```

--- /task ---

The survival rate for new trees is 80% meaning that 2 trees out of every 10 planted will die of natural causes before they are fully grown. Add new fully-grown trees to your count to see how many there are whilst the simulation is running.

--- task ---

At the end of your `when I start as a clone` script add a `change trees by 1` block.

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
set size to (0)%
repeat (10)
change size by (2)
wait (0.1) seconds
end
+ change (trees) by (1)
```

--- /task ---

We can now count our new trees but even fully-grown trees can die or be chopped down through both human and natural deforestation. We need to reduce our count of trees if a tree has been touched by the **Tree feller** or **Natural Disaster** sprites.

--- task ---

Add a `wait until` block to the end of your code. Use an `or operator` to allow a choice of events. In the first circle of your `or` block add a `touching mouse-pointer ?` block and change the value to `Tree feller`. In the second circle of your `or` block add another `touching mouse-pointer ?` block and change the value to 'Natural Disaster'.

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
set size to (0)%
repeat (10)
change size by (2)
wait (0.1) seconds
end
change (trees) by (1)
+ wait until {{touching [Tree feller v]?} or {touching [Natural Disaster v]?}}
```
--- /task ---

--- task ---

Now, add a `change Trees by (1)` block changing the value to `-1` and finally a `delete this clone` block to remove the tree.

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
set size to (0)%
repeat (10)
change size by (2)
wait (0.1) seconds
end
change (trees) by (1)
wait until {{touching [Tree feller v]?} or {touching [Natural Disaster v]?}}
+ change (trees) by (-1)
+ delete this clone
```

--- /task ---