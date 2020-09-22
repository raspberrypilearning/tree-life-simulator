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

Create another new variable and call it `trees felled`{:class="block3variables"}. Add a `set trees felled to 0`{:class="block3variables"} block to reset the number everytime the **Tree Feller** sprite is clicked.

```blocks3
when this sprite clicked
+ set [trees felled v] to (0)
ask [How many trees are needed?] and wait
set [trees needed v] to (answer)
```

--- /task ---

--- task ---

Set the digger up to fell the forest

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

Move the feller until trees felled = trees needed across the screen and back.

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

Move down and back.

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

--- task ---

If the feller touches a tree it should pause to chop it down and change trees felled by 1.

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

--- task ---

Once we have enough trees say how many.

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

Test.

--- /task ---
