## मानवी जंगलतोड

मानवाने झाडे तोडण्याची अनेक कारणे आहेत. फर्निचर तयार करण्यासाठी, इमारती बनवण्यासाठी किंवा इंधन म्हणून जाळण्यासाठी लाकडाची आवश्यकता असू शकते. पर्यायाने, पिके वाढवण्यासाठी, गुरे चरण्यासाठी किंवा इमारती बांधण्यासाठी जंगलात व्यापलेली जमीन आवश्यक असू शकते.

या टप्प्यात, तुम्हाला आवश्यक असलेली झाडे मिळवण्यासाठी **Tree Feller** स्प्राइट तुम्ही कोड कराल आणि जंगलात फिरून मानवी जंगलतोड कराल.

प्रत्येक वेळी क्लिक केल्यावर किती झाडांची गरज आहे हे विचारण्यासाठी **Tree Feller** स्प्राईट कोड करा.

--- task ---

**Tree Feller** स्प्राईटवर क्लिक करा आणि `when this sprite clicked`{:class="block3events"} ब्लॉकसह नवीन स्क्रिप्ट चालू करा. ` तुमचे नाव काय विचारा जोडा? आणि `{:class="block3sensing"} ब्लॉकची प्रतिक्षा करा आणि टेक्स्ट बदला `How many trees are needed? हे विचारण्यासाठी (max 20)`:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
```

--- /task ---

पुढे, पुढील प्रश्न विचारण्यातून इनपुट ठेवण्यासाठी व्हेरिएबलची तुम्हाला आवश्यकता आहे ` किती झाडांची आवश्यकता आहे? (max 20)`.

--- task ---

नवीन `variable`{:class="block3variables"} तयार करा आणि त्याला `trees needed` म्हणा.

--- /task ---

प्रत्येक वेळी, कोणीतरी जास्त झाडांची विनंती सबमिट केल्यावर, **Tree Feller** स्प्राईटने आवश्यक झाडांच्या संख्येसाठी संख्या जोडायला हवी.

--- task ---

`trees needed`{:class="block3variables"} व्हेरिएबलमध्ये तुमच्या प्रश्नाचे उत्तर स्टोअर कऱण्यासाठी, `change trees needed by 1`{:class="block3variables"} ब्लॉक जोडा आणि त्यामध्ये `answer`{:class="block3sensing"} ब्लॉक ड्रॅग करा जेथे तो म्हणतो`1`{:class="block3variables"}:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
+ change [trees needed v] by (answer)
```

--- /task ---

झाडे मोठी आणि जड असल्यामुळे, विनंती करता येणारी अधिकतम संख्या 20 सेट करायला हवी.

--- task ---

तुमच्या कोडच्या शेवटी `if ... then`{:class="block3control"} ब्लॉक जोडा स्थिती `trees needed`{:class="block3variables"} `greater than`{:class="block3operators"} `20` सह. `if ... then`{:class="block3control"} ब्लॉकच्या आत,`set trees needed to`{:class="block3variables"} `20` जोडा:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
change [trees needed v] by (answer)
+ if {(trees neeed) > (20)} then
set (trees needed v) to (20)
end
```

--- /task ---

सिम्युलेशन सुरू करण्यासाठी हिरवा झेंडा क्लिक केल्यावर प्रत्येक वेळी आवश्यक असलेल्या झाडांची संख्या रीसेट करा, त्यामुळे ते नवीन विनंतीसाठी तयार व्हेरिएबल पुसेल.

--- task ---

`when green flag clicked`{:class="block3control"} ब्लॉकसह नवीन स्क्रिप्ट चालू करा, आणि`set trees needed to 0`{:class="block3variables"} ब्लॉक जोडा:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when flag clicked
set [trees needed v] to (0)
```

--- /task ---

--- task ---

तुमचे सिम्युलेशन रन करा. **Tree Feller** स्प्राईटवर क्लिक करा आणि झाडांच्या संख्येची विनंती करा. `trees needed`{:class="block3variables"} व्हेरिएबलबाबत प्रत्येक वेळी काय घडते ते बघण्यासाठी वेगवेगळ्या संख्या एंटर करा.

--- /task ---

**Tree Feller** स्प्राईट मोठ्या झाडाला स्पर्श करतो तेव्हा, आवश्यक असलेल्या झाडांची संख्या कमी होईल.

--- task ---

**Tree** स्प्राईटवर क्लिक करा आणि स्क्रिप्टला `change trees needed by`{:class="block3variables"} `-1` जोडा त्यानंतर `touches Tree Feller`{:class="block3sensing"} जोडा.

`wait until`{:class="block3control"} ब्लॉकची `touches Tree Feller`{:class="block3sensing"} `and`{:class="block3operators"} `trees needed`{:class="block3variables"} `>`{:class="block3operators"} `0` बनण्यासाठी स्थिती बदला

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

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
+ wait until {{touching [Tree Feller v]?} and {(trees needed)>(0)}}
+ change (trees needed) by (-1)
change (mature trees) by (-1)
delete this clone
```

--- /task ---

Stage बऱ्याच `variables`{:class="block3variables"} सह क्राऊड झालेला दिसत आहे. त्यांना स्थान द्या जेणेकरून ते तुमच्या सिम्युलेशनमध्ये अधिक चांगल्या ठिकाणी दिसतील आणि जे वृक्ष व्यवस्थापनाशी संबंधित मूल्ये दर्शवत नाहीत ते लपवा.

--- task ---

`Variables`{:class="block3variables"} ब्लॉक्स मेनूवर जा आणि `trees needed`{:class="block3variables"} व्हेरिएबलवर अनटीक करा.

**tree management** स्लाइडर व्हेरिएबल आणि **mature trees** काऊंटर व्हेरिएबल Stage च्या खालच्या कोपऱ्यात ड्रॅग करा.

![व्हेरिएबल सह stage ची इमेज](images/stage-with-variables.png)

--- /task ---

**Tree Feller** स्प्राईटसाठी प्रत्येक वेळी सिम्युलेशन चालू झाल्यावर सुरूवातीची पोजिशन सेट करा.

--- task ---

**Tree Feller** स्प्राईटवर क्लिक करा आणि `when green flag clicked`{:class="block3events"} स्क्रिप्टमध्ये,`set rotation style left-right`{:class="block3motion"} ब्लॉक इंसर्ट करा जेणेकरून**Tree Feller** स्प्राईट वरच्या बाजूला खाली जाणार नाही. **Tree Feller** स्प्राईट डाव्या हाताच्या कोपऱ्यात वर चालू होण्यासाठी `go to x:0 y:0`{:class="block3motion"} ब्लॉक जोडा आणि व्हॅल्यू `-200` आणि `150` ला बदला. `point in direction 90`{:class="block3motion"} ला स्प्राईट आणा:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when flag clicked
set [trees needed v] to (0)
+ set rotation style [left-right v]
+ go to x: (-200) y: (150)
+ point in direction (90)
```

--- /task ---

**Tree Feller** स्प्राईट पुरेशी झाडे तोडेपर्यंत जंगलातून डावीकडून उजवीकडे आणि पुन्हा मागे हलेल. ऑपरेटरचा वापर करा जेणेकरून **Tree Feller** स्प्राईटला आवश्यक झाडांची संख्या शून्य असेल तेव्हा त्याने पुरेशी झाडे गोळा केली आहेत हे माहिती असेल.

--- task ---

`when this sprite clicked`{:class="block3events"} स्क्रिप्टमध्ये, `repeat until`{:class="block3control"} ब्लॉक जोडा आणि आत समान `=`{:class="block3operators"} ब्लॉक ड्रॅग करा. स्थिती जोडा `trees needed`{:class="block3variables"} `=`{:class="block3operators"} `0`.

लूपमध्ये, `move 10 steps`{:class="block3motion"} ब्लॉक जोडा आणि व्हॅल्यू `4` ला बदला:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
+ repeat until {(trees needed) = (0)}
move (4) steps
end
```

--- /task ---

--- task ---

तुमचे सिम्युलेशन रन करा. **Tree Feller** स्प्राईटवर क्लिक करा आणि झाडांच्या संख्येची विनंती करा. **Tree Feller** स्प्राईट पूर्ण Stage मधून हलतो का?

--- /task ---

याक्षणी, **Tree Feller** स्प्राईट केवळ Stage च्या वरच्या भागात हलतो. तो Stage च्या कडेला स्पर्श करत असल्यास तुम्हाला स्प्राईट सेंस तयार करणे आवश्यक आहे, जेणेकरून त्याला दिशा बदलणे माहिती असेल.

--- task ---

`if ... then`{:class="block3control"} ब्लॉक `touching edge`{:class="block3sensing"} स्थितीसह जोडा. तुमच्या `if`{:class="block3control"} लूपच्या आत, दोन `Motion`{:class="block3motion"} ब्लॉक्स जोडा:  `turn right by`{:class="block3motion"} `180` `degrees`{:class="block3motion"} आणि `change y by`{:class="block3motion"} `-40`:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
+ if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
end
```

--- /task ---

**Tree Feller** स्प्राईट Stage च्या खाली पोहोचला, तर तो पुन्हा वरच्या भागातून चालू करणे आवश्यक आहे.

--- task ---

दुसरा `if ... then`{:class="block3control"} ब्लाॉक `y position`{:class="block3motion"} `<`{:class="block3operators"} `-120` स्थितीसह जोडा. तुमच्या `if ... then`{:class="block3control"} लूपच्या आत, `go to x:`{:class="block3motion"} `-200` `y:`{:class="block3motion"} `150` जोडा जेणेकरून तो सुरूवात स्थितीला परत हलतो:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
+ if {(y position)<(-120)} then
go to x: (-200) y: (150)
end
end
```

--- /task ---

पुढे, **Tree Feller** स्प्राईटने पुरेशी झाडे कधी तोडली हे तुम्ही शोधणे आवश्यक आहे. विनंत्या पूर्ण झाल्याची घोषणा करण्यासाठी **Tree Feller** स्प्राईट मिळवा.

--- task ---

`Looks`{:class="block3looks"} ब्लॉक तुमच्या कोडच्या शेवटी जोडा जेणेकरून **Tree Feller** स्प्राईट `say`{:class="block3looks"} `विनंत्या पूर्ण झाल्या.` `for 2 seconds`{:class="block3looks"}:

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {(y position)<(-120)} then
go to x: (-200) y: (150)
end
end
+ say [Requests completed.] for (2) seconds
```

--- /task ---

--- task ---

तुमचे सिम्युलेशन रन करा. **Tree Feller** स्प्राईटवर क्लिक करा आणि झाडांच्या संख्येची विनंती करा. **Tree Feller** स्प्राईटने पुरेशी झाडे गोळा केल्यास, ते तुम्हाला पूर्ण झाल्याचे सांगेल.

--- /task ---

विनंत्या पूर्ण झाल्यावर, पुढील विनंतीसाठी तयार असलेल्या झाडाच्या क्षेत्राच्या बाजूला जाण्यासाठी **Tree Feller** स्प्राइट मिळवा.

--- task ---

दोन `Motion`{:class="block3motion"} ब्लॉक्स जोडा: `set x to`{:class="block3motion"} `-200` ब्लॉक आणि `point in direction 90`{:class="block3motion"} ब्लॉक.

![Tree Feller स्प्राईटची इमेज](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
change [trees needed v] by (answer)
if {(trees needed) > (20)} then
set (trees needed v) to (20)
end
repeat until {(trees needed) = (0)}
move (4) steps
if {touching [edge v]?} then
turn right (180) degrees
change y by (-40)
end
if {(y position)<(-120)} then
go to x: (-200) y: (150)
end
end
say [Requests completed.] for (2) seconds
+ set x to (-200)
+ point in direction (90)
```

--- /task ---

--- task ---

तुमचे सिम्युलेशन रन करा. लाकडाच्या वेगवेगळ्या प्रमाणाची विनंती करण्यासाठी **Tree Feller** स्प्राईटवर क्लिक करा.

![झाडे तोडल्याची घोषणा करणाऱ्या Tree Feller ची इमेज](images/feller-trees-felled.png)

--- /task ---

--- save ---
