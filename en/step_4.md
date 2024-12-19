## Count the trees
<div border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;
color: #0faeb0>
Scientists monitor trees and wildlife. They record the cover (size), variety, and health of the trees and surrounding areas. By doing this, they can see the true impact of deforestation. Observations can be taken from planes and satellites in the air, as well as sensors and people on the ground. People can use their findings to see where extra measures are needed to protect trees. For example, the construction of fences around a forest to allow trees to thrive, or the employment of more firefighters to help find and stop fires.
</div>

Monitor the trees in your simulation through a variable that stores the number of trees and reflects changes to the environment. 

--- task ---

Create a new `variable`{:class="block3variables"} to store the number of full-grown trees. Call this variable `mature trees`{:class="block3variables"}.

--- /task ---

Reset the number of trees when the simulation starts to `0`.

--- task ---

Underneath the `when green flag clicked`{:class="block3events"} block, set the `mature trees`{:class="block3variables"} variable to `0`:

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when flag clicked
+ set (mature trees) to (0)
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
reset timer
repeat until {{(timer)>((6)-(tree management))}}
wait (1) seconds
end
create clone of [myself v]
end
```

--- /task ---

Make sure your counter records how many trees are created while the simulation runs.

--- task ---

Find your `when I start as a clone`{:class="block3control"} script and add a `change mature trees by 1`{:class="block3variables"} block at the end:

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
+ change (mature trees) by (1)
```

--- /task ---

Now you can count your new trees, however not all those trees will survive. 

<div border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;
color: #0faeb0>
The survival rate for new trees is estimated to be 80 percent, which means that 2 trees out of every 10 planted will die of natural causes before they are full grown. 
</div>

### Human Deforestation
Mature trees can also be chopped down through human deforestation. To show this, reduce the count of mature trees if a tree has been touched by the **Tree Feller** sprite. 

--- task ---

Add a `wait until`{:class="block3control"} block to the end of your code.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
change (mature trees) by (1)
+wait until {<>}
```

--- /task ---

--- task ---

Inside the `wait until`{:class="block3control"} block, add a `touching Tree Feller`{:class="block3sensing"} block.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
change (mature trees) by (1)
+wait until {touching [Tree Feller v]?}
```

--- /task ---

--- task ---

Add a `change mature trees by 1`{:class="block3variables"} block below the `wait until`{:class="block3control"} block, and change the value to `-1`.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
change (mature trees) by (1)
wait until {touching [Tree Feller v]?}
+change (mature trees) by (-1)
```

--- /task ---

--- task ---

Add a `delete this clone`{:class="block3control"} block below the `change mature trees by 1`{:class="block3variables"} block to remove the tree.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
change (mature trees) by (1)
wait until {touching [Tree Feller v]?}
change (mature trees) by (-1)
+delete this clone
```

--- /task ---

### Natural Disaster
Trees can also die from natural deforestation, whether they are mature or still growing. To show this, reduce your count of trees if a tree has been touched by the **Natural Disaster** sprite.

--- task ---

Start a new script with a `when I start as a clone`{:class="block3control"} block.

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when I start as a clone
```

--- /task ---

--- task ---

Add a `wait until`{:class="block3control"} block to the end of your code. Inside this block, add a `touching Natural Disaster`{:class="block3sensing"} block.

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when I start as a clone
+wait until {touching [Natural Disaster v]?}
```

--- /task ---

--- task ---

Add an `if ... then`{:class="block3control"} block below the `wait until`{:class="block3control"} block, with the condition `size`{:class="block3looks"} `=`{:class="block3operators"} `20`.

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when I start as a clone
wait until {touching [Natural Disaster v]?}
+if {(size) = (20)} then
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add a `change mature trees by 1`{:class="block3variables"} block, and change the value to `-1`.

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when I start as a clone
wait until {touching [Natural Disaster v]?}
if {(size) = (20)} then
+change (mature trees) by (-1)
end
```

--- /task ---

--- task ---

Add a `delete this clone`{:class="block3control"} block below the `if ... then`{:class="block3control"} block to remove the tree.

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when I start as a clone
wait until {touching [Natural Disaster v]?}
if {(size) = (20)} then
change (mature trees) by (-1)
end
+delete this clone
```

--- /task ---

--- save ---
