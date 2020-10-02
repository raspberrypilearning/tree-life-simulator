## Count the trees

Scientists monitor trees and wildlife. They record the cover (size), variety and health of the trees and surrounding areas. By doing this they can see the true impact of deforestation. Observations are taken from planes and satellites in the air as well as sensors and people on the ground. Using their findings people can see where extra measures are needed to protect trees for example the addition of fences around a forest to allow trees to thrive or employing more firefighters to help find and stop fires.

In this step we'll monitor the trees in your simulation by using a variable to store the number of trees and reflect changes.

--- task ---

Create a new variable to store the number of fully-grown trees. Call this variable `mature trees`{:class="block3variables"}.

--- /task ---

Reset the number of trees when the simulation starts to `0`.

--- task ---

Underneath the `when flag clicked`{:class="block3events"} block set the `mature trees`{:class="block3variables"} variable to `0`:

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

Make sure your counter records how many trees are being created as the simulation is running.

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

We can now count our new trees however not all those trees will survive. The survival rate for new trees is estimated to be 80% meaning that 2 trees out of every 10 planted will die of natural causes before they are fully-grown. We aren't going to reflect this in our simulation but its important to know that not all new trees survive naturally.

Mature trees can also be chopped down through human deforestation. Show this by reducing the count of mature trees if a tree has been touched by the **Tree feller** sprite. 

--- task ---

Add a `wait until`{:class="block3control"} block to the end of your code and inside this block a `touching Tree Feller`{:class="block3sensing"} block. Add a `change mature trees by 1`{:class="block3variables"} block and change the value to `-1`. Add a `delete this clone`{:class="block3control"} block to remove the tree:

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
+ wait until {touching [Tree feller v]?}
+ change (mature trees) by (-1)
+ delete this clone
```
--- /task ---

Trees can also die from natural deforestation, whether they are mature or still growing. We'll show this by reducing our count of trees if a tree has been touched by the **Natural Disaster** sprite.

--- task ---

Start a new script with a `when I start as a clone`{:class="block3control"} block. Add a `wait until`{:class="block3control"} block to the end of your code and inside this block a `touching Natural Disaster`{:class="block3sensing"} block. Add an `if...then`{:class="block3control"} block with the condition `size`{:class="block3looks"} `=`{:class="block3operators"} `20`. 

Inside the `if...then`{:class="block3control"} block add a `change mature trees by 1`{:class="block3variables"} block so that the count of mature trees is only decreased if the tree was fully-grown. Add a `delete this clone`{:class="block3control"} block to remove the tree:

```blocks3
when I start as a clone
wait until {touching [Natural Disaster v]?}
if {(size) = (20)} then
change (mature trees) by (-1)
end
delete this clone
```

--- /task ---
