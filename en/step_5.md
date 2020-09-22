## Human deforestation

There are many reasons why humans chop down trees. The wood might be needed for making furniture, buildings or firewood. Alternatively, the land used by the forest might be needed for growing crops, grazing cattle or adding buildings.

--- task ---

When this sprite is click ask how many trees are needed.

```blocks3
when this sprite clicked
ask (How many trees do you need?) and wait
```

--- /task ---

--- task ---

Create a new variable called trees needed.

Set the answer to trees needed.

```blocks3
when this sprite clicked
ask (How many trees do you need?) and wait
+ set [trees needed v] to (answer)
```

--- /task ---

--- task ---

Create a new variable called trees felled set this to 0 in the beginning.

```blocks3
when this sprite clicked
+ set [trees felled v] to (0)
ask (How many trees do you need?) and wait
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
ask (How many trees do you need?) and wait
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
ask [How many trees do you need?] and wait
set [trees needed v] to (answer)
+ repeat until {(trees felled) = (trees needed)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
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
ask [How many trees do you need?] and wait
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
ask [How many trees do you need?] and wait
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
