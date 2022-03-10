## पेड़ों की गिनती करें

वैज्ञानिक पेड़ों और वन्यजीवों की निगरानी करते हैं। वे पेड़ों और आसपास के क्षेत्रों के आवरण (आकार), विविधता और स्वास्थ्य को रिकॉर्ड करते हैं। ऐसा करने से वे वनोन्मूलन के वास्तविक प्रभाव को देख सकते हैं। विमानों और उपग्रहों के साथ-साथ सेंसर और जमीन पर मौजूद लोगों से भी प्रेक्षण किए जा सकते हैं। लोग अपने निष्कर्षों का उपयोग यह देखने के लिए कर सकते हैं कि पेड़ों की सुरक्षा के लिए अतिरिक्त उपायों की आवश्यकता कहां है। उदाहरण के लिए, पेड़ों को फलने-फूलने के लिए जंगल के चारों ओर बाड़ का निर्माण, या आग को देखने और रोकने में मदद करने के लिए अधिक अग्निशामकों को नियुक्त करना।

इस चरण में, आप अपने सिमुलेशन में पेड़ों की निगरानी एक वेरिएबल के माध्यम से करेंगे जो पेड़ों की संख्या को संग्रहीत करता है और पर्यावरण में परिवर्तन को दर्शाता है।

--- task ---

पूर्ण विकसित पेड़ों की संख्या को संग्रहित करने के लिए एक नया `variable`{:class="block3variables"} बनाएं। इस वेरिएबल को `mature trees`{:class="block3variables"} कहें।

--- /task ---

सिमुलेशन `0` से शुरू होने पर पेड़ों की संख्या रीसेट करें।

--- task ---

`when green flag clicked`{:class="block3events"} ब्लॉक के नीचे `mature trees`{:class="block3variables"} वेरिएबल को `0` पर सेट करें:

![Tree स्प्राइट की छवि](images/tree-sprite.png)

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

सुनिश्चित करें कि आपका काउंटर यह रिकॉर्ड करता है कि सिमुलेशन चलने के दौरान कितने पेड़ बनाए गए हैं।

--- task ---

अपनी `when I start as a clone`{:class="block3control"} स्क्रिप्ट ढूंढें और अंत में एक `change mature trees by 1`{:class="block3variables"} ब्लॉक जोड़ें:

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
+ change (mature trees) by (1)
```

--- /task ---

अब आप अपने नए पेड़ों की गिनती कर सकते हैं, हालांकि वे सभी पेड़ जीवित नहीं रहेंगे। नए पेड़ों के जीवित रहने की दर 80 प्रतिशत होने का अनुमान है, जिसका अर्थ है कि लगाए गए प्रत्येक 10 में से 2 पेड़ पूर्ण विकसित होने से पहले ही प्राकृतिक कारणों से मर जाएंगे। आप इसे अपने सिमुलेशन में प्रतिबिंबित नहीं करने जा रहे हैं, लेकिन यह जानना महत्वपूर्ण है कि सभी नए पेड़ प्राकृतिक रूप से जीवित नहीं रहते हैं।

मानव वनोन्मूलन के माध्यम से परिपक्व पेड़ों को भी काटा जा सकता है। यह दिखाने के लिए, परिपक्व पेड़ों की गिनती कम करें यदि एक पेड़ को **Tree Feller** स्प्राइट द्वारा छुआ गया है।

--- task ---

अपने कोड के अंत में एक `wait until`{:class="block3control"} ब्लॉक जोड़ें, और इस ब्लॉक के अंदर एक `touching Tree Feller`{:class="block3sensing"} ब्लॉक जोड़ें। एक `change mature trees by 1`{:class="block3variables"} ब्लॉक जोड़ें और मान को `-1` में बदलें। पेड़ को हटाने के लिए `delete this clone`{:class="block3control"} ब्लॉक जोड़ें:

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
+ wait until {touching [Tree Feller v]?}
+ change (mature trees) by (-1)
+ delete this clone
```

--- /task ---

पेड़ प्राकृतिक वनोन्मूलन से भी मर सकते हैं, चाहे वे परिपक्व हों या अभी भी बढ़ रहे हों। यह दिखाने के लिए, परिपक्व पेड़ों की गिनती कम करें यदि एक पेड़ को **Natural Disaster** स्प्राइट द्वारा छुआ गया है।

--- task ---

`when I start as a clone`{:class="block3control"} ब्लॉक के साथ एक नई स्क्रिप्ट प्रारंभ करें। अपने कोड के अंत में एक `wait until`{:class="block3control"} ब्लॉक जोड़ें, और इस ब्लॉक के अंदर एक `touching Natural Disaster`{:class="block3sensing"} ब्लॉक जोड़ें। एक `if ... then`{:class="block3control"} ब्लॉक जोड़ें `size`{:class="block3looks"} `=`{:class="block3operators"} `20` शर्त के साथ।

`if ... then`{:class="block3control"} ब्लॉक के अंदर एक `change mature trees by 1`{:class="block3variables"} ब्लॉक जोड़ें, ताकि परिपक्व पेड़ों की संख्या केवल तभी कम हो जब यह पूर्ण विकसित वृक्ष थे। पेड़ को हटाने के लिए `delete this clone`{:class="block3control"} ब्लॉक जोड़ें:

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
