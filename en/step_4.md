## Count the trees

Scientists monitor trees and wildlife. They record the cover (size), variety and health of the forests. By doing this they can see the true impact of deforestation. Observations are taken from planes and satellites in the air as well as sensors and people on the ground.

--- task ---

Create a new variable to store the number of trees. Call this variable `trees`{:class="block3variables"}.

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

The survival rate for new trees is estimated to be 80% meaning that 2 trees out of every 10 planted will die of natural causes before they are fully-grown. Add new fully-grown trees to your `trees`{:class="block3variables"} count to monitor how many there are whilst the simulation is running.

--- task ---

At the end of your `when I start as a clone`{:class="block3control"} script add a `change trees by 1`{:class="block3variables"} block.

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

We can now count our new trees but even fully-grown trees can die or be chopped down through human and natural deforestation. We need to reduce our count of trees if a tree has been touched by the **Tree feller** sprite or **Natural Disaster** sprite.

--- task ---

Add a `wait until`{:class="block3control"} block to the end of your code. Use an `or`{:class="block3operators"} operator to allow a choice of events. In the first circle of your `or`{:class="block3operators"} block add a `touching mouse-pointer`{:class="sensing"} block and change the value to `Tree feller`. In the second circle of your `or`{:class="block3operators"} block add another `touching mouse-pointer`{:class="block3sensing"} block and change the value to `Natural Disaster`.

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

Now, add a `change Trees by (1)`{:class="block3variables"} block changing the value to `-1` and finally a `delete this clone`{:class="block3control"} block to remove the tree.

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
