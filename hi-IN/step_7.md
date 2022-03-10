## प्राकृतिक वनोन्मूलन

वनोन्मूलन तब हो सकती है जब एक प्राकृतिक आपदा - जैसे सूखा, जंगल की आग, या बवंडर - भूमि के एक क्षेत्र को तबाह कर देती है। यह मानव गतिविधि से भी शुरू हो सकता है, जैसे कि कैम्प फायर, लेकिन प्राकृतिक परिस्थितियों जैसे शुष्क मौसम के कारण बहुत तेजी से फैलता है। यह विशेष रूप से घातक हो सकता है, क्योंकि प्रभावित व्यापक क्षेत्र में, उनके आवासों के विनाश के साथ-साथ पूरी प्रजाति गायब हो सकती है।

प्राकृतिक आपदाओं के प्रभाव का सिमुलेशन करें जो यादृच्छिकता से गल से गुजरते हैं। सिमुलेशन की शुरुआत में **Natural Disaster** स्प्राइट छुपाएं।

--- task ---

**Natural Disaster** स्प्राइट पर क्लिक करें, फिर Code क्षेत्र में `when green flag clicked`{:class="block3events"} ब्लॉक जोड़ें, और उसके बाद एक `hide`{:class="block3looks"} ब्लॉक:

![Natural Disaster स्प्राइट की छवि](images/natural-disaster-sprite.png)

```blocks3
when flag clicked
hide
```

--- /task ---

**Natural Disaster** स्प्राइट स्क्रीन के ऊपर से नीचे तक जाएगी।

--- task ---

अपने कोड के अंत में एक `forever`{:class="block3control"} ब्लॉक जोड़ें। इसके भीतर, `go to x:0 y:0`{:class="block3motion"} ब्लॉक जोड़ें और `y:`{:class="block3motion"} मान को `200` में बदलें। एक `show`{:class="block3looks"} ब्लॉक जोड़ें, उसके बाद `glide 1 secs to x:0 y:0`{:class="block3motion"} जोड़ें, और सेकंड के मान को `3` बदलें और `y:`{:class="block3motion"} मान से `-200`:

![Natural Disaster स्प्राइट की छवि](images/natural-disaster-sprite.png)


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

**Natural Disaster** स्प्राइट में तीन पोशाकें होती हैं: **Drought**, **Forest Fire**, और **Tornado**, क्योंकि पेड़ कई प्रकार की प्राकृतिक आपदाओं की चपेट में आ सकते हैं। कोड जोड़ें ताकि सिमुलेशन में कई आपदा प्रकार हों।

--- task ---

 पोशाकें देखने के लिए **Costumes** टैब पर क्लिक करें। **Code** टैब पर वापस क्लिक करें और `hide`{:class="block3looks"} ब्लॉक जोड़ें जब यह स्क्रीन के नीच पहुच जाए, और उसके बाद `next costume`{:class="block3looks"} ब्लॉक:

![Natural Disaster स्प्राइट की छवि](images/natural-disaster-sprite.png)


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

अपने प्रोजेक्ट का परीक्षण करें। **Natural Disaster** स्प्राइट अब ऊपर से नीचे की ओर चलती है, और हर बार पोशाक बदलती है।

![मंच पर प्राकृतिक आपदा की तस्वीर](images/disaster-on-stage.png)

--- /task ---

वैज्ञानिक कभी-कभी भविष्यवाणी कर सकते हैं कि प्राकृतिक आपदाएं कब होंगी, हालांकि यह मुश्किल हो सकता है क्योंकि सिमुलेशन के विपरीत, उनका समय हमेशा स्पष्ट नहीं होता है। अब, स्प्राइट की उपस्थिति को वास्तविक जीवन की तरह अप्रत्याशित बनाने के लिए **Natural Disaster** स्प्राइट में यादृच्छिक समय जोड़ें।

--- task ---

यादृच्छिक समय बनाने के लिए अपने `forever`{:class="block3control"} ब्लॉक के ऊपर एक `wait 1 seconds`{:class="block3control"} ब्लॉक जोड़ें। `pick random`{:class="block3operators"} ऑपरेटर को `wait`{:class="block3control"} ब्लॉक में खींचें, और मानों को `10` और `20` में बदलें:

![Natural Disaster स्प्राइट की छवि](images/natural-disaster-sprite.png)


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

**Natural Disaster** स्प्राइट के संचलन में यादृच्छिकता जोड़ें।

--- task ---

एक <`pick random`{:class="block3operators"} ऑपरेटर को दोनों `go to`{:class="block3motion"} ब्लॉक और `glide`{:class="block3motion"} ब्लॉक के `x:`{:class="block3motion"} निर्देशांक में खींचें। प्रत्येक में मानों को `-200` और `200` में बदलें:

![Natural Disaster स्प्राइट की छवि](images/natural-disaster-sprite.png)


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

अपने प्रोजेक्ट का फिर से परीक्षण करें। आपके **Natural Disaster** स्प्राइट को अब यादृच्छिक स्थिति से दूसरी यादृच्छिक स्थिति में गिरने से पहले 10 से 20 सेकंड के बीच प्रतीक्षा करनी चाहिए। यह हर बार पोशाक भी बदलता है और जिस भी पेड़ को छूटा है तो उसे हटा देता है।

--- /task ---

--- save ---
