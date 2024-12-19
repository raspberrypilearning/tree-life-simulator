## Tree management

The rate at which new trees grow depends on a number of factors, such as climate conditions, soil quality, disease, sunlight, and water. Add a slider to demonstrate how managing these conditions can impact the number of trees in the area. 

The growing speed will be held in a `variable`{:class="block3variables"} called `tree management`{:class="block3variables"}.

--- task ---

To create a new variable, click on the `Variables`{:class="block3variables"} blocks menu.

Then click on the **Make a Variable** button.

You can give your `variable`{:class="block3variables"} a name. Call it `tree management`.
![A user interface pop-up titled "New Variable" with a purple header. Below, a text field labeled "New variable name:" contains the typed text "tree management." Two radio button options are shown: "For all sprites" (selected) and "For this sprite only." At the bottom right are two buttons, "Cancel" and "OK," with the "OK" button highlighted in purple.](images/make_variable.png)

--- /task ---

Your new `variable`{:class="block3variables"} is visible on the Stage. Next, create a slider to control the speed in your simulation.

--- task ---

On the Stage, right-click on the `tree management`{:class="block3variables"} variable, and a menu will appear.

Select **slider** in the menu.

![A graphical interface on a green background featuring a label "tree management" with a value of "0" displayed in an orange box beside it. To the right, a drop-down menu is open with options: "normal readout," "large readout," "slider" (highlighted in purple), and "hide." A small yellow forklift icon is partially visible next to the "tree management" label.](images/slider_menu.png)

--- /task ---

At the moment, the `tree management`{:class="block3variables"} range is too wide.

--- task ---

On the Stage, right-click on the **tree management** slider and select **change slider range**.

![A graphical interface on a green background featuring a label "tree management" with a value of "0" displayed in an orange box beside it. Below the label is a slider bar with a blue knob set to the left. To the right, a drop-down menu is open with options: "normal readout," "large readout," "slider," "change slider range" (highlighted in purple), and "hide." A portion of a yellow forklift icon is visible next to the "tree management" label.](images/slider_range.png)

Change the range to between `0` and `5`.
![A pop-up interface titled "Change slider range" with a purple header. It contains two labeled input fields: "Minimum value" with the default value of "0" and "Maximum value" with the value "5" in a purple-bordered box. At the bottom, there are two buttons: "Cancel" on the left and "OK" highlighted in purple on the right.](images/slider_range_change.png)

--- /task ---

In the simulation, the **tree management** slider controls the speed that new trees grow. If you move the slider to the right, it speeds up the growth; if you move it to the left, it slows down the growth. 

Add a set of blocks to make sure that the speed that new trees grow is in reaction to a change in the **tree management** slider.  

--- task ---

Go to the `Sensing`{:class="block3sensing"} blocks menu, and click on the checkbox next to the `timer`{:class="block3sensing"} block to show the timer on the Stage. 

![A graphical interface showing a blue checkbox with a checkmark, followed by an oval button labeled "timer." Below, a puzzle-piece-shaped blue block is labeled "reset timer." The elements are arranged vertically against a light background.](images/timer_tick.png)

Click on the green flag and you'll notice the timer starts to count up immediately. Click on the checkbox again to hide the timer from view. 

--- /task ---

Reset the timer to zero each time the flag is clicked.

--- task ---

Insert a `reset timer`{:class="block3sensing"} block into your `when green flag clicked`{:class="block3events"} script for the **Tree** sprite, so that the timer resets each time a new tree is cloned: 

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
+reset timer
create clone of [myself v]
end
```

--- /task ---

Create a quick response to the slider so that the user immediately sees the impact of their interaction. Set up a loop that checks the **tree management** slider value frequently and adjusts the speed before cloning another tree.

--- task ---

Insert a `repeat until`{:class="block3control"} block with the condition `timer`{:class="block3sensing"} `>`{:class="block3operators"} `6` `-`{:class="block3operators"} `tree management`{:class="block3variables"}. Place it within the `forever`{:class="block3control"} loop.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
reset timer
+repeat until {{(timer)>((6)-(tree management))}}
end
create clone of [myself v]
end
```

--- /task ---

--- task ---

Within the `repeat until`{:class="block3control"} block, add a `wait 1 seconds`{:class="block3control"} block.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
reset timer
repeat until {{(timer)>((6)-(tree management))}}
+wait (1) seconds
end
create clone of [myself v]
end
```

--- /task ---

--- task ---

Test your simulation again. The **tree management** slider should control the speed that new trees grow.

![image of a busy forest](images/busy-forest.png)

--- /task ---

--- save ---
