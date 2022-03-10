## झाडे मोजा

वैज्ञानीक झाडे आणि वन्यजीवनाचे निरीक्षण करतात. ते झाडांचे क्षेत्र (साईज), प्रकार, आणि आरोग्य तसेच सभोवतालचे क्षेत्र यांची नोंद ठेवतात. असे करून, ते जंगलतोडीचे खरे परिणाम बघू शकतात. हवेतील विमाने आणि उपग्रह, तसेच सेन्सर्स आणि पृथ्वीवरील लोकांकडून निरीक्षणे घेतली जाऊ शकतात. झाडांचे संरक्षण करण्यासाठी अतिरिक्त उपाय कुठे आवश्यक आहेत हे पाहण्यासाठी लोक त्यांचे निष्कर्ष वापरू शकतात. उदाहरणार्थ, झाडे वाढू देण्यासाठी जंगलाभोवती कुंपण बांधणे किंवा आग शोधण्यात आणि थांबविण्यात मदत करण्यासाठी अधिक अग्निशामकांची नियुक्ती.

या टप्प्यात, तुम्ही व्हेरिएबलच्या माध्यमातून तुमच्या सिम्युलेशन मधील झाडांचे निरीक्षण कराल ज्यामध्ये झाडांची संख्या स्टोअर केली जाते आणि पर्यावरणामध्ये बदल केले जातात.

--- task ---

पूर्ण वाढलेल्या झाडांची संख्या स्टोअर करण्यासाठी नवीन `variable`{:class="block3variables"} तयार करा. या व्हेरिएबलला `mature trees`{:class="block3variables"} म्हणा.

--- /task ---

सिम्युलेशन `0` ला चालू होईल तेव्हा झाडांची संख्या रीसेट करा.

--- task ---

`when green flag clicked`{:class="block3events"} ब्लॉकच्या खाली, `mature trees`{:class="block3variables"} व्हेरिएबल `0` ला सेट करा:

![Tree स्प्राईटची इमेज](images/tree-sprite.png)

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

सिम्युलेशन चालू असताना तुमचा काउंटर किती झाडे तयार झाली याची नोंद करत असल्याची खात्री करा.

--- task ---

तुमची `when I start as a clone`{:class="block3control"} स्क्रिप्ट शोधा आणि शेवटी `change mature trees by 1`{:class="block3variables"} ब्लॉक जोडा:

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
+ change (mature trees) by (1)
```

--- /task ---

आता तुम्ही तुमची नवीन झाडे मोजू शकता, तरीसुद्धा सर्व झाडे जिवंत राहणार नाहीत. नवीन झाडांसाठी जगण्याचा दर अंदाजे 80 टक्के आहे, याचा अर्थ असा की लागवड केलेल्या प्रत्येक 10 पैकी 2 झाडे पूर्ण वाढ होण्याआधीच नैसर्गिक कारणांमुळे मरतील. तुम्ही याचे तुमच्या सिम्युलेशनमध्ये परावर्तन करणार नाही, परंतु हे जाणून घेणे महत्त्वाचे आहे की सर्व नवीन झाडे नैसर्गिकरित्या टिकत नाहीत.

मानवी जंगलतोड करून मोठी झाडे देखील तोडली जाऊ शकतात. हे दाखवण्यासाठी, जर एखाद्या झाडाला **Tree Feller** स्प्राइटने स्पर्श केला असेल तर मोठ्या झाडांची संख्या कमी करा.

--- task ---

`wait until`{:class="block3control"} ब्लॉक तुमच्या कोडच्या शेवटी जोडा, या ब्लॉकच्या आत `touching Tree Feller`{:class="block3sensing"} ब्लॉक जोडा. `change mature trees by 1`{:class="block3variables"} ब्लॉक जोडा आणि व्हॅल्यू `-1` मध्ये बदला. झाड काढण्यासाठी `delete this clone`{:class="block3control"} ब्लॉक जोडा:

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
+ wait until {touching [Tree Feller v]?}
+ change (mature trees) by (-1)
+ delete this clone
```

--- /task ---

झाडे मोठी असोत किंवा अजून वाढत असलेली असोत, नैसर्गिक जंगलतोडीमुळे झाडे देखील मरू शकतात. हे दाखवण्यासाठी, जर एखाद्या झाडाला **Natural Disaster** स्प्राइटने स्पर्श केला असेल तर झाडांची संख्या कमी करा.

--- task ---

`when I start as a clone`{:class="block3control"} ब्लॉकसह नवीन स्क्रिप्ट चालू करा. तुमच्या कोडच्या शेवटी `wait until`{:class="block3control"} ब्लॉक जोडा, आणि या ब्लॉकच्या आत `touching Natural Disaster`{:class="block3sensing"} ब्लॉक जोडा. `if ... then`{:class="block3control"} ब्लॉक स्थिती `size`{:class="block3looks"} `=`{:class="block3operators"} `20` सह जोडा.

`if ... then`{:class="block3control"} ब्लॉकच्या आत, `change mature trees by 1`{:class="block3variables"} ब्लॉक जोडा, जेणेकरून मोठ्या झाडांची संख्या केवळ ते पूर्ण वाढलेले झाड असेल तरच कमी होईल. झाड काढण्यासाठी `delete this clone`{:class="block3control"} ब्लॉक जोडा:

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
