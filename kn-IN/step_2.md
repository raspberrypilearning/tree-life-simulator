## ಕೆಲವು ಮರಗಳನ್ನು ಬೆಳೆಸಿ

ಭೂಮಿಯ ಮೇಲ್ಮೈಯ 30 ಪ್ರತಿಶತದಷ್ಟನ್ನು ಮರಗಳು ಆವರಿಸುತ್ತವೆ ಎಂದು ನಿಮಗೆ ತಿಳಿದಿದೆಯೇ? ನಾವು ನಮ್ಮ ಸ್ಥಳೀಯ ಮರಗಳನ್ನು ಈಗ ನೋಡಿಕೊಳ್ಳುವ ರೀತಿ, ನಮ್ಮ ಗ್ರಹದ ಭವಿಷ್ಯದ ಮೇಲೆ ಪರಿಣಾಮ ಬೀರುತ್ತದೆ. ಈ ಹಂತದಲ್ಲಿ, ಬೇರೆ ಬೇರೆ ವೈವಿಧ್ಯವುಳ್ಳ ಮರಗಳಿಂದ ಕೂಡಿದ ಮರಗಳ ಪ್ರದೇಶವನ್ನು ರಚಿಸಲು ನೀವು ಕೋಡ್‌ ಸೇರಿಸುತ್ತೀರಿ.

--- task ---

**ಆನ್‌ಲೈನ್:** ಸ್ಕ್ರಾಚ್‌ನಲ್ಲಿ [ಪ್ರಾಂಭಿಕ ಪ್ರಾಜೆಕ್ಟ್](http://rpf.io/tree-life-simulator-on){:target="_blank"} ತೆರೆಯಿರಿ.

**ಆಫ್‌ಲೈನ್:** Scratch ಆಫ್‌ಲೈನ್‌ ಎಡಿಟರ್‌ನಲ್ಲಿ [ಪ್ರಾಜೆಕ್ಟ್‌ ಪ್ರಾರಂಭಿಕ ಫೈಲ್](http://rpf.io/p/kn-IN/tree-life-simulator-get){:target="_blank"} ತೆರೆಯಿರಿ. ನಿಮಗೆ ಬೇಕಾದರೆ, ನೀವು [ಇಲ್ಲಿ Scratch ಡೌನ್‌ಲೋಡ್‌ ಮಾಡಿಕೊಂಡು ಇನ್‌ಸ್ಟಾಲ್‌ ಮಾಡಬಹುದು](https://scratch.mit.edu/download){:target="_blank"}.

ನೀವು ಹಸಿರು ಹುಲ್ಲುಗಾವಲು ಹಿನ್ನೆಲೆಯನ್ನು ನೋಡಬೇಕು.

![ಪ್ರಾರಂಭಿಕ ಪ್ರಾಜೆಕ್ಟ್](images/starter_project.png)

--- /task ---

Scratch‌ ನಲ್ಲಿ, ನೀವು ಒಂದು ಸ್ಪ್ರೈಟ್‌ನ 300 ನಕಲುಗಳವರೆಗೆ ಮಾಡಬಹುದು! ಇದನ್ನು **ತದ್ರೂಪ** ಎಂದು ಕರೆಯುತ್ತಾರೆ. ನಿಮ್ಮ ಕಾರ್ಯವೆಂದರೆ Stage ಮೇಲೆ ಅದರ ತದ್ರೂಪವನ್ನು ತಾನೆ ರಚಿಸಿಕೊಳ್ಳುವಂತೆ ಮಾಡಲು **Tree** ಸ್ಪ್ರೈಟ್‌ಗೆ ಕೋಡ್‌ ಸೇರಿಸುವುದು.

--- task ---

Sprites ಪೇನ್‌ಗೆ ಹೋಗಿ, ಮತ್ತು **Tree** ಸ್ಪ್ರೈಟ್‌ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ. `when green flag clicked`{:class="block3events"} ಬ್ಲಾಕ್‌ ಮತ್ತು `forever`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ನಿಮ್ಮ Code ಪ್ರದೇಶಕ್ಕೆ ಎಳೆಯಿರಿ. `forever`{:class="block3control"} ಬ್ಲಾಕ್‌ ಒಳಗೆ, `go to x:`{:class="block3motion"} `0` `y:`{:class="block3motion"} `0` ಬ್ಲಾಕ್‌ ಮತ್ತು `create clone of myself`{:class="block3control"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ:

![tree ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when flag clicked
forever
go to x:(0) y:(0)
create clone of [myself v]
end
```

--- /task ---

ನಂತರ, Stage ಉದ್ದಕ್ಕೂ ಯಾದೃಚ್ಛಿಕ ಸ್ಥಾನಗಳಲ್ಲಿ ತದ್ರೂಪ ಮಾಡಿದ ಮರಗಳನ್ನು ನೆಡಿ.

--- task ---

ಮರಗಳು ಎಲ್ಲಿ ಬೆಳೆಯಬೇಕು ಎನ್ನುವುದನ್ನು ಮಾರ್ಪಾಡು ಮಾಡಲು `pick random`{:class="block3operators"} ಬ್ಲಾಕ್‌ನ್ನು ನಿಮ್ಮ ಎರಡೂ `x:`{:class="block3motion"} ಮತ್ತು `y:`{:class="block3motion"} ಮೌಲ್ಯಗಳಿಗೆ ಸೇರಿಸಿ. `x:`{:class="block3motion"} ನಿರ್ದೇಶಾಂಕಗಳನ್ನು `pick random`{:class="block3operators"} `-150` `ರಿಂದ`{:class="block3operators"} `200`ಕ್ಕೆ ಬದಲಾಯಿಸಿ. `y:`{:class="block3motion"} ನಿರ್ದೇಶಾಂಕಗಳನ್ನು `pick random`{:class="block3operators"} `-120` `ರಿಂದ`{:class="block3operators"} `120`ಕ್ಕೆ ಬದಲಾಯಿಸಿ:

![tree ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when flag clicked
forever
+ go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
create clone of [myself v]
end
```

--- /task ---

ವಿವಿಧ ಶ್ರೇಣಿಯ ಪ್ರಾಣಿಗಳನ್ನು ಇರಿಸಲು, ವಾತಾವರಣವನ್ನು ಪುನರ್ನಿಮಾಣ ಮಾಡಲು, ಮತ್ತು ಜನರ ಪ್ರಯೋಜನಕ್ಕಾಗಿ ನೀವು ವಿವಿಧ ಮರಗಳನ್ನು ನೆಡುವುದು ಮಹತ್ವವಾಗಿರುತ್ತದೆ. ಉದಾಹರಣೆಗೆ, ಆಸ್ಟ್ರೇಲಿಯಾದಲ್ಲಿ ಕೋಲಾ ಅಗಲ ಎಲೆಯ ನಿತ್ಯಹರಿದ್ವರ್ಣಗಳ ಮೇಲೆ ಅವಲಂಬಿತವಾಗಿರುತ್ತದೆ, ಆದರೆ ಮಡಗಾಸ್ಕರ್‌ನಲ್ಲಿ ಲೇಮುರ್‌ಗೆ ದ್ವೀಪದಲ್ಲಿ ಬೆಳೆಯುವ ಎಲೆ ಉದುರಿಸುವ ಮರಗಳು ಬೇಕಾಗುತ್ತವೆ.

**Tree** ಸ್ಪ್ರೈಟ್‌ಗೆ ಮೂರು ಉಡುಪುಗಳಿವೆ: **tree 1**, **tree 2**, ಮತ್ತು **tree 3**. ಅವುಗಳನ್ನು ನೋಡಲು **Costumes** ಟ್ಯಾಬ್‌ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ.

ಮತ್ತೆ **Code** ಟ್ಯಾಬ್‌ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ ಮತ್ತು ಮರಗಳ ನೋಟವನ್ನು ಬದಲಾಯಿಸಲು ಹಾಗು ಪ್ರದೇಶಕ್ಕೆ ವೈವಿಧ್ಯತೆಯನ್ನು ಸೇರಿಸಲು `random`{:class="block3operators"} ಆಪರೇಟರ್‌ ಉಪಯೋಗಿಸಿ.

--- task ---

`when I start as a clone`{:class="block3control"} ಬ್ಲಾಕ್‌ನೊಂದಿಗೆ ಹೊಸ ಬರಹವನ್ನು ಪ್ರಾರಂಭಿಸಿ. ಅದರ ಕೆಳಗೆ `switch costume to`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ. `switch costume to`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಒಳಗೆ `pick random 1 to 10`{:class="block3operators"} ಬ್ಲಾಕ್‌ನ್ನು ಎಳೆಯಿರಿ. ಮೌಲ್ಯಗಳನ್ನು `1` ಮತ್ತು `10` ರಿಂದ `1` ಮತ್ತು `3` ರವರೆಗೆ ಬದಲಾಯಿಸಿ:

![tree ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
```

--- /task ---

--- task ---

ಹಸಿರು ಬಾವುಟದ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ ನಿಮ್ಮ ಸಾದೃಶ್ಯವನ್ನು ಪರೀಕ್ಷಿಸಿ. ನೀವು ವೈವಿಧ್ಯ ಮರಗಳನ್ನು ಹೊಂದಿರುವುದನ್ನು ಖಚಿತಪಡಿಸಿಕೊಳ್ಳಿ.

![ಮೊದಲ ಮರಗಳ ಚಿತ್ರ ](images/first-trees.png)

--- /task ---

ಮರಗಳು ಸಂಪೂರ್ಣವಾಗಿ ಬೆಳೆದಿರುವಂತೆ ಕಾಣುವುದಷ್ಟೆ ಅಲ್ಲ, ಅವುಗಳು ಸಮಯ ಕಳೆದಂತೆ ದೊಡ್ಡದಾಗುತ್ತವೆ. ಮರವು ಬೆಳೆದಂತೆ ನೀವು ಅದರ ಗಾತ್ರವನ್ನು ಶೇಕಡಾ 20ಕ್ಕೆ ಸಮನಾಗುವವರೆಗೆ ಬದಲಾಯಿಸಲು ನೀವು `repeat until`{:class="block3control"} ಲೂಪ್‌ ಹೊಂದಿಸಬೇಕು.

--- task ---

`set size to 100`{:class="block3looks"} (percent) ಬ್ಲಾಕ್‌ ತನ್ನಿ, ಆದರೆ ಮೌಲ್ಯವನ್ನು `0` ಬದಲಾಯಿಸಿ, ಅದರಿಂದ **Tree** ಸ್ಪ್ರೈಟ್‌ ಶೂನ್ಯದಿಂದ ಪ್ರಾರಂಭಿಸುತ್ತದೆ. `repeat until`{:class="block3control"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ, ಮತ್ತು ಅದರೊಳಗೆ ಬರೋಬ್ಬರಿ `=`{:class="block3operators"} ಬ್ಲಾಕ್‌ ಎಳೆಯಿರಿ. `size`{:class="block3looks"} `=`{:class="block3operators"} `20` ಷರತ್ತನ್ನು ಸೇರಿಸಿ:

![tree ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
+ set size to (0)%
+ repeat until {(size)=[20]}
end
```

--- /task ---

ಮರವು ಗಾತ್ರ ಬದಲಾಯಿಸುವಂತೆ ಮಾಡಿ ಮತ್ತು ಅದು ಬೆಳೆಯಲು ಕಾಯಿರಿ.

--- task ---

ಲೂಪ್‌ ಒಳಗೆ `change size by 10`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ ಮತ್ತು ಮೌಲ್ಯವನ್ನು `1`ಕ್ಕೆ ಬದಲಾಯಿಸಿ. `wait 1 seconds`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ಸೇರಿಸಿ ಮತ್ತು ಮೌಲ್ಯವನ್ನು `0.1` ಕ್ಕೆ ಬದಲಾಯಿಸಿ, ಅದರಿಂದ ಅದು ಬೇಗ ಬದಲಾಗುತ್ತದೆ:

![tree ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/tree-sprite.png)

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
+ change size by (1)
+ wait (0.1) seconds
end
```

--- /task ---

--- task ---

ನಿಮ್ಮ ಸಾದೃಶ್ಯವನ್ನು ಮತ್ತೊಮ್ಮೆ ಪರೀಕ್ಷಿಸಿ. ನಿಮ್ಮ ಮರಗಳು ಬೆಳೆಯುತ್ತವೆ, ಆದರೆ ನಿಮ್ಮ ಮುಂದಿನ ತದ್ರೂಪವು ಬೆಳೆಯುತ್ತಿರುತ್ತದೆಯೋ ಅಲ್ಲಿ ಸಂಪೂರ್ಣವಾಗಿ ಬೆಳೆದ ಮರವೂ ಕಾಣಿಸಿಕೊಳ್ಳುತ್ತದೆ.

--- /task ---

ಮರವು ಹೊಸ ತದ್ರೂಪವನ್ನು ಪ್ರಾರಂಭಿಸುವವರೆಗೆ ಅದನ್ನು ಮರೆಮಾಡಿ.

--- task ---

`when green flag clicked`{:class="block3events"} ಬರಹದ ಪ್ರಾರಂಭದಲ್ಲಿ `hide`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ ಮತ್ತು `when I start as a clone`{:class="block3control"} ಬರಹದ ಪ್ರಾರಂಭದಲ್ಲಿ `show`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ.

```blocks3
when flag clicked
+ hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
create clone of [myself v]
end
```

```blocks3
when I start as a clone
+ show
switch costume to (pick random (1) to (3))
set size to (0)%
repeat until {(size)=[20]}
change size by (1)
wait (0.1) seconds
end
```

--- /task ---

--- task ---

ನಿಮ್ಮ ಸಾದೃಶ್ಯವನ್ನು ಮತ್ತೊಮ್ಮೆ ಪರೀಕ್ಷಿಸಿ. ನಿಮ್ಮ ಮರಗಳು ಈಗ ನಿಜ ಜೀವನದಲ್ಲಿ ಬೆಳೆಯುವಂತೆ ಬೆಳೆಯಬೇಕು.

--- /task ---

--- save ---
