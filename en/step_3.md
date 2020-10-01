## Tree management

In the simulation we want to see the impact of new trees sprouting at a faster or slower speed. The speed at which new trees grow depends on a number of factors such as climate conditions, soil quality, disease, sunlight and water. In this step you'll add a slider to demonstrate how managing these conditions impacts the growth of the number of trees in the area. 

The growing speed will be held in a variable called `tree management`{:class="block3variables"}.

--- task ---

Create a new variable by clicking on the `Variables`{:class="block3variables"} blocks menu.

Then click on the **Make a Variable** button.

You can give your variable a name. Call this variable `tree management`.

--- /task ---

Your new variable is visible on the stage. Create a slider to control the speed in your simulation.

--- task ---

On the stage, right-click on the tree management variable, and a menu will appear.

Select **slider** in the menu.

--- /task ---

At the moment the tree management range is too wide.

--- task ---

On the stage, right-click on the tree management slider and select **change slider range**.

Change the range to between `0` and `5`.

--- /task ---

In our simulation the **tree management** slider will control the speed the trees grow. Moving the slider to the right will speed up the growth whilst moving to the left will slow down the growth. When the slider is at the right the simulation will wait 1 seconds to plant a tree and when it is at the left it will wait 6 seconds to plant a tree.

 ![image of the slider maths](images/slider-maths.png)

This means if `tree management`{:class="block3variables"} equals `4` the wait time will be 2 seconds but if `tree management`{:class="block3variables"} equals `1` the wait time will be slower at 5 seconds. 

We need to add a set of blocks to make sure that the **tree management** slider reacts quickly to the users.  

--- task ---

In this task you'll see how the `timer`{:class="block3sensing"} block works. Go to the `Sensing`{:class="block3sensing"} menu and click on the tick next to the `timer`{:class="block3sensing"} block to show the timer on the stage. 

Click on the green flag to start your simulation. You'll notice the timer starts to count up immediately. Click on the tick again to hide the timer from view. 

--- /task ---

--- task ---

Insert a `reset timer`{:class="block3sensing"} block into your `when flag clicked`{:class="block3events"} script so that the timer resets each time a new tree is cloned. Below it add a `repeat until`{:class="block3control"} block with the condition `timer`{:class="block3sensing"} `>`{:class="block3operators"} `6` `-`{:class="block3operators"} `tree management`{:class="block3variables"} this will create a quick response to the slider as it checks  frequently and adjusts before cloning another tree. Within the `repeat until`{:class="block3control"} block add a `wait 1 seconds`{:class="block3control"} block:

![image of the Tree sprite](images/tree-sprite.png)

```blocks3
when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
+ reset timer
+ repeat until {{(timer)>((6)-(tree management))}}
wait (1) seconds
end
create clone of [myself v]
end
```
--- /task ---

--- task ---

Test your simulation again. The **tree management** slider will control the speed the forest grows.

![image of a busy forest](images/busy-forest.png)

--- /task ---
