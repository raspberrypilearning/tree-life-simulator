## Natural deforestation

Simulate the impact of natural disasters that randomly move through the forest. Hide the **Natural Disaster** sprite at the start of the simulation.

--- task ---

Click on the **Natural Disaster** sprite, then in the Code area add this script:

![image of the Natural Disaster sprite](images/natural-disaster-sprite.png)
```blocks3
when flag clicked
hide
forever
go to x:(0) y:(200)
show
+glide (3) secs to x:(0) y:(-200)
end
```

--- /task ---

The **Natural Disaster** sprite has three costumes: **Drought**, **Forest Fire**, and **Tornado**, as trees can be hit by many types of natural disaster. Add code so that the simulation has multiple disaster types.

--- task ---

 Click on the **Costumes** tab to view the costumes. Click back to the **Code** tab and add a `hide`{:class="block3looks"} block when it reaches the bottom of the screen, followed by a `next costume`{:class="block3looks"} block:

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

Test your project. The **Natural Disaster** sprite now moves from top to bottom, and changes costume each time.

![image of the Natural Disaster on stage](images/disaster-on-stage.png)

--- /task ---

Scientists can sometimes predict when natural disasters will occur, though this can be difficult because their timing isn't always clear, unlike in the simulation. Now, add random timing to the **Natural Disaster** sprite to make the sprite's appearance unpredictable like in real life.

--- task ---

To create random timing add a `wait 1 seconds`{:class="block3control"} block to the top of your `forever`{:class="block3control"} block. Drag a `pick random`{:class="block3operators"} operator into the `wait`{:class="block3control"} block, and change the values to `10` and `20`:

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

Add randomness to the movement of the **Natural Disaster** sprite.

--- task ---

Drag a `pick random`{:class="block3operators"} operator into the `x:`{:class="block3motion"} coordinates of both the `go to`{:class="block3motion"} block and the `glide`{:class="block3motion"} block. Change the values in each to `-200` and `200`:

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

Test your project again. Your **Natural Disaster** sprite should now wait between 10 and 20 seconds before it falls from a random position to another random position. It also changes costume each time and removes any trees it touches.

--- /task ---

--- save ---
