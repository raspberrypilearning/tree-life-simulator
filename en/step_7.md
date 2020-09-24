## Natural deforestation

Deforestation can happen when natural disasters such as drought, forest fire and tornados devastate an area of land. This can be particularly deadly as, in the wide area  affected, entire species can disappear with the destruction of their habitats.

Simulate the impact of natural disasters randomly moving through the forest.

--- task ---

At the start of the simulation the **Natural Disaster** sprite will hide. Click on the **Natural Disaster** sprite then in the Code area add a `when flag clicked`{:class="block3events"} block followed by a `hide`{:class="block3looks"} block.

![image of the Natural Disaster sprite](images/natural-disaster-sprite.png)

```blocks3
when flag clicked
hide
```

--- /task ---

The **Natural Disaster** sprite will move from the top to the bottom of the screen.

--- task ---

Add a `forever`{:class="block3control"} block to the end of your code. Within it add a `go to x:0 y:0`{:class="block3motion"} block changing the y: value to `200`. Add a `show`{:class="block3looks"} block followed by a `glide 1 secs to x:0 y:0`{:class="block3motion"} changing the seconds value to `3` and the y: value to `-200`.

![image of the Natural Disaster sprite](images/natural-disaster-sprite.png)


```blocks3
when flag clicked
hide
+ forever
go to x:(0) y:(200)
show
glide (3) secs to x:(0) y:(-200)
+ end
```

--- /task ---

--- task ---

Click on the Comstumes tab. The **Natural Disaster** sprite has 3 costumes (Drought, Forest Fire and Tornado) as forests can be hit by many types of natural disaster. Click back to the Code tab and add a `hide`{:class="block3looks"} block when it reaches the bottom of the screen followed by a `next costume`{:class="block3looks"} block so that the simulation has multiple disaster types.

![image of the Natural Disaster sprite](images/natural-disaster-sprite.png)


```blocks3
when flag clicked
hide
forever
go to x:(0) y:(200)
show
glide (3) secs to x:(0) y:(-200)
+ hide
+ next costume
end
```

--- /task ---

--- task ---

Test your project. The **Natural Disaster** sprite will move from top to bottom changing costume each time.

--- /task ---

Scientists can sometimes predict when natural disasters will occur but their timing is not as consistent as in your simulation. Add some randomness to the **Natural Disaster** sprite.

--- task ---

To create random timing add a `wait 1 seconds`{:class="block3control"} block to the top of your forever loop. Drag a `pick random`{:class="block3operators"} operator into the `wait`{:class="block3control"} block and change the values to `10` and `20.`

![image of the Natural Disaster sprite](images/natural-disaster-sprite.png)


```blocks3
when flag clicked
hide
forever
+ wait (pick random (10) to (20)) seconds
go to x:(0) y:(200)
show
glide (3) secs to x:(0) y:(-200)
hide
next costume
end
```

--- /task ---

--- task ---

You can also add randomness to the movement of the **Natural Disaster** sprite. Drag a `pick random`{:class="block3operator"} operator into the x: coordinates of both the `go to`{:class="block3motion"} block and the `glide`{:class="block3motion"} block. Change the values in each to `-200` and `200`.

![image of the Natural Disaster sprite](images/natural-disaster-sprite.png)


```blocks3
when flag clicked
hide
forever
wait (pick random (10) to (20)) seconds
+ go to x:(pick random (-200) to (200)) y:(200)
show
+ glide (3) secs to x:(pick random (-200) to (200)) y:(-200)
hide
next costume
end
```

--- /task ---

--- task ---

Test your project again. Your **Natural Disaster** sprite will now wait between 10 and 20 seconds before falling from a random position to another random position. It will also change costume each time.

--- /task ---
