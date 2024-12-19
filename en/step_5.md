## Human deforestation

There are many reasons why humans chop down trees. The wood might be needed to create furniture, make buildings, or burn as firewood. Alternatively, the land used by the forest might be needed to grow crops, graze cattle, or construct buildings.

In this step, you will code the **Tree Feller** sprite to get the amount of trees needed, and move through the forest causing human deforestation.

Code the **Tree Feller** sprite to ask how many trees are needed each time it is clicked. 

--- task ---

Click on the **Tree Feller** sprite and start a new script with a `when this sprite clicked`{:class="block3events"} block.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
```

--- /task ---

--- task ---

Add an `ask What is your name? and wait`{:class="block3sensing"} block. Change the text to ask `How many trees are needed? (max 20)`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
+ask [How many trees are needed? (max 20)] and wait
```

--- /task ---

Next, you need a variable to hold the input from asking the question `How many trees are needed? (max 20)`.

--- task ---

Create a new `variable`{:class="block3variables"} and call it `trees needed`.

--- /task ---

Each time someone submits a request for more trees, the **Tree Feller** sprite should add that number to the amount of trees needed. 

--- task ---

To store the answer to your question in the `trees needed`{:class="block3variables"} variable, add a `change trees needed by 1`{:class="block3variables"} block and drag an `answer`{:class="block3sensing"} block into where it says `1`{:class="block3variables"}:

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
+ change [trees needed v] by (answer)
```

--- /task ---

As trees are big and heavy, the maximum number that can be requested should be set to 20. 

--- task ---

Add an `if ... then`{:class="block3control"} block to the end of your code with the condition `trees needed`{:class="block3variables"} `greater than`{:class="block3operators"} `20`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
change [trees needed v] by (answer)
+if {(trees needed) > (20)} then
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add `set trees needed to`{:class="block3variables"} `20`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
+set (trees needed v) to (20)
end
```

--- /task ---

Reset the number of trees needed every time the green flag is clicked to start the simulation, so it clears the variable ready for a new request.

--- task ---

Start a new script with `when green flag clicked`{:class="block3control"} block, and add a `set trees needed to 0`{:class="block3variables"} block:

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when flag clicked
set [trees needed v] to (0)
```

--- /task ---

--- task ---

Run your simulation. Click on the **Tree Feller** sprite and request a number of trees. Enter different numbers to see what happens to the `trees needed`{:class="block3variables"} variable each time.

--- /task ---

When the **Tree Feller** sprite touches a mature tree, the number of trees needed will decrease.

--- task ---

Click on the **Tree** sprite and change the condition of the `wait until`{:class="block3control"} block to be `touching Tree Feller`{:class="block3sensing"} `and`{:class="block3operators"} `trees needed`{:class="block3variables"} `>`{:class="block3operators"} `0`.

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
+wait until {{touching [Tree Feller v]?} and {(trees needed) > (0)}}
change (mature trees) by (-1)
delete this clone
```

--- /task ---

--- task ---

Add `change trees needed by`{:class="block3variables"} `-1` to the script after it `touches Tree Feller`{:class="block3sensing"}.

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
wait until {{touching [Tree Feller v]?} and {(trees needed) > (0)}}
+change (trees needed) by (-1)
change (mature trees) by (-1)
delete this clone
```

--- /task ---

The Stage is looking crowded with so many `variables`{:class="block3variables"}. Position them so they appear in better places in your simulation, and hide the ones that don't show values relating to tree management.

--- task ---

Go to the `Variables`{:class="block3variables"} blocks menu and untick the `trees needed`{:class="block3variables"} variable.

Drag the **tree management** slider variable and **mature trees** counter variable to the bottom corners of the Stage.

![image of the stage with variables](images/stage-with-variables.png)

--- /task ---

Set the starting position for the **Tree Feller** sprite each time the simulation starts.

--- task ---

Click on the **Tree Feller** sprite and in the `when green flag clicked`{:class="block3events"} script, insert a `set rotation style left-right`{:class="block3motion"} block so that the **Tree Feller** sprite does not tip upside down.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when flag clicked
set [trees felled v] to (0)
+set rotation style [left-right v]
```

--- /task ---

--- task ---

Add a `go to x:0 y:0`{:class="block3motion"} block and change the values to `-200` and `150` to position the **Tree Feller** sprite at the top left-hand corner.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when flag clicked
set [trees felled v] to (0)
set rotation style [left-right v]
+go to x: (-200) y: (150)
```

--- /task ---

--- task ---

Add a `point in direction 90`{:class="block3motion"} block to make the **Tree Feller** sprite face right.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when flag clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-200) y: (150)
+point in direction (90)
```

--- /task ---

The **Tree Feller** sprite will move through the forest from left to right and back again, until it has felled enough trees. Use an operator so the **Tree Feller** sprite knows it has collected enough trees when the number of trees needed equals zero.

--- task ---

In the `when this sprite clicked`{:class="block3events"} script, add a `repeat until`{:class="block3control"} block and drag an equals `=`{:class="block3operators"} block inside. Add the condition `trees needed`{:class="block3variables"} `=`{:class="block3operators"} `0`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
+repeat until {(trees needed) = (0)}
end
```

--- /task ---

--- task ---

Within the `repeat until`{:class="block3control"} block, add a `move 10 steps`{:class="block3motion"} block and change the value to `4`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
+move (4) steps
end
```

--- /task ---

--- task ---

Run your simulation. Click on the **Tree Feller** sprite and request a number of trees. Does the **Tree Feller** sprite move through the whole Stage? 

--- /task ---

At the moment, the **Tree Feller** sprite only moves across the top of the Stage. You need to make the sprite sense if it is touching the edge of the Stage, so that it knows to change direction.

--- task ---

Add an `if ... then`{:class="block3control"} block with a `touching edge`{:class="block3sensing"} condition inside the `repeat until`{:class="block3control"} loop.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
+if {touching [edge v]?} then
end
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add a `turn right by`{:class="block3motion"} `180` `degrees`{:class="block3motion"} block.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
+turn right (180) degrees
end
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add a `change y by`{:class="block3motion"} `-40` block.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
+change y by (-40)
end
end
```

--- /task ---

If the **Tree Feller** sprite reaches the bottom of the Stage, it needs to start again from the top.

--- task ---

Add another `if ... then`{:class="block3control"} block with a `y position`{:class="block3motion"} `<`{:class="block3operators"} `-120` condition inside the `repeat until`{:class="block3control"} loop.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
+if {(y position)<(-120)} then
end
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add a `go to x:`{:class="block3motion"} `-200` `y:`{:class="block3motion"} `150` block so that it moves back to the starting position.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)
```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {(y position)<(-120)} then
+go to x: (-200) y: (150)
end
end
```

--- /task ---

Next, you need to find out when the **Tree Feller** sprite has felled enough trees. Get the **Tree Feller** sprite to announce it has finished the requests.

--- task ---

Add a `Looks`{:class="block3looks"} block to the end of your code so that the **Tree Feller** sprite will `say`{:class="block3looks"} `Requests completed.` `for 2 seconds`{:class="block3looks"}:

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees neeed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {(y position)<(-120)} then
go to x: (-200) y: (150)
end
end
+ say [Requests completed.] for (2) seconds
```

--- /task ---

--- task ---

Run your simulation. 

Click on the **Tree Feller** sprite and request a number of trees. Once the **Tree Feller** sprite has collected enough trees, it will tell you it has finished. 

--- /task ---

Once the requests are complete, get the **Tree Feller** sprite to move to the side of the tree area, ready for the next request. 

--- task ---

Add two `Motion`{:class="block3motion"} blocks: a `set x to`{:class="block3motion"} `-200` block and a `point in direction 90`{:class="block3motion"} block.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees neeed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {(y position)<(-120)} then
go to x: (-200) y: (150)
end
end
say [Requests completed.] for (2) seconds
+ set x to (-200)
+ point in direction (90)
```

--- /task ---

--- task ---

Test your simulation. Click on the **Tree Feller** sprite a few times to request different amounts of wood.

![image of the Tree Feller announcing trees felled](images/feller-trees-felled.png)

--- /task ---

--- save ---
