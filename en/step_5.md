## Human deforestation

There are many reasons why humans chop down trees. The wood might be needed for making furniture, buildings or firewood. Alternatively, the land used by the forest might be needed for growing crops, grazing cattle or adding buildings.

Code the tree feller to ask how many trees are needed each time it is clicked.

--- task ---

Click on the **Tree Feller** sprite and drag a `When this sprite is clicked`{:class="block3events"} block to the Code area. Add an `ask (What is your name?) and wait`{:class="block3sensing"} block changing the value to ask `how many trees are needed?`.

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
```

--- /task ---

--- task ---

Create a new variable to store the number of trees needed. Call this variable `trees needed`{:class="block3variables"}.

Store the answer to you question in the trees needed variable by adding a `set trees needed to 0`{:class="block3variables"} block and dragging an `answer`{:class="block3sensing"} block into the circle.

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
+ set [trees needed v] to (answer)
```

--- /task ---

--- task ---

Create another new variable and call it `trees felled`{:class="block3variables"}. Add a `set trees felled to 0`{:class="block3variables"} block to reset the number every time the **Tree Feller** sprite is clicked.

```blocks3
when this sprite clicked
+ set [trees felled v] to (0)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
```

--- /task ---

The Tree Feller will move through the forest from left-right and back again until it has felled enough trees.

--- task ---

Add blocks to set the starting position for the digger each time it is clicked.

Insert a `set rotation style left-right`{:class="block3motion"} block so that the **Tree Feller** sprite does not tip upside-down at any point. Next add a `go to x:0 y:0`{:class="block3motion"} block changing the values to `-200` and `150` to make the **Tree Feller** sprite start in the top left corner of the stage. Finally, add a `point in direction 90`{:class="block3motion"} block.

```blocks3
when this sprite clicked
set [trees felled v] to (0)
+ set rotation style [left-right v]
+ go to x: (-200) y: (150)
+ point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
```

--- /task ---

--- task ---

Add a `repeat until`{:class="block3control"} loop and drag an `equals`{:class="block3operators"} operator into the block. In the first circle add a `trees felled`{:class="block3variables"} block and in the second circle a `trees needed`{:class="block3variables"} block.

Within the `repeat`{:class="block3control"} block add a `move 10 steps`{:class="block3motion"} block changing the value to `4` so that the **Tree Feller** sprite repeatedly moves 4 steps until it has collected enough trees.

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-200) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
+ repeat until {(trees felled) = (trees needed)}
move (4) steps
end
+ end
```

--- /task ---

--- task ---

At the moment the **Tree Feller** sprite will only move across the top of the stage. Add an `if...then`{:class="block3control"} block within your `repeat until`{:class="block3control"} loop. Drag a `touching mouse-pointer`{:class="block3sensing"} block selecting `edge` from the dropdown.

Inside the `if`{:class="block3control"} block add a `turn right by 15 degrees`{:class="block3motion"} block changing the value to `180` and a `change y by 10`{:class="block3motion"} block changing the value to `-40` so that the **Tree Feller** sprite turns round and moves down the Stage once it's reached the edge.

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-200) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
repeat until {(trees felled) = (trees needed)}
move (4) steps
+ if {touching [edge v]?} then
+ turn right (180) degrees
+ change y by (-40)
end
+ end
```

--- /task ---

Cutting down trees takes time even for a big forestry machine.

--- task ---

Add an `if...then`{:class="block3control"} block and drag across a `touching mouse-pointer`{:class="block3sensing"} block selecting `edge` from the dropdown. Inside your `if...then`{:class="block3control"} block add a `change trees felled by 1`{:class="block3variables"} block and a 'wait 1 seconds' block changing the value to `0.5` to create a small delay when the **Tree Feller** sprite comes across a tree.

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-200) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
repeat until {(trees felled) = (trees needed)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
+ if {touching [tree v]?} then
change [trees felled v] by (1)
wait (0.5) seconds
+ end
end
```

--- /task ---

Once the **Tree Feller** sprite has felled enough trees announce how many have been collected.

--- task ---

Add a `say Hello! for 2 seconds`{:class="block3looks"} block to the end of your code. Replace the `Hello!` message by dragging a `join`{:class="block3operators"} block inside. In the first circle drag a `trees felled`{:class="block3variables"} block and in the second circle type ' trees felled'.

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-200) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
repeat until {(trees felled) = (trees needed)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {touching [tree v]?} then
change [trees felled v] by (1)
wait (0.5) seconds
end
end
+ say {join(trees felled)[ trees felled]} for (2) seconds
```

--- /task ---

--- task ---

Test your simulation. Click on the **Tree Feller** sprite a few times to request different amounts of wood. 

--- /task ---
