## मानव द्वारा जंगलों का वनोन्मूलन

मनुष्य द्वारा पेड़ों को काटने के कई कारण हैं। फर्नीचर बनाने, भवन बनाने या जलाऊ लकड़ी के रूप में जलाने के लिए लकड़ी की आवश्यकता हो सकती है। वैकल्पिक रूप से, जंगल द्वारा उपयोग की जाने वाली भूमि की आवश्यकता फसल उगाने, मवेशियों को चराने या भवनों के निर्माण के लिए हो सकती है।

इस चरण में, आप **Tree Feller** स्प्राइट को कोड करेंगे, आवश्यक पेड़ों की मात्रा प्राप्त करने के लिए, और और मानव द्वारा वनोन्मूलन के कारणों में से जाएँगे।

**Tree Feller** स्प्राइट को यह पूछने के लिए कोड करें कि हर बार क्लिक करने पर कितने पेड़ों की आवश्यकता होती है।

--- task ---

**Tree Feller** स्प्राइट पर क्लिक करें और `when this sprite clicked`{:class="block3events"} ब्लॉक के साथ एक नई स्क्रिप्ट शुरू करें। एक `ask What is your name? and wait`{:class="block3sensing"} की प्रतीक्षा करें और टेक्स्ट को `How many trees are needed? (max 20)` पूछने के लिए बदलें:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed? (max 20)] and wait
```

--- /task ---

इसके बाद, आपको प्रश्न पूछने से इनपुट रखने के लिए एक वेरियबल `How many trees are needed? (max 20)` की आवश्यकता है.

--- task ---

एक नया `variable`{:class="block3variables"} बनाएं, जिसे `trees needed` कहा जाता है।

--- /task ---

हर बार जब कोई अधिक पेड़ों के लिए अनुरोध करता है, तो **Tree Feller** स्प्राइट को उस संख्या को आवश्यक पेड़ों की मात्रा में जोड़ना चाहिए।

--- task ---

अपने प्रश्न के उत्तर को `trees needed`{:class="block3variables"} वेरिएबल में संग्रहीत करने के लिए, एक `change trees needed by 1`{:class="block3variables"} ब्लॉक जोड़ें और `answer`{:class="block3sensing"} ब्लॉक को वहाँ खीचें जहाँ यह कहता है `1`{:class="block3variables"}:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
+ change [trees needed v] by (answer)
```

--- /task ---

चूंकि पेड़ बड़े और भारी होते हैं, इसलिए अनुरोध की जा सकने वाली अधिकतम संख्या 20 पर सेट की जानी चाहिए।

--- task ---

आपके कोड के अंत में एक `if ... then`{:class="block3control"} ब्लॉक जोड़ें `trees needed`{:class="block3variables"} `greater than`{:class="block3operators"} `20` शर्त के साथ। `if ... then`{:class="block3control"} ब्लॉक के अंदर `set trees needed to`{:class="block3variables"} `20` ब्लॉक जोड़ें:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

```blocks3
when this sprite clicked
ask [How many trees are needed?] and wait
change [trees needed v] by (answer)
+ if {(trees neeed) > (20)} then
set (trees needed v) to (20)
end
```

--- /task ---

सिमुलेशन शुरू करने के लिए हर बार हरे झंडे पर क्लिक करने पर आवश्यक पेड़ों की संख्या को रीसेट करें, इसलिए यह एक नए अनुरोध के लिए वेरियबल को खाली करके तैयार करता है ।

--- task ---

`when green flag clicked`{:class="block3control"} ब्लॉक के साथ एक नई स्क्रिप्ट शुरू करें और एक `set trees needed to 0`{:class="block3variables"} ब्लॉक जोड़ें:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

```blocks3
when flag clicked
set [trees needed v] to (0)
```

--- /task ---

--- task ---

अपना सिमुलेशन चलाएं। **Tree Feller** स्प्राइट पर क्लिक करें और कई पेड़ों का अनुरोध करें। यह देखने के लिए की `trees needed`{:class="block3variables"} वेरियबल को क्या होता है, यह देखने के लिए विभिन्न संख्याएं दर्ज करें।

--- /task ---

जब **Tree Feller** स्प्राइट एक परिपक्व पेड़ को छूता है, तो आवश्यक पेड़ों की संख्या कम हो जाएगी।

--- task ---

**Tree** sprite पर क्लिक करें और स्क्रिप्ट में `change trees needed by`{:class="block3variables"} `-1` जोड़ें जब वह `touches Tree Feller`{:class="block3sensing"} करता है।

`wait until`{:class="block3control"} की शर्त को बदलें ताकि यह `touches Tree Feller`{:class="block3sensing"} `and`{:class="block3operators"} `trees needed`{:class="block3variables"} `>`{:class="block3operators"} `0` हो जाए

![Tree स्प्राइट की छवि](images/tree-sprite.png)

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

मंच इतने सारे `variables`{:class="block3variables"} के साथ बहुत भीड़भाड़ वाला दिख रहा है। उन्हें इस तरह व्यवस्थित करें ताकि वे आपके सिमुलेशन में बेहतर स्थानों पर दिखाई दें, और उन पेड़ों को छुपाएं जो वृक्ष प्रबंधन से संबंधित मान नहीं दिखाते हैं।

--- task ---

`Variables`{:class="block3variables"} ब्लॉक मेन्यू पर जाएं और `trees needed`{:class="block3variables"} वेरिएबल को अचिह्नित करें।

**tree management** स्लाइडर वेरिएबल और**mature trees** काउंटर वेरिएबल को Stage के निचले कोनों तक खींचें।

![वेरियबल के साथ मंच की छवि](images/stage-with-variables.png)

--- /task ---

हर बार सिमुलेशन शुरू होता है तो तब के किए **Tree Feller** स्प्राइट के लिए शुरुआती स्थिति सेट करें।

--- task ---

**Tree Feller** स्प्राइट पर क्लिक करें और `when green flag clicked`{:class="block3events"} स्क्रिप्ट में एक `set rotation style left-right`{:class="block3motion"} ब्लॉक डालें ताकि **Tree Feller** उल्टा नहीं झुकता है। **Tree Feller** स्प्राइट को बाएं हाथ के सबसे ऊपर कोने से शुरू होने के लिए, एक `go to x:0 y:0`{:class="block3motion"} ब्लॉक जोड़ें और मानों को `-200` और `150` में बदलें। स्प्राइट को `point in direction 90`{:class="block3motion"} करवाएँ:

![ree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

```blocks3
when flag clicked
set [trees needed v] to (0)
+ set rotation style [left-right v]
+ go to x: (-200) y: (150)
+ point in direction (90)
```

--- /task ---

**Tree Feller** स्प्राइट जंगल में बाएं से दाएं और फिर से तब तक घूमेगा, जब तक कि वह पर्याप्त पेड़ नहीं काट लेता। एक ऑपरेटर का उपयोग करें ताकि **Tree Feller** स्प्राइट को पता चले कि उसने पर्याप्त पेड़ एकत्र किए हैं जब आवश्यक पेड़ों की संख्या शून्य के बराबर होती है।

--- task ---

`when this sprite clicked`{:class="block3events"} स्क्रिप्ट पर एक `repeat until`{:class="block3control"} ब्लॉक जोड़ें और बराबर `=`{:class="block3operators"} ब्लॉक को अंदर खींचें। `trees needed`{:class="block3variables"} `=`{:class="block3operators"} `0` शर्त जोड़ें:

लूप के भीतर, `move 10 steps`{:class="block3motion"} ब्लॉक जोड़ें और मान को `4` में बदलें:

![Tree Fellerस्प्राइट की छवि](images/tree-feller-sprite.png)

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

अपना सिमुलेशन चलाएं। **Tree Feller** स्प्राइट पर क्लिक करें और कई पेड़ों का अनुरोध करें। क्या **Tree Feller** स्प्राइट पूरे Stage पर घूमता है?

--- /task ---

फिलहाल, **Tree Feller** sprite स्प्राइट केवल Stage के शीर्ष पर चलता है। आपको स्प्राइट को यह महसूस करने की जरूरत है अगर वह Stage के किनारे को छू रहा है, ताकि वह दिशा बदलना जानता हो।

--- task ---

एक `if ... then`{:class="block3control"} ब्लॉक जोड़ें `touching edge`{:class="block3sensing"} शर्त के साथ। अपने `if`{:class="block3control"} लूप के अंदर, दो `Motion`{:class="block3motion"} ब्लॉक जोड़ें:  `turn right by`{:class="block3motion"} `180` `degrees`{:class="block3motion"} और `change y by`{:class="block3motion"} `-40`:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

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

यदि **Tree Feller** स्प्राइट Stage के निचले भाग तक पहुँचता है, तो इसे फिर से ऊपर से शुरू करने की आवश्यकता होती है।

--- task ---

एक और `if ... then`{:class="block3control"} ब्लॉक जोड़ें `y position`{:class="block3motion"} `<`{:class="block3operators"} `-120` शर्त के साथ। आपके `if ... then`{:class="block3control"} लूप के अंदर, `go to x:`{:class="block3motion"} `-200` `y:`{:class="block3motion"} `150` ब्लॉक जोड़ें ताकि वह वापस प्रारंभिक स्थिति में आ जाए:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

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

इसके बाद, आपको यह पता लगाना होगा कि **Tree Feller** स्प्राइट ने कब पर्याप्त पेड़ काटे। **Tree Feller** स्प्राइट से यह उद्घोषणा करवाएँ की उसने सारे अनुरोध पूरे कर लिए हैं।

--- task ---

आपके कोड के अंत में एक `Looks`{:class="block3looks"} जोड़ें ताकि **Tree Feller** स्प्राइट कहेगा `say`{:class="block3looks"} `Requests completed. ` `for 2 seconds`{:class="block3looks"}:

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

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

अपना सिमुलेशन चलाएं। **Tree Feller** स्प्राइट पर क्लिक करें और कई पेड़ों का अनुरोध करें। एक बार **Tree Feller** स्प्राइट ने पर्याप्त पेड़ एकत्र कर लिए, यह आपको बताएगा कि इसका काम हो गया है ।

--- /task ---

एक बार अनुरोध पूरा हो जाने पर, **Tree Feller** स्प्राइट को पेड़ों के क्षेत्र के किनारे की ओर चलाएँ, जो अगले अनुरोध के लिए तैयार है।

--- task ---

दो `Motion`{:class="block3motion"} ब्लॉक जोड़ें: a `set x to`{:class="block3motion"} `-200` ब्लॉक और एक `point in direction 90`{:class="block3motion"} ब्लॉक।

![Tree Feller स्प्राइट की छवि](images/tree-feller-sprite.png)

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

अपने सिमुलेशन का परीक्षण करें। विभिन्न मात्रा में लकड़ी का अनुरोध करने के **Tree Feller** स्प्राइट पर कुछ बार क्लिक करें।

![पेड़ों को काटने की घोषणा करने वाले Tree Feller की छवि](images/feller-trees-felled.png)

--- /task ---

--- save ---
