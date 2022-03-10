## नैसर्गीक जंगलतोड

जेव्हा एखादी नैसर्गिक आपत्ती — जसे की दुष्काळ, जंगलातील आग किंवा वादळ — जमिनीचे क्षेत्र उद्ध्वस्त करते तेव्हा जंगलतोड होऊ शकते. हे कॅम्पफायर सारख्या मानवी कृतींद्वारे सुद्धा प्रवर्तीत केले जाऊ शकते, परंतु कोरड्या हंगामासारख्या नैसर्गिक परिस्थितीमुळे ते लवकर पसरते. हे विशेषतः प्राणघातक असू शकते कारण, प्रभावित झालेल्या विस्तृत क्षेत्रामध्ये, संपूर्ण प्रजाती त्यांच्या निवासस्थानाच्या नाशासह अदृश्य होऊ शकतात.

जंगलातून कोठेही फिरणाऱ्या नैसर्गिक आपत्ती प्रभाव सिम्युलेट करा. सिम्युलेशनच्या सुरूवातीला **Natural Disaster** स्प्राईट लपवा.

--- task ---

**Natural Disaster** स्प्राईटवर क्लिक करा, त्यानंतर कोड एरियामध्ये `when green flag clicked`{:class="block3events"} ब्लॉक जोडा, त्यानंतर `hide`{:class="block3looks"} ब्लॉक जोडा:

![Natural Disaster स्प्राईटची इमेज](images/natural-disaster-sprite.png)

```blocks3
when flag clicked
hide
```

--- /task ---

**Natural Disaster** स्प्राईट स्क्रीनच्या वरपासून खालपर्यंत हलेल.

--- task ---

`forever`{:class="block3control"} ब्लॉक तुमच्या कोडच्या शेवटी जोडा. त्यामध्ये, `go to x:0 y:0`{:class="block3motion"} ब्लॉक जोडा, आणि `y:`{:class="block3motion"} व्हॅल्यू `200` मध्ये बदला. `show`{:class="block3looks"} ब्लॉक जोडा, त्यानंतर `glide 1 secs to x:0 y:0`{:class="block3motion"} जोडा, आणि दुसरी व्हॅल्यू `3` मध्ये `y:`{:class="block3motion"} व्हॅल्यू `-200` मध्ये बदला:

![Natural Disaster स्प्राईटची इमेज](images/natural-disaster-sprite.png)


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

**Natural Disaster** स्प्राईटला तीन कॉश्चुम आहेत: **Drought**, **Forest Fire**, आणि **Tornado**, कारण झाडांना अनेक प्रकारच्या नैसर्गीक आपत्तींचा फटका बसू शकतो. कोड जोडा जेणेकरून सिम्युलेशनमध्ये अनेक आपत्ती प्रकार असतील.

--- task ---

 कॉश्चुम बघण्यासाठी **Costumes** टॅबवर क्लिक करा. परत **Code** टॅबवर क्लिक करा आणि `hide`{:class="block3looks"} ब्लॉक जोडा जेव्हा तो स्क्रीनच्या खालच्या भागात पोहोचतो, त्यानंतर `next costume`{:class="block3looks"} ब्लॉकवर:

![Natural Disaster स्प्राईटची इमेज](images/natural-disaster-sprite.png)


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

तुमच्या प्रोजेक्टची तपासणी करा. **Natural Disaster** स्प्राईट आता वरपासून खालपर्यंत हलतो, आणि प्रत्येक वेळी कॉश्चुम बदलतो.

![stage वरील Natural Disaster स्प्राईटची इमेज](images/disaster-on-stage.png)

--- /task ---

वैज्ञानीक काहीवेळा नैसर्गिक आपत्ती कधी येतील याचा अंदाज लावू शकतात, हे कठीण असले तरीही त्यांची वेळ नेहमी सिम्युलेशनप्रमाणे स्पष्ट नसते. आता, वास्तव जीवनाप्रमाणे न सांगण्यायोग्य स्प्राईट दिसण्यासाठी **Natural Disaster** स्प्राईटला कोणत्याही वेळा जोडा.

--- task ---

कोणत्याही वेळा तयार करण्यासाठी `wait 1 seconds`{:class="block3control"} ब्लॉक तुमच्या `forever`{:class="block3control"} ब्लॉकच्या वरच्या भागात जोडा. `pick random`{:class="block3operators"} ऑपरेटर `wait`{:class="block3control"} ब्लॉकमध्ये ड्रॅग करा, आणि व्हॅल्यू `10` and `20` मध्ये बदला:

![Natural Disaster स्प्राईटची इमेज](images/natural-disaster-sprite.png)


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

**Natural Disaster** स्प्राईटच्या हालचालीमध्ये यादृच्छिकता जोडा.

--- task ---

`pick random`{:class="block3operators"} ऑपरेटर `x:`{:class="block3motion"} हा दोन्ही `go to`{:class="block3motion"} ब्लॉक आणि `glide`{:class="block3motion"} ब्लॉकमध्ये ड्रॅग करा. `-200` आणि `200` मध्ये प्रत्येक व्हॅल्यू बदला:

![Natural Disaster स्प्राईटची इमेज](images/natural-disaster-sprite.png)


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

तुमच्या कोडची पुन्हा तपासणी करा. तुमच्या **Natural Disaster** स्प्राईटने आता तो कोणत्याही पोजिशन मधून दुसऱ्या कोणत्याही पोजिशन मध्ये जाण्याआधी 10 आणि 20 दरम्यान प्रतिक्षा करायला हवी. तो प्रत्येक वेळी कॉश्चुम बदलतो आणि तो स्पर्श करणारी कोणतेही झाडे काढतो.

--- /task ---

--- save ---
