## Monitor C02 levels

Trees are extremely important to our quality of life on land. From trees people get fruits to eat, oils for healthy living and shelter from the weather. They are also home to many different species of animals.

Trees also absorb carbon dioxide and help to reduce the rate of CO2 emitted across the globe. Trees help protect our planet! Add a variable to your simulation to calculate the current amount of CO2 that would be absorbed by your fully-grown trees each year.

--- task ---

Create a new variable to store the amount of CO2 absorbed by fully-grown trees. Call this variable `CO2 absorbed`{:class="block3variables"}.

--- /task ---

--- task ---

Click on the **Maya** sprite. You'll see a couple of blocks are already in the Code area. These tell Maya to start the simulation with some text for the users. Add a `set CO2 absorbed to 0`{:class="block3variables"} block when the simulation begins.

```blocks3
when flag clicked
+ set [CO2 absorbed v] to (0)
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
```

--- /task ---

Maya is a Scientist and knows that a typical hardwood tree can absorb as much as 48 pounds of carbon dioxide per year. Using this she can calculate the expected amount of CO2 absorbed by the forest each year.

--- task ---

Add a `forever`{:class="block3control"} block to the end of your code so that the calculation runs continuously throughout the simulation. Inside the `forever`{:class="block3control"} loop add a `set CO2 absorbed to 0`{:class="block3variables"} block. Replace the `0` with a `multiply`{:class="block3operators"} operator to set up the calculation. In the first circle add a `trees`{:class="block3variables"} block and in the second circle type `48`

```blocks3
when flag clicked
set [CO2 absorbed v] to (0)
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
+ forever
set [CO2 absorbed v] to {(trees)*(48)}
end
```

--- /task ---

--- task ---

Test your simulation. As fully-grown trees appear the CO2 absorbed will increase, if deforestation occurs the CO2 absorbed will go down to show the expected impact.

--- /task ---

The simulation will end when the user stops it or when all the trees have gone.

--- task ---

Add an `if...then...else`{:class="block3control"}block to your forever loop inserting your `set [CO2 absorbed v] to`{:class="block3variables"}`trees`{:class="block3variables"}`*`{:class="block3operators"}`48` block into the top `if..then`{:class="block3control"} section.

Drag a `greater than`{:class="operators"} operator into the top of the block, adding `trees`{:class="block3variables"} to the first circle and changing the value `50` to `0` in the second circle.

```blocks3
when flag clicked
set [CO2 absorbed v] to (0)
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
forever
+ if {(trees) > [0]} then
set [CO2 absorbed v] to {(trees)*(48)}
else
end
```

--- /task ---

--- task ---

In the `else`{:class="block3control"} section add a `set [CO2 absorbed v] to 0`{:class="block3variables"} block and a 'say Hello! for 2 seconds'{:class="block3looks"} block changing the value to `The trees have gone! Our planet is in danger`

```blocks3
when flag clicked
set [CO2 absorbed v] to (0)
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
forever
if {(trees) > [0]} then
set [CO2 absorbed v] to {(trees)*(48)}
else
+ set [CO2 absorbed v] to (0)
+ say [The trees have gone! Our planet is in danger] for (2) seconds
end
```

--- /task ---

--- task ---

Task text

--- /task ---

--- task ---

Task text

--- /task ---

--- task ---

Task text

--- /task ---
