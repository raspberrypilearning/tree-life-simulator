## ನೈಸರ್ಗಿಕ ಅರಣ್ಯನಾಶ

ಬರ, ಕಾಡ್ಗಿಚ್ಚು, ಅಥವಾ ಸುಂಟರಗಾಳಿಯಂತಹ ನೈಸರ್ಗಿಕ ವಿಪತ್ತು- ಭೂ ಪ್ರದೇಶವೊಂದನ್ನು ಧ್ವಂಸಗೊಳಿಸಿದಾಗ ಅರಣ್ಯನಾಶ ಸಂಭವಿಸಬಹುದು. ಕ್ಯಾಂಪ್‌ ಫೈರ್‌ನಂತಹ ಮಾನವ ಚಟುವಟಿಕೆಯಿಂದ ಸಹ ಅದು ಪ್ರಚೋದನೆಗೊಂಡಿರಬಹುದು, ಆದರೆ ತುಂಬಾ ಒಣ ಋತುವಿನಂತಹ ನೈಸರ್ಗಿಕ ಪರಿಸ್ಥಿತಿಗಳಿಂದ ಬೇಗ ಹರಡುತ್ತದೆ. ಪೀಡಿತ ವಿಶಾಲ ಪ್ರದೇಶದಲ್ಲಿ ಸಂಪೂರ್ಣ ಪ್ರಭೇದಗಳು ಅವುಗಳ ಆವಾಸಸ್ಥಾನಗಳೊಂದಿಗೆ ಕಣ್ಮರೆಯಾಗಬಹುದಾದುರಿಂದ ಇದು ವಿಶೇಷವಾಗಿ ಮಾರಣಾಂತಿಕವಾಗಬಹುದು.

ಅರಣ್ಯದಲ್ಲಿ ಯಾದೃಚ್ಛಿಕವಾಗಿ ಚಲಿಸುವ ಪ್ರಕೃತಿ ವಿಕೋಪದ ಪ್ರಭಾವವನ್ನು ಸಾದೃಶ್ಯಗೊಳಿಸಿ. ಸಾದೃಶ್ಯದ ಪ್ರಾರಂಭದಲ್ಲಿ **Natural Disaster** ಸ್ಪ್ರೈಟ್‌ನ್ನು ಮರೆಮಾಚಿ.

--- task ---

**Natural Disaster** ಸ್ಪ್ರೈಟ್‌ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ, ನಂತರ Code ಪ್ರದೇಶದಲ್ಲಿ `when green flag clicked`{:class="block3events"} ಬ್ಲಾಕ್‌ನ್ನು ಸೇರಿಸಿ, ಅದಾದ ನಂತರ `hide`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ:

![Natural Disaster ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/natural-disaster-sprite.png)

```blocks3
when flag clicked
hide
```

--- /task ---

**Natural Disaster** ಸ್ಪ್ರೈಟ್‌ ಪರದೆಯ ಮೇಲೆ ಮೇಲಿನಿಂದ ಕೆಳಕ್ಕೆ ಚಲಿಸುತ್ತದೆ.

--- task ---

`forever`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ನಿಮ್ಮ ಕೋಡ್‌ ಕೊನೆಯಲ್ಲಿ ಸೇರಿಸಿ. ಅದರೊಳಗೆ, `go to x:0 y:0`{:class="block3motion"} ಬ್ಲಾಕ್‌ನ್ನು ಸೇರಿಸಿ, ಮತ್ತು `y:`{:class="block3motion"} ಮೌಲ್ಯವನ್ನು `200` ಕ್ಕೆ ಬದಲಾಯಿಸಿ. `show`{:class="block3looks"} ಬ್ಲಾಕ್ ಸೇರಿಸಿ, ಅದಾದ ನಂತರ `glide 1 secs to x:0 y:0`{:class="block3motion"}, ಮತ್ತು ಸೆಕೆಂಡುಗಳ ಮೌಲ್ಯವನ್ನು `3` ಮತ್ತು `y:`{:class="block3motion"} ಮೌಲ್ಯವನ್ನು `-200`‌ ಕ್ಕೆ ಬದಲಾಯಿಸಿ:

![Natural Disaster ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/natural-disaster-sprite.png)


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

**Natural Disaster** ಸ್ಪ್ರೈಟ್‌ ಮೂರು ಉಡುಪುಗಳನ್ನು ಹೊಂದಿದೆ: **Drought**, **Forest Fire**, ಮತ್ತು **Tornado**, ಏಕೆಂದರೆ ಮರಗಳು ಅನೇಕ ವಿಧದ ಪ್ರಕೃತಿ ವಿಕೋಪಗಳಿಂದ ಹೊಡೆತಕ್ಕೊಳಗಾಗಬಹುದು. ಕೊಡ್‌ನ್ನು ಸೇರಿಸಿ ಅದರಿಂದ ಸಾದೃಶ್ಯವು ಬಹು ವಿಧಗಳ ವಿಪತ್ತುಗಳನ್ನು ಹೊಂದಿರುತ್ತದೆ.

--- task ---

 ಉಡುಪುಗಳನ್ನು ನೋಡಲು **Costumes** ಟ್ಯಾಬ್‌ ಕ್ಲಿಕ್‌ ಮಾಡಿ. ಹಿಂತಿರುಗಿ **Code** ಟ್ಯಾಬ್‌ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ ಮತ್ತು ಅದು ಪರದೆಯ ಕೆಳಭಾಗಕ್ಕೆ ತಲುಪಿದಾಗ `hide`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ, ಅದಾದ ನಂತರ `next costume`{:class="block3looks"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ:

![Natural Disaster ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/natural-disaster-sprite.png)


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

ನಿಮ್ಮ ಪ್ರಾಜೆಕ್ಟನ್ನು ಪರೀಕ್ಷಿಸಿ. **Natural Disaster** ಸ್ಪ್ರೈಟ್‌ ಈಗ ಮೇಲಿನಿಂದ ಕೆಳಕ್ಕೆ ಚಲಿಸುತ್ತದೆ ಮತ್ತು ಪ್ರತಿಬಾರಿ ಉಡುಪನ್ನು ಬದಲಾಯಿಸುತ್ತದೆ.

![ವೇದಿಕೆ ಮೇಲೆ ಪ್ರಕೃತಿ ವಿಕೋಪದ ಚಿತ್ರ](images/disaster-on-stage.png)

--- /task ---

ಪ್ರಕೃತಿ ವಿಕೋಪಗಳು ಯಾವಾಗ ಸಂಭವಿಸುತ್ತವೆ ಎಂಬುದನ್ನು ವಿಜ್ಞಾನಿಗಳು ಕೆಲವೊಮ್ಮೆ ಊಹಿಸಬಹುದು, ಆದರೂ ಇದು ಕಷ್ಟಕರವಾಗಿರುತ್ತದೆ ಏಕೆಂದರೆ ಸಾದೃಶ್ಯದಂತೆ ಅವುಗಳ ಸಮಯವು ಯಾವಾಗಲೂ ಸ್ಪಷ್ಟವಾಗಿರುವುದಿಲ್ಲ,. ಈಗ, ನಿಜ ಜೀವನದಂತೆ ಸ್ಪ್ರೈಟ್‌ನ ಕಾಣಿಸಿಕೊಳ್ಳುವಿಕೆಯನ್ನು ಅನಿರೀಕ್ಷಿತಗೊಳೀಸಲು **Natural Disaster** ಸ್ಪ್ರೈಟ್‌ಗೆ ಯಾದೃಚ್ಛಿಕ ಸಮಯಗಳನ್ನು ಸೇರಿಸಿ.

--- task ---

ಯಾದೃಚ್ಛಿಕ ಸಮಯಗಳನ್ನು ರಚಿಸಲು `wait 1 seconds`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ನಿಮ್ಮ `forever`{:class="block3control"} ಬ್ಲಾಕ್‌ ಮೇಲ್ಗಡೆ ಸೇರಿಸಿ. `pick random`{:class="block3operators"} ಆಪರೇಟರ್‌ನ್ನು`wait`{:class="block3control"} ಬ್ಲಾಕ್‌ ಒಳಗೆ ಎಳೆಯಿರಿ ಮತ್ತು ಮೌಲ್ಯಗಳನ್ನು `10` ಮತ್ತು `20`ಕ್ಕೆ ಬದಲಾಯಿಸಿ:

![Natural Disaster ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/natural-disaster-sprite.png)


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

**Natural Disaster** ಸ್ಪ್ರೈಟ್‌ನ ಚಲನೆಗೆ ಯಾದೃಚ್ಛಿಕತೆಯನ್ನು ಸೇರಿಸಿ.

--- task ---

`pick random`{:class="block3operators"} ಆಪರೇಟರ್‌ನ್ನು `x:`{:class="block3motion"} ರೊಳಗೆ `go to`{:class="block3motion"} ಬ್ಲಾಕ್‌ ಮತ್ತು `glide`{:class="block3motion"} ಬ್ಲಾಕ್‌ಗಳೆರಡರ ನಿರ್ದೇಶಾಂಕಗಳಿಗೆ ಎಳೆಯಿರಿ. ಪ್ರತಿಯೊಂದರಲ್ಲೂ ಮೌಲ್ಯಗಳನ್ನು `-200` ಮತ್ತು `200` ಕ್ಕೆ ಬದಲಾಯಿಸಿ:

![Natural Disaster ಸ್ಪ್ರೈಟ್‌ನ ಚಿತ್ರ](images/natural-disaster-sprite.png)


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

ನಿಮ್ಮ ಪ್ರಾಜೆಕ್ಟನ್ನು ಮತ್ತೊಮ್ಮೆ ಪರೀಕ್ಷಿಸಿ. ನಿಮ್ಮ **Natural Disaster** ಸ್ಪ್ರೈಟ್‌ ಈಗ ಒಂದು ಯಾದೃಚ್ಛಿಕ ಸ್ಥಾನದಿಂದ ಇನ್ನೊಂದು ಯಾದೃಚ್ಛಿಕ ಸ್ಥಾನಕ್ಕೆ ಬೀಳುವ ಮೊದಲು 10 ಮತ್ತು 20 ಸೆಕೆಂಡುಗಳ ನಡುವೆ ಕಾಯಬೇಕು. ಅದು ಪ್ರತಿಬಾರಿಯೂ ಉಡುಪನ್ನೂ ಸಹ ಬದಲಾಯಿಸುತ್ತದೆ ಮತ್ತು ಅದು ಸ್ಪರ್ಶಿಸುವ ಯಾವುದೇ ಮರವನ್ನು ತೆಗೆದುಹಾಕುತ್ತದೆ.

--- /task ---

--- save ---
