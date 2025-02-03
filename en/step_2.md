## Grow some trees

Add code to create an area of trees with a variety of different tree types.

--- task ---

Open the [starter project](http://rpf.io/tree-life-simulator-on){:target="_blank"} in Scratch.

You should see a green grassland background.

![starter project](images/starter_project.png)

--- /task ---

### Make a clone
In Scratch, you can make up to 300 copies of one sprite! This is called **cloning**. Your task is to add code to the **Tree** sprite so that it creates clones of itself on the Stage.

--- task ---  
Go to the Sprites pane.  
--- /task ---  

--- task ---  
Click on the **Tree** sprite.  
--- /task ---  

--- task ---  
Drag a `when green flag clicked`{:class="block3events"} block onto your Code area.  

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
```  

--- /task ---  

--- task ---  
Drag a `forever`{:class="block3control"} block onto your Code area.  

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
+forever
end
```  

--- /task ---  

--- task ---  
Within the `forever`{:class="block3control"} block, add a `go to x:`{:class="block3motion"} `0` `y:`{:class="block3motion"} `0` block.  

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
forever
+go to x:(0) y:(0)
end
```  

--- /task ---  

--- task ---  
Within the `forever`{:class="block3control"} block, add a `create clone of myself`{:class="block3control"} block.  

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
forever
go to x:(0) y:(0)
+create clone of [myself v]
end
```  

--- /task ---  

--- task ---
Add a `pick random`{:class="block3operators"} block to your `x:`{:class="block3motion"} value to vary where the trees grow. 

Change the `x:`{:class="block3motion"} coordinate to `pick random`{:class="block3operators"} `-150` `to`{:class="block3operators"} `200`.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
forever
+go to x:(pick random (-150) to (200)) y:(0)
create clone of [myself v]
end
```
--- /task ---

--- task ---
Add a `pick random`{:class="block3operators"} block to your `y:`{:class="block3motion"} value to vary where the trees grow.
Change the `y:`{:class="block3motion"} coordinate to `pick random`{:class="block3operators"} `-120` `to`{:class="block3operators"} `120`.

![image of the Tree sprite](images/tree-sprite.png)
```blocks3
when flag clicked
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
create clone of [myself v]
end
```
--- /task ---

--- task ---

**Test your code.** Click the green flag and watch clones appear on your screen.

--- /task ---

