## Monitor tree levels

Add code to monitor the number of trees, and add messages to say if the tree area is healthy or too small.

<div border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;
color: #0faeb0>
Trees are extremely important to our quality of life on land. From trees, people get fruits to eat, oils for healthy living, and shelter from the weather. Trees absorb carbon dioxide and help to reduce the rate of CO2 emitted across the globe. They are also home to many different species of animals. Trees help protect our planet! 
</div>

Set the tree management level to zero when the simulation starts.

--- task ---

Click on the **Maya** sprite. You'll see a couple of blocks are already in the Code area. These tell Maya to start the simulation with some text for the users. Add a `set tree management to 0`{:class="block3variables"} block.

![image of the Maya sprite](images/maya-sprite.png)

```blocks3
when flag clicked
+ set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
```

--- /task ---

Add code to the simulation so that the **Maya** sprite says when all the trees have gone.

--- task ---

Add a `forever`{:class="block3control"} block to the end of the script.

![image of the Maya sprite](images/maya-sprite.png)
```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
+forever
end
```

--- /task ---

--- task ---

Inside the `forever`{:class="block3control"} block, insert an `if ... then`{:class="block3control"} block with the condition `mature trees`{:class="block3variables"} `=`{:class="block3operators"} `0`.

![image of the Maya sprite](images/maya-sprite.png)
```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
+if {(mature trees) = [0]} then
end
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add a `say for 2 seconds`{:class="block3looks"} block and type: `Our planet needs more trees.`

![image of the Maya sprite](images/maya-sprite.png)
```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
if {(mature trees) = [0]} then
+say [Our planet needs more trees.] for (2) seconds
end
end
```

![image of trees gone message](images/trees-gone-message.png)

--- /task ---

Scientists use their observations to give warnings if CO2 levels are looking dangerous. Add an alert so that the **Maya** sprite warns if there are not enough trees.

Set up a message to appear when the number of mature trees left is greater than `0` and less than `10`.

--- task ---

Add an `if ... then`{:class="block3control"} block inside your `forever`{:class="block3control"} block.

![image of the Maya sprite](images/maya-sprite.png)
```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
if {(mature trees) = [0]} then
say [Our planet needs more trees.] for (2) seconds
end
+if {<>} then
end
end
```

--- /task ---

--- task ---

Add some operators for your calculation. First add a `and`{:class="block3operators"} block, then a `greater than`{:class="block3operators"} block, and a `less than`{:class="block3operators"} block. Set up the condition: `mature trees`{:class="block3variables"} `greater than`{:class="block3operators"} `0` `and`{:class="block3operators"} `mature trees`{:class="block3variables"} `less than`{:class="block3operators"} `10`.

![image of the Maya sprite](images/maya-sprite.png)
```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
if {(mature trees) = [0]} then
say [Our planet needs more trees.] for (2) seconds
end
if {{(mature trees)>[0]} and {(mature trees)<[10]}} then
end
end
```

--- /task ---

--- task ---

Inside the `if ... then`{:class="block3control"} block, add a `say`{:class="block3looks"} block and type: `Global warming is at dangerous levels.` `for 2 seconds`{:class="block3looks"}.

![image of the Maya sprite](images/maya-sprite.png)
```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
if {(mature trees) = [0]} then
say [Our planet needs more trees.] for (2) seconds
end
if {{(mature trees)>[0]} and {(mature trees)<[10]}} then
+say [Global warming is at dangerous levels.] for (2) seconds
end
end
```

--- /task ---

Add another observation message.

--- task ---

Right-click on the last `if ... then`{:class="block3control"} block, and choose **Duplicate** from the menu. 

Insert your duplicated blocks below the last `if ... then`{:class="block3control"} block, and change the values from `0` and `10` to `50` and `60`. Think of a different message to display in the `say`{:class="block3looks"} block:

![image of the Maya sprite](images/maya-sprite.png)

```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
if {(mature trees) = [0]} then
say [Our planet needs more trees.] for (2) seconds
end
if {{(mature trees)>[0]} and {(mature trees)<[10]}} then
say [Global warming is at dangerous levels.] for (2) seconds
end
+ if {{(mature trees)>[50]} and {(mature trees)<[60]}} then
say [Animals have many habitats.] for (2) seconds
end
end
```

--- /task ---

--- task ---

Test your simulation. When the number of trees gets to the range of your `if ... then`{:class="block3control"} blocks, the **Maya** sprite will say an observational message.

--- /task ---

--- save ---
