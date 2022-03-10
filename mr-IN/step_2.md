## काही झाडे लावा

पृथ्वीच्या 30 टक्के भूभाग झाडांनी व्यापलेला आहे हे तुम्हाला माहित आहे का? आपण आता आपल्या स्थानिक झाडांची काळजी जशी घेऊ, त्याप्रमाणे आपल्या ग्रहावर परिणाम होईल. या टप्प्यात, तुम्ही विविध झाडांच्या विविध प्रकारांसह झाडांचे क्षेत्र तयार करण्यासाठी कोड जोडाल.

--- task ---

**ऑनलाईन:** Scratch मधील [स्टार्टर प्रोजेक्ट](http://rpf.io/tree-life-simulator-on){:target="_blank"} उघडा.

**ऑफलाईन:** Scratch ऑफलाईन एडिटरमधील [प्रोजेक्ट स्टार्टर फाईल](http://rpf.io/p/en/tree-life-simulator-get){:target="_blank"} उघडा. तुम्हाला आवश्यकता असल्यास, तुम्ही [येथे Scratch डाऊनलोड आणि इंस्टॉल करू शकता](https://scratch.mit.edu/download){:target="_blank"}.

तुम्हाला हिरव्या गवताळ प्रदेशाचे बॅकग्राऊंड दिसायला हवे.

![स्टार्टर प्रोजेक्ट](images/starter_project.png)

--- /task ---

Scratch मध्ये, तुम्ही एका स्प्राईटच्या 300 पर्यंत प्रती तयार करू शकता! याला **क्लोनिंग** म्हणतात. **Tree** स्प्राईटला तुमचा कोड जोडणे हे तुमचे कार्य आहे जेणेकरून तो Stage वर स्वतःच क्लोन्स निर्माण करेल.

--- task ---

Sprites pane वर जा, आणि **Tree** स्प्राईटवर क्लिक करा. कोड एरियात `when green flag clicked`{:class="block3events"} ब्लॉक आणि `forever`{:class="block3control"} ब्लॉक ड्रॅग करा. `forever`{:class="block3control"} ब्लॉकमध्ये, `go to x:`{:class="block3motion"} `0` `y:`{:class="block3motion"} `0` ब्लॉक जोडा आणि `create clone of myself`{:class="block3control"} ब्लॉक:

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

```blocks3
when flag clicked
forever
go to x:(0) y:(0)
create clone of [myself v]
end
```

--- /task ---

पुढे, Stage वर कोणत्याही पोजिशनमध्ये क्लोन केलेली झाडे लावा.

--- task ---

झाडे वाढत आहेत का हे बघण्यासाठी `pick random`{:class="block3operators"} ब्लॉक तुमच्या दोन्ही `x:`{:class="block3motion"} आणि `y:`{:class="block3motion"} व्हॅल्यूजला जोडा. `x:`{:class="block3motion"} कोऑर्डीनेटर्स बदला `pick random`{:class="block3operators"} `-150` `to`{:class="block3operators"} `200`. `y:`{:class="block3motion"} कोऑर्डीनेटर्स बदला `pick random`{:class="block3operators"} `-120` `to`{:class="block3operators"} `120`:

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

```blocks3
when flag clicked
forever
+ go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
create clone of [myself v]
end
```

--- /task ---

प्राण्यांची संख्या वाढवणे, पर्यावरणाचा पुनर्संचय करणे, आणि लोकांना लाभ होण्यासाठी विविध प्रकारची झाडे तुम्ही लावणे महत्वाचे आहे. उदाहरणार्थ, कोआला ऑस्ट्रेलियातील ब्रॉडलीफ एव्हरग्रीनवर अवलंबून असतो, तर मादागास्करमधील लेमरला बेटावर वाढणारी पानझडी झाडे आवश्यक असतात.

**Tree** स्प्राईटला तीन कॉश्चुम असतात: **tree 1**, **tree 2**, and **tree 3**. ते बघण्यासाठी **Costumes** टॅबवर क्लिक करा.

**Code** टॅबवर पुन्हा क्लिक करा आणि झाडांचे स्वरूप बदलणे आणि एरियामध्ये विविधता जोडण्यासाठी `random`{:class="block3operators"} ऑपरेटरचा वापर करा.

--- task ---

`when I start as a clone`{:class="block3control"} ब्लॉकसह नवीन स्क्रिप्ट चालू करा. त्याखाली `switch costume to`{:class="block3looks"} ब्लॉक जोडा. `pick random 1 to 10`{:class="block3operators"} ब्लॉक `switch costume to`{:class="block3looks"} ब्लॉकमध्ये ड्रॅग करा. `1` आणि `10` ते `1` आणि `3` व्हॅल्यूज बंद करा:

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
```

--- /task ---

--- task ---

हिरव्या झेंड्यावर क्लिक करून तुमचा सिम्युलेशन तपासा. तुमच्याकडे विविध प्रकारची झाडे आहेत याची खात्री करा.

![पहिल्या झाडाची इमेज ](images/first-trees.png)

--- /task ---

झाडे फक्त पूर्ण वाढलेली दिसत नाहीत, ती कालांतराने मोठी होतात. तुम्हाला `repeat until`{:class="block3control"} लूप सेट करण्याची आवश्यकता आहे जेणेकरून तुम्ही साईज 20 टक्के होईपर्यंत झाडाची वाढण्याची साईज बदलू शकता.

--- task ---

`set size to 100`{:class="block3looks"} (टक्के) ब्लॉक मिळवा, परंतु व्हॅल्यू `0` ला बदला जेणेकरून **Tree** स्प्राईट शून्यापासून चालू करेल. `repeat until`{:class="block3control"} ब्लॉक जोडा आणि बरोबर `=`{:class="block3operators"} चा ब्लॉक आत ड्रॅग करा. स्थिती जोडा `size`{:class="block3looks"} `=`{:class="block3operators"} `20`:

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

```blocks3
when I start as a clone
switch costume to (pick random (1) to (3))
+ set size to (0)%
+ repeat until {(size)=[20]}
end
```

--- /task ---

झाडाला रीसाईज होऊ द्या आणि तो कसा वाढतो त्याची प्रतीक्षा करा.

--- task ---

लूपमध्ये `change size by 10`{:class="block3looks"} ब्लॉक जोडा आणि व्हॅल्यू `1` मध्ये बदला. `wait 1 seconds`{:class="block3control"} ब्लॉक जोडा आणि व्हॅल्यू `0.1` मध्ये बदला जेणेकरून तो तात्काळ बदलेल:

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

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

तुमच्या सिम्युलेशनची पुन्हा चाचणी करा. तुमची झाडे वाढतील, परंतु जेव्हा तुमचा पुढील क्लोन वाढतो त्याचवेळी पूर्ण वाढलेले झाड सुद्धा दिसते.

--- /task ---

नवीन क्लोन चालू होईपर्यंत झाड लपवा.

--- task ---

`hide`{:class="block3looks"} ब्लॉक जोडा तुमची `when green flag clicked`{:class="block3events"} स्क्रिप्ट चालू करण्यासाठी, आणि `show`{:class="block3looks"} ब्लॉक जोडा तुमची `when I start as a clone`{:class="block3control"} स्क्रिप्ट चालू करण्यासाठी.

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

तुमच्या सिम्युलेशनची पुन्हा चाचणी करा. तुमची झाडे आता खऱ्या जीवनात वाढतील तशी वाढायला हवी.

--- /task ---

--- save ---
