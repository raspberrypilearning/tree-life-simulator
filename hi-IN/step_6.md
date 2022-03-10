## पेड़ के स्तर की निगरानी करें

धरती पर हमारे जीवन की गुणवत्ता के लिए पेड़ अत्यंत महत्वपूर्ण हैं। पेड़ों से लोगों को खाने के लिए फल, स्वस्थ जीवन के लिए तेल और मौसम से आश्रय मिलता है। पेड़ कार्बन डाइऑक्साइड को अवशोषित करते हैं और दुनिया भर में उत्सर्जित CO2 की दर को कम करने में मदद करते हैं। वे जानवरों की कई अलग-अलग प्रजातियों का घर भी हैं। पेड़ हमारे ग्रह की रक्षा में मदद करते हैं!

इस चरण में, आप पेड़ों की संख्या की निगरानी के लिए कोड जोड़ेंगे, और यह बताने के लिए संदेश जोड़ेंगे कि वृक्ष क्षेत्र स्वस्थ है या बहुत छोटा है।

सिमुलेशन शुरू होने पर वृक्ष प्रबंधन स्तर को शून्य पर सेट करें।

--- task ---

**Maya** स्प्राइट पर क्लिक करें। आप देखेंगे कि कुछ ब्लॉक पहले से ही Code क्षेत्र में हैं। ये Maya को उपयोगकर्ताओं के लिए कुछ टेक्स्ट के साथ सिमुलेशन शुरू करने के लिए कहते हैं। `set tree management to 0`{:class="block3variables"} ब्लॉक जोड़ें।

![Maya स्प्राइट की छवि](images/maya-sprite.png)

```blocks3
when flag clicked
+ set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
```

--- /task ---

सिमुलेशन में कोड जोड़ें ताकि **Maya** स्प्राइट बोले जब सभी पेड़ ख़तम हो जाते हैं।

--- task ---

एक `forever`{:class="block3control"} ब्लॉक जोड़ें, फिर अंदर `if ... then`{:class="block3control"} ब्लॉक डालें। शर्त जोड़ें, <`mature trees`{:class="block3variables"} `=`{:class="block3operators"} `0`। `say for 2 seconds`{:class="block3looks"} ब्लॉक जोड़ें और टाइप करें: `Our planet needs more trees.`:

![Maya स्प्राइट की छवि](images/maya-sprite.png)

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

![पेड़ ख़तम हो गये संदेश की छवि](images/trees-gone-message.png)

--- /task ---

वैज्ञानिक अपने अवलोकनों का उपयोग चेतावनी देने के लिए करते हैं यदि CO2 का स्तर खतरनाक दिख रहा है। एक चेतावनी जोड़ें ताकि **Maya** स्प्राइट चेतावनी दे सके अगर पर्याप्त पेड़ नहीं हैं।

जब परिपक्व पेड़ों की संख्या `0` से अधिक और `10` से कम हो, तब प्रकट होने के लिए एक संदेश सेट करें।

--- task ---

अपने `forever`{:class="block3control"} ब्लॉक के अंदर एक`if ... then`{:class="block3control"} ब्लॉक जोड़ें।

अपनी गणना के लिए कुछ ऑपरेटरों को जोड़ें। पहले एक `and`{:class="block3operators"} ब्लॉक जोड़ें, फिर एक `greater than`{:class="block3operators"} block, और एक `less than`{:class="block3operators"} ब्लॉक जोड़ें। गणना सेट करें `mature trees`{:class="block3variables"} `greater than`{:class="block3operators"} `0` `and`{:class="block3operators"} `mature trees`{:class="block3variables"} `less than`{:class="block3operators"} `10`. `say`{:class="block3looks"} `Global warming is at dangerous levels.` `for 2 seconds`{:class="block3looks"} डालें:

![Maya स्प्राइट की छवि](images/maya-sprite.png)

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

एक और अवलोकन संदेश जोड़ें।

--- task ---

आखरी `if ... then`{:class="block3control"} ब्लॉक पर राइट-क्लिक करें, और मेनू से **Duplicate** चुनें अपने डुप्लीकेट ब्लॉक को अंतिम `if ... then`{:class="block3control"} ब्लॉक में डालें और मानों को `0` और `10` से `50` और `60` में बदलें। `say`{:class="block3looks"} ब्लॉक में प्रदर्शित करने के लिए एक चेतावनी संदेश के बारे में सोचें:

![Maya स्प्राइट की छवि](images/maya-sprite.png)

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

अपने सिमुलेशन का परीक्षण करें। जब पेड़ों की संख्या आपके `if ... then`{:class="block3control"} ब्लॉक की सीमा में आ जाती है, **Maya** स्प्राइट एक एक अवलोकन संदेश कहेगी।

--- /task ---

--- save ---
