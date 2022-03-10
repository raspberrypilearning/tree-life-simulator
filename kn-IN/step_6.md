## ಮರದ ಮಟ್ಟಗಳನ್ನು ಗಮನಿಸಿ

ಭೂಮಿಯ ಮೇಲಿನ ನಮ್ಮ ಜೀವನದ ಗುಣಮಟ್ಟಕ್ಕೆ ಮರಗಳು ಬಹಳ ಮಹತ್ವವಾಗಿರುತ್ತವೆ. ಮರಗಳಿಂದ, ಜನರು ತಿನ್ನಲು ಹಣ್ಣುಗಳನ್ನು, ಆರೋಗ್ಯಕರ ಜೀವನಕ್ಕೆ ತೈಲಗಳು, ಮತ್ತು ಹವಾಮಾನದಿಂದ ಆಶ್ರಯ ಪಡೆಯುತ್ತಾರೆ. ಮರಗಳು ಕಾರ್ಬನ್‌ ಡೈ ಆಕ್ಸೈಡ್‌ ಹೀರಿಕೊಳ್ಳುತ್ತವೆ ಮತ್ತು ಪ್ರಪಂಚದಾದ್ಯಂತ ಹೊರಸೂಸಲ್ಪಡುವ CO2 ದರವನ್ನು ಕಡಿಮೆ ಮಾಡಲು ಸಹಾಯ ಮಾಡುತ್ತವೆ. ಅವುಗಳು ಅನೇಕ ವಿವಿಧ ಜಾತಿಯ ಪ್ರಾಣಿಗಳಿಗೆ ನೆಲೆಯಾಗಿವೆ. ನಮ್ಮ ಗ್ರಹವನ್ನು ರಕ್ಷಿಸಲು ಮರಗಳು ಸಹಾಯ ಮಾಡುತ್ತವೆ!

ಈ ಹಂತದಲ್ಲಿ, ನೀವು ಮರಗಳ ಸಂಖ್ಯೆಯನ್ನು ಗಮನಿಸಲು ಕೋಡ್‌ ಸೇರಿಸುವಿರಿ ಮತ್ತು ಮರದ ಪ್ರದೇಶವು ಆರೋಗ್ಯಕರವಾಗಿದೆಯೇ ಅಥವಾ ತುಂಬಾ ಚಿಕ್ಕದಾಗಿದೆಯೇ ಎಂದು ಹೇಳುವ ಸಂದೇಶಗಳನ್ನು ಸೇರಿಸುತ್ತೀರಿ.

ಸಾದೃಶ್ಯವು ಪ್ರಾರಂಭವಾದಾಗ ಮರದ ನಿರ್ವಹಣೆಯ ಮಟ್ಟವನ್ನು ಸೊನ್ನೆಗೆ ಹೊಂದಿಸಿ.

--- task ---

**Maya** ಸ್ಪ್ರೈಟ್‌ ಮೇಲೆ ಕ್ಲಿಕ್‌ ಮಾಡಿ. Code ಪ್ರದೇಶದಲ್ಲಿ ಈಗಾಗಲೇ ಒಂದೆರಡು ಬ್ಲಾಕ್‌ಗಳು ಇರುವುದನ್ನು ನೀವು ನೋಡುತ್ತೀರಿ. ಇವುಗಳು Maya ಗೆ ಬಳಕೆದಾರರಿಗೆ ಕೆಲವು ಪಠ್ಯಗಳೊಂದಿಗೆ ಸಾದೃಶ್ಯವನ್ನು ಪ್ರಾರಂಭಿಸಲು ಹೇಳುತ್ತವೆ. `set tree management to 0`{:class="block3variables"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ.

![Maya ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/maya-sprite.png)

```blocks3
when flag clicked
+ set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
```

--- /task ---

ಸಾದೃಶ್ಯಕ್ಕೆ ಕೋಡ್‌ ಸೇರಿಸಿ ಅದರಿಂದ **Maya** ಸ್ಪ್ರೈಟ್‌ ಎಲ್ಲಾ ಮರಗಳು ಹೋದಾಗ ಹೇಳುತ್ತದೆ.

--- task ---

`forever`{:class="block3control"} ಬ್ಲಾಕ್‌ನ್ನು ಸೇರಿಸಿ, ನಂತರ ಅದರೊಳಗೆ `if ... then`{:class="block3control"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ. ಷರತ್ತನ್ನು ಸೇರಿಸಿ, `mature trees`{:class="block3variables"} `=`{:class="block3operators"} `0`. `say for 2 seconds`{:class="block3looks"} ಬ್ಲಾಕ್ ಸೇರಿಸಿ‌ ಮತ್ತು ಟೈಪ್‌ ಮಾಡಿ: `Our planet needs more trees.`:

![Maya ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/maya-sprite.png)

```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
+ forever
if {(mature trees) = [0]} then
say [Our planet needs more trees.] for (2) seconds
end
```

![ಮರಗಳು ಹೋಗಿವೆ ಸಂದೇಶದ ಚಿತ್ರ](images/trees-gone-message.png)

--- /task ---

CO2 ಮಟ್ಟಗಳು ಅಪಾಯಕಾರಿ ಎಂದು ಕಂಡುಬಂದರೆ ವಿಜ್ಞಾನಿಗಳು ಎಚ್ಚರಿಕೆ ನೀಡಲು ತಮ್ಮ ಅವಲೋಕನಗಳನ್ನು ಉಪಯೋಗಿಸುತ್ತಾರೆ. ಎಚ್ಚರಿಕೆಯನ್ನು ಸೇರಿಸಿ ಅದರಿಂದ ಸಾಕಷ್ಟು ಮರಗಳಿಲ್ಲದಿದ್ದರೆ **Maya** ಸ್ಪ್ರೈಟ್‌ ಎಚ್ಚರಿಸುತ್ತದೆ.

ಉಳಿದಿರುವ ಪ್ರೌಢ ಮರಗಳ ಸಂಖ್ಯೆ `0` ಕ್ಕಿಂತ ಹೆಚ್ಚು ಮತ್ತು `10` ಕ್ಕಿಂತ ಕಡಿಮೆ ಇದ್ದಾಗ ಸಂದೇಶವೊಂದು ಕಾಣಿಸಿಕೊಳ್ಳುವಂತೆ ಹೊಂದಿಸಿ.

--- task ---

ನಿಮ್ಮ `forever`{:class="block3control"} ಬ್ಲಾಕ್‌ ಒಳಗೆ `if ... then`{:class="block3control"} ಸೇರಿಸಿ.

ನಿಮ್ಮ ಲೆಕ್ಕಾಚಾರಕ್ಕೆ ಕೆಲವು ಆಪರೇಟರ್‌ಗಳನ್ನು ಸೇರಿಸಿ. ಮೊದಲಿಗೆ `and`{:class="block3operators"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ, ನಂತರ `greater than`{:class="block3operators"} ಬ್ಲಾಕ್,‌ ಮತ್ತು `less than`{:class="block3operators"} ಬ್ಲಾಕ್‌ ಸೇರಿಸಿ. ಲೆಕ್ಕಾಚಾರವನ್ನು ಹೊಂದಿಸಿ `mature trees`{:class="block3variables"} `greater than`{:class="block3operators"} `0` `and`{:class="block3operators"} `mature trees`{:class="block3variables"} `less than`{:class="block3operators"} `10`. `say`{:class="block3looks"} `Global warming is at dangerous levels.` `for 2 seconds`{:class="block3looks"} ನ್ನು ಸೇರಿಸಿ:

![Maya ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/maya-sprite.png)

```blocks3
when flag clicked
set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet.] for (4) seconds
forever
if {(mature trees) = [0]} then
say [Our planet needs more trees.] for (2) seconds
end
+ if {{(mature trees)>[0]} and {(mature trees)<[10]}} then
say [Global warming is at dangerous levels.] for (2) seconds
end
end
```

--- /task ---

ಇನ್ನೊಂದು ವೀಕ್ಷಣಾ ಸಂದೇಶವನ್ನು ಸೇರಿಸಿ.

--- task ---

ಕೊನೆಯ `if ... then`{:class="block3control"} ಬ್ಲಾಕ್‌ ಮೇಲೆ ರೈಟ್‌-ಕ್ಲಿಕ್‌ ಮಾಡಿ, ಮತ್ತು ಮೆನುನಿಂದ **Duplicate** ಆಯ್ಕೆ ಮಾಡಿ. ನಿಮ್ಮ ನಕಲು ಬ್ಲಾಕ್‌ಗಳನ್ನು ಕೊನೆಯ `if ... then`{:class="block3control"} ಬ್ಲಾಕ್‌ ಕೆಳಗೆ ಸೇರಿಸಿ, ಮತ್ತು ಮೌಲ್ಯಗಳನ್ನು `0` ಮತ್ತು `10` ದಿಂದ `50` ಮತ್ತು `60` ರವರೆಗೆ ಬದಲಾಯಿಸಿ. `say`{:class="block3looks"} ಬ್ಲಾಕ್‌ನಲ್ಲಿ ಏನು ಎಚ್ಚರಿಕೆ ಸಂದೇಶ ಪ್ರದರ್ಶಿಸಬೇಕೆಂಬುವುದರ ಕುರಿತು ಆಲೋಚಿಸಿ:

![Maya ಸ್ಪ್ರೈಟ್ ಚಿತ್ರ](images/maya-sprite.png)

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

ನಿಮ್ಮ ಸಾದೃಶ್ಯವನ್ನು ಪರೀಕ್ಷಿಸಿ. ಮರಗಳ ಸಂಖ್ಯೆ ನಿಮ್ಮ `if ... then`{:class="block3control"} ಬ್ಲಾಕ್‌ಗಳ ಶ್ರೇಣಿಗೆ ಬಂದಾಗ, **Maya** ಸ್ಪ್ರೈಟ್‌ ಒಂದು ವೀಕ್ಷಣಾ ಸಂದೇಶವನ್ನು ಹೇಳುತ್ತದೆ.

--- /task ---

--- save ---
