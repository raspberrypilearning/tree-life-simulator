## Human deforestation

There are many reasons why humans chop down trees. The wood might be needed for making furniture, constructing buildings or firewood. Alternatively, the land used by the forest might be needed for growing crops, grazing cattle or buildings.

In this step you will code the **Tree Feller** to get the amount of trees needed and move through the forest causing human deforestation.

Code the **Tree Feller** to ask how many trees are needed each time it is clicked.

--- task ---

Click on the **Tree Feller** sprite and start a new script with a `when this sprite clicked`{:class="block3events"} block. Add an `ask (What is your name?) and wait`{:class="block3sensing"} block changing the text to ask `How many trees are needed?`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
```

--- /task ---

We need a variable to hold the input from asking the question `How many trees are needed?`.

--- task ---

Create a new variable and call this variable `trees needed`{:class="block3variables"}.

--- /task ---

--- task ---

Store the answer to you question in the trees needed variable by adding a `set trees needed to 0`{:class="block3variables"} block and dragging an `answer`{:class="block3sensing"} block into where it says `0`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
+ set [trees needed v] to (answer)
```

--- /task ---

We need another variable to keep a count of trees felled so far so that the **Tree Feller** sprite knows when it has collected enough.

--- task ---

Create another new variable and call it `trees felled`{:class="block3variables"}.

--- /task ---

 We need to reset the number of trees felled every time the **Tree Feller** sprite is clicked so it clears the variable ready for a new request.

--- task ---

Insert a `set trees felled to 0`{:class="block3variables"} block

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
+ set [trees felled v] to (0)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
```

--- /task ---

The stage is looking crowded with so many variables. We need to hide the ones that don't show the health of the forest and position them so they appear in better places in your simulation.

--- task ---

Go to the Variables menu and untick the `trees felled`{:class="block3variables"} and `trees needed`{:class="block3variables"} variables.

Drag the forest health slider variable and trees counter variable to the bottom corners of the stage.

![image of the stage with variables](images/tstage-with-variables.png)

--- /task ---

Set the starting position for the **Tree Feller** sprite each time it is clicked.

--- task ---

Insert a `set rotation style left-right`{:class="block3motion"} block so that the **Tree Feller** sprite does not tip upside-down. Get the **Tree Feller** sprite start at the top left corner by adding a `go to x:0 y:0`{:class="block3motion"} block changing the values to `-180` and `150`. Get the sprite to `point in direction 90`{:class="block3motion"}.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
set [trees felled v] to (0)
+ set rotation style [left-right v]
+ go to x: (-180) y: (150)
+ point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
```

--- /task ---

The **Tree Feller** sprite will move through the forest from left-right and back again until it has felled enough trees. We need an operator so the **Tree Feller** knows it has collected enough trees when the number of trees felled equals the number of trees needed.

--- task ---

Add a `repeat until`{:class="block3control"} block and drag an equals `=`{:class="block3operators"} operator inside. Add the condition `trees felled`{:class="block3variables"} `=`{:class="block3operators"} `trees needed`{:class="block3variables"}.

Within the loop add a `move 10 steps`{:class="block3motion"} block changing the value to `4`.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-180) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
+ repeat until {(trees felled) = (trees needed)}
move (4) steps
end
```

--- /task ---

At the moment the **Tree Feller** sprite will only move across the top of the stage. Get it to sense if it is touching the edge of the stage so that it knows to change direction.

--- task ---

Add an `if...then`{:class="block3control"} block with a `touching edge`{:class="block3sensing"} condition. Inside your `if`{:class="block3control"} loop add two `Motion`{:class="block3motion"} blocks:  `turn right by 180 degrees`{:class="block3motion"} and `change y by -40`{:class="block3motion"}.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-180) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
repeat until {(trees felled) = (trees needed)}
move (4) steps
+ if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
+ end
```

--- /task ---

When the **Tree Feller** sprite gets to a tree it needs to wait then add that tree to it's `trees felled`{:class="block3variables"} counter.

--- task ---

Add another `if...then`{:class="block3control"} block with a `touching Tree`{:class="block3sensing"} condition. Inside your `if...then`{:class="block3control"} loop add a `wait 0.5 seconds`{:class="block3control"} block and a `change trees felled by 1`{:class="block3variables"} block.

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-180) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
repeat until {(trees felled) = (trees needed)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
+ if {touching [Tree v]?} then
wait (0.5) seconds
change [trees felled v] by (1)
+ end
end
```

--- /task ---

We'd like to know when the **Tree Feller** sprite has felled enough trees. Get the **Tree Feller** sprite to announce it has finished and say how many trees it has collected.

--- task ---

Add a `Looks`{:class="block3looks"} block to the end of your code so that the **Tree Feller** sprite will `say`{:class="block3looks"}**how many trees it has felled**`for 2 seconds`{:class="block3looks"}. to say **how many trees it has felled**  `join`{:class="block3operators"} operator to link the `trees felled`{:class="block3variables"} variable and the text " trees felled".

![image of the Tree Feller sprite](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
set [trees felled v] to (0)
set rotation style [left-right v]
go to x: (-180) y: (150)
point in direction (90)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
repeat until {(trees felled) = (trees needed)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {touching [Tree v]?} then
wait (0.5) seconds
change [trees felled v] by (1)
end
end
+ say {join(trees felled)[ trees felled]} for (2) seconds
```

--- /task ---

--- task ---

Test your simulation. Click on the **Tree Feller** sprite a few times to request different amounts of wood.

![image of the Tree Feller announcing trees felled](images/feller-trees-felled.png)

--- /task ---
