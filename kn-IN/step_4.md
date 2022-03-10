## ಮರಗಳನ್ನು ಎಣಿಸಿ

ವಿಜ್ಞಾನಿಗಳು ಮರಗಳು ಮತ್ತು ವನ್ಯಜೀವಿಗಳನ್ನು ಗಮನಿಸುತ್ತಿರುತ್ತಾರೆ. ಅವರು ಮರಗಳ ಮತ್ತು ಸುತ್ತಮುತ್ತಲಿನ ಪ್ರದೇಶಗಳ ಹೊದಿಕೆ(ಗಾತ್ರ), ವೈವಿಧ್ಯ, ಮತ್ತು ಆರೋಗ್ಯವನ್ನು ದಾಖಲು ಮಾಡಿಕೊಳ್ಳುತ್ತಾರೆ. ಇದನ್ನು ಮಾಡುವುದರಿಂದ, ಅವರು ಅರಣ್ಯನಾಶದ ನಿಜವಾದ ಪರಿಣಾಮವನ್ನು ನೋಡಬಹುದು. ಗಾಳಿಯಲ್ಲಿ ವಿಮಾನಗಳು ಮತ್ತು ಉಪಗ್ರಹಗಳು, ಹಾಗೆಯೇ ಸೆನ್ಸರ್‌ಗಳು ಮತ್ತು ನೆಲದ ಮೇಲಿನ ಜನರಿಂದ ಅವಲೋಕನಗಳನ್ನು ತೆಗೆದುಕೊಳ್ಳಬಹುದು. ಮರಗಳನ್ನು ಸಂರಕ್ಷಿಸಲು ಎಲ್ಲಿ ಅಧಿಕ ಕ್ರಮಗಳ ಅವಶ್ಯಕತೆ ಇದೆ ಎಂದು ಜನರು ನೋಡಲು ತಮ್ಮ ಸಂಶೋಧನೆಗಳನ್ನು ಉಪಯೋಗಿಸಬಹುದು. ಉದಾಹರಣೆಗೆ, ಮರಗಳು ಹುಲುಸಾಗಿ ಬೆಳೆಯಲು ಅರಣ್ಯದ ಸುತ್ತ ಬೇಲಿ ನಿರ್ಮಿಸುವುದು ಅಥವಾ ಕಾಡ್ಗಿಚ್ಚನ್ನು ಪತ್ತೆ ಮಾಡಲು ಮತ್ತು ನಿಲ್ಲಿಸಲು ಸಹಾಯಕವಾಗಲು ಹೆಚ್ಚು ಅಗ್ನಿಶಾಮಕ ಸಿಬ್ಬಂದಿಗಳನ್ನು ನೇಮಕ ಮಾಡಿಕೊಳ್ಳುವುದು.

ಈ ಹಂತದಲ್ಲಿ, ಮರಗಳ ಸಂಖ್ಯೆಯನ್ನು ಸಂಗ್ರಹವನ್ನು ಮಾಡುವ ಮತ್ತು ವಾತಾವರಣದಲ್ಲಿನ ಬದಲಾವಣೆಯನ್ನು ಪ್ರತಿಫಲನ ಮಾಡುವ ವೇರಿಯೇಬಲ್‌ ಮೂಲಕ ನೀವು ನಿಮ್ಮ ಸಾದೃಶ್ಯದಲ್ಲಿ ಮರಗಳನ್ನು ಗಮನಿಸುತ್ತೀರಿ.

--- task ---

ಸಂಪೂರ್ಣವಾಗಿ ಬೆಳೆದಿರುವ ಮರಗಳ ಸಂಖ್ಯೆಯನ್ನು ಸಂಗ್ರಹಿಸಲು ಹೊಸ `variable`{:class="block3variables"} ರಚಿಸಿ. ಈ ವೇರಿಯೇಬಲ್‌ನ್ನು `mature trees`{:class="block3variables"} ಎಂದು ಕರೆಯಿರಿ.

--- /task ---

ಸಾದೃಶ್ಯ `0` ಕ್ಕೆ ಪ್ರಾರಂಭವಾದಾಗ ಮರಗಳ ಸಂಖ್ಯೆಯನ್ನು ಮರುಹೊಂದಿಸಿ.

--- task ---

`when green flag clicked`{:class="block3events"} ಬ್ಲಾಕ್‌ ಕೆಳಗೆ, `mature trees`{:class="block3variables"} ವೇರಿಯೇಬಲ್‌ನ್ನು `0` ಗೆ ಹೊಂದಿಸಿ:

![Tree  ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when flag clicked
+ set (mature trees) to (0)
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
reset timer
repeat until {{(timer)>((6)-(tree management))}}
wait (1) seconds
end
create clone of [myself v]
end
```

--- /task ---

ಸಾದೃಶ್ಯ ರನ್‌ ಆಗುತ್ತಿರುವಾಗ ನಿಮ್ಮ ಕೌಂಟರ್‌ ಎಷ್ಟು ಮರಗಳು ರಚನೆಯಾದವು ಎನ್ನುವುದನ್ನು ದಾಖಲಿಸಿಕೊಳ್ಳುತ್ತದೆ ಎಂದು ಖಚಿತಪಡಿಸಿಕೊಳ್ಳಿ.

--- task ---

ನಿಮ್ಮ `when I start as a clone`{:class="block3control"} ಬರಹವನ್ನು ಪತ್ತೆ ಮಾಡಿ ಮತ್ತು `change mature trees by 1`{:class="block3variables"} ಬ್ಲಾಕ್‌ನ್ನು ಕೊನೆಯಲ್ಲಿ ಸೇರಿಸಿ:

![Tree  ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
+ change (mature trees) by (1)
```

--- /task ---

ಅವುಗಳಲ್ಲಿ ಎಲ್ಲಾ ಮರಗಳೂ ಬದುಕುವುದಿಲ್ಲವಾದರೂ, ಈಗ ನೀವು ನಿಮ್ಮ ಹೊಸ ಮರಗಳನ್ನು ಎಣಿಸಬಹುದು. ಹೊಸ ಮರಗಳು ಬದುಕುಳಿಯುವ ದರವನ್ನು ಶೇಕಡಾ 80 ಎಂದು ಅಂದಾಜು ಮಾಡಲಾಗಿದೆ, ಅಂದರೆ ನೆಟ್ಟಿರುವ 10 ಮರಗಳಲ್ಲಿ 2 ಮರಗಳು ಸಂಪೂರ್ಣವಾಗಿ ಬೆಳೆಯುವ ಮೊದಲೇ ನೈಸರ್ಗಿಕ ಕಾರಣಗಳಿಂದ ಸಾಯುತ್ತವೆ. ನೀವು ಇದನ್ನು ನಿಮ್ಮ ಸಾದೃಶ್ಯದಲ್ಲಿ ಪ್ರತಿಬಿಂಬಿಸುವುದಿಲ್ಲ, ಆದರೆ ಎಲ್ಲಾ ಹೊಸ ಮರಗಳೂ ಸಹಜವಾಗಿ ಬದುಕುವುದಿಲ್ಲ ಎಂದು ತಿಳಿದುಕೊಳ್ಳುವುದು ಮಹತ್ವವಾಗಿರುತ್ತದೆ.

ಮಾನವ ಅರಣ್ಯನಾಶದ ಮೂಲಕ ಬೆಳೆದಿರುವ ಮರಗಳನ್ನೂ ಸಹ ಕಡಿಯಬಹುದು. ಇದನ್ನು ತೋರಿಸಲು, ಮರವನ್ನು **Tree Feller** ಸ್ಪ್ರೈಟ್‌ ಸ್ಪರ್ಶಿಸಿದರೆ ಪ್ರೌಢ ಮರಗಳ ಸಂಖ್ಯೆಯನ್ನು ಕಡಿಮೆ ಮಾಡಿ.

--- task ---

`wait until`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ನಿಮ್ಮ ಕೋಡ್‌ನ ಕೊನೆಗೆ ಸೇರಿಸಿ, ಮತ್ತು ಈ ಬ್ಲಾಕ್‌ನ ಒಳಗೆ `touching Tree Feller`{:class="block3sensing"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ. `change mature trees by 1`{:class="block3variables"} ಬ್ಲಾಕ್‌ನ್ನು ಸೇರಿಸಿ ಮತ್ತು ಮೌಲ್ಯವನ್ನು `-1` ಕ್ಕೆ ಬದಲಾಯಿಸಿ. ಮರವನ್ನು ತೆಗೆದುಹಾಕಲು `delete this clone`{:class="block3control"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ:

![Tree  ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when I start as a clone
show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
change (mature trees) by (1)
+ wait until {touching [Tree Feller v]?}
+ change (mature trees) by (-1)
+ delete this clone
```

--- /task ---

ಮರಗಳು ಪ್ರೌಢವಾಗಿರಬಹುದು ಅಥವಾ ಇನ್ನೂ ಬೆಳೆಯುತ್ತಿರಬಹುದು ಅವುಗಳು ನೈಸರ್ಗಿಕ ಅರಣ್ಯನಾಶದಿಂದಲೂ ಸಹ ಸಾಯಬಹುದು. ಇದನ್ನು ತೋರಿಸಲು, ಮರವನ್ನು **Natural Disaster** ಸ್ಪ್ರೈಟ್‌ ಸ್ಪರ್ಶಿಸಿದರೆ ನಿಮ್ಮ ಮರಗಳ ಸಂಖ್ಯೆಯನ್ನು ಕಡಿಮೆ ಮಾಡಿ.

--- task ---

`when I start as a clone`{:class="block3control"} ಬ್ಲಾಕ್‌ನೊಂದಿಗೆ ಹೊಸ ಬರಹವನ್ನು ಪ್ರಾರಂಭಿಸಿ. `wait until`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ನಿಮ್ಮ ಕೋಡ್‌ನ ಕೊನೆಯಲ್ಲಿ ಸೇರಿಸಿ ಮತ್ತು ಈ ಬ್ಲಾಕ್‌ ಒಳಗೆ `touching Natural Disaster`{:class="block3sensing"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ. `size`{:class="block3looks"} `=`{:class="block3operators"} `20` ಷರತ್ತಿನೊಂದಿಗೆ `if ... then`{:class="block3control"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ .

`if ... then`{:class="block3control"} ಬ್ಲಾಕ್‌ ಒಳಗೆ, `change mature trees by 1`{:class="block3variables"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ, ಅದರಿಂದ ಸಂಪೂರ್ಣ ಬೆಳೆದ ಮರವಾದರೆ ಮಾತ್ರ ಪೌಢ ಮರಗಳ ಸಂಖ್ಯೆ ಕಡಿಮೆಯಾಗುತ್ತದೆ. ಮರವನ್ನು ತೆಗದುಹಾಕಲು `delete this clone`{:class="block3control"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ:

```blocks3
when I start as a clone
wait until {touching [Natural Disaster v]?}
if {(size) = (20)} then
change (mature trees) by (-1)
end
delete this clone
```

--- /task ---

--- save ---
