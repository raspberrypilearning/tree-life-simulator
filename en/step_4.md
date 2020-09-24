## Count the trees

Scientists monitor trees and wildlife. They record the cover (size), variety and health of the forests. By doing this they can see the true impact of deforestation. Observations are taken from planes and satellites in the air as well as sensors and people on the ground. Using their findings people can see where extra measures are needed to protect trees for example the addition of fences around the forest to allow trees to thrive or employing more firefighters to help find and stop fires. 

In this step we'll monitor the trees in your simulation by using variables to store the number of trees and reflect changes.

--- task ---

Create a new variable to store the number of trees. Call this variable `trees`{:class="block3variables"}.

--- /task ---

Reset the number of trees when the simulation starts to `0`.

--- task ---

Underneath the `when flag clicked`{:class="block3events"} block set the `trees`{:class="block3variables"} variable to `0`.

![image of the Tree sprite](images/tree-sprite.png)

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

 Make sure your counter records how many trees are being planted as the simulation is running.

--- task ---

Find your `when I start as a clone`{:class="block3control"} script and add a `change trees by 1`{:class="block3variables"} block at the end.

![image of the Tree sprite](images/tree-sprite.png)

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

We can now count our new trees however not all those trees will survive. The survival rate for new trees is estimated to be 80% meaning that 2 trees out of every 10 planted will die of natural causes before they are fully-grown. We aren't going to reflect this in our simulation but its important to know that not all new trees survive naturally.

Trees can also die or be chopped down through human and natural deforestation. We'll show this by reducing our count of trees if a tree has been touched by the **Natural Disaster** sprite or the **Tree feller** sprite.

--- task ---

Add a `wait until`{:class="block3control"} block to the end of your code. Inside this block use an `or`{:class="block3operators"} operator. Add two more blocks inside the `or`{:class="block3operators"} operator to sense if the **Tree** sprite is `touching Natural Disaster`{:class="block3sensing"} or `touching Tree Feller`{:class="block3sensing"}.

![image of the Tree sprite](images/tree-sprite.png)

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

When a tree has been touched make sure the tree counter decreases and the tree clone is removed.

--- task ---

Add a `change Trees by 1`{:class="block3variables"} block changing the value to `-1` and finally a `delete this clone`{:class="block3control"} block to remove the tree.

![image of the Tree sprite](images/tree-sprite.png)

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
