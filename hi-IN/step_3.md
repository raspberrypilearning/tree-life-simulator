## वृक्ष प्रबंधन

जिस दर पर नए पेड़ उगते हैं, वह कई कारकों पर निर्भर करता है, जैसे कि जलवायु की स्थिति, मिट्टी की गुणवत्ता, रोग, धूप और पानी। इस चरण में, आप यह प्रदर्शित करने के लिए एक स्लाइडर जोड़ेंगे कि इन स्थितियों का प्रबंधन क्षेत्र में पेड़ों की संख्या को कैसे प्रभावित कर सकता है।

विकास की दर `variable`{:class="block3variables"}में रखी जाएगी जिसे `tree management`{:class="block3variables"}कहा जाता है।

--- task ---

एक नया वेरिएबल बनाने के लिए, `Variables`{:class="block3variables"} ब्लॉक मेनू पर क्लिक करें।

फिर, **Make a Variable** बटन पर क्लिक करें।

आप अपने `variable`{:class="block3variables"} को एक नाम दे सकते हैं। इसे `tree management` कहें।

--- /task ---

आपका नया `variable`{:class="block3variables"} Stage पर दिखाई दे रहा है। इसके बाद, अपने सिमुलेशन में गति को नियंत्रित करने के लिए एक स्लाइडर बनाएं।

--- task ---

Stage पर, `tree`{:class="block3variables"} वेरियबल पर राइट-क्लिक करें, और एक मेनू दिखाई देगा।

मेनू में **slider** चुनें।

--- /task ---

इस समय, `tree management`{:class="block3variables"} की सीमा बहुत व्यापक है।

--- task ---

Stage पर, **tree**{: class="block3variables"} स्लाइडर पर राइट-क्लिक करें और **change slider range** चुनें।

सीमा को `0` और `5` के बीच बदलें।

--- /task ---

सिमुलेशन में, **tree management** स्लाइडर नए पेड़ों के बढ़ने की गति को नियंत्रित करता है। यदि आप स्लाइडर को दाईं ओर ले जाते हैं, तो यह वृद्धि को गति देता है; यदि आप इसे बाईं ओर ले जाते हैं, तो यह वृद्धि को धीमा कर देता है।

जब स्लाइडर दाईं ओर (5) होता है, तो सिमुलेशन एक पेड़ लगाने के लिए एक सेकंड की प्रतीक्षा करता है, और जब यह बाईं ओर (0) होता है तो यह एक पेड़ लगाने के लिए छह सेकंड तक प्रतीक्षा करता है।

आप यह सुनिश्चित करने के लिए ब्लॉक का एक सेट जोड़ेंगे कि नए पेड़ बढ़ने की गति **tree management** स्लाइडर में बदलाव की प्रतिक्रिया में है।

--- task ---

इस कार्य में, आप देखेंगे कि `timer`{:class="block3sensing"} ब्लॉक कैसे काम करता है। Stage पर घड़ी दिखाने के लिए `Sensing`{:class="block3sensing"} ब्लॉक मेनू पर जाएं, और `timer`{:class="block3sensing"} ब्लॉक के बगल में स्थित चेकबॉक्स पर क्लिक करें।

हरे झंडे पर क्लिक करें और आप देखेंगे कि घड़ी तुरंत गिनना शुरू कर देता है। घड़ी को दिखने से छिपाने के लिए फिर से चेकबॉक्स पर क्लिक करें।

--- /task ---

हर बार फ़्लैग पर क्लिक करने पर घड़ी को शून्य पर रीसेट करें।

--- task ---

`when green flag clicked`{:class="block3events"} स्क्रिप्ट पर `reset timer</0{:class="block3sensing"} ब्लॉक डालें, ताकि घड़ी हर बार एक नया पेड़ क्लोन होने पर रीसेट हो जाए।: </p>

<p spaces-before="0"><img src="images/tree-sprite.png" alt="Tree स्प्राइट की छवि" /></p>

<pre><code class="blocks3">when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
+ reset timer
create clone of [myself v]
end
`</pre>

--- /task ---

स्लाइडर के लिए त्वरित प्रतिक्रिया बनाएं ताकि उपयोगकर्ता तुरंत उनकी पारस्परिक क्रिया के प्रभाव को देख सके। एक लूप सेट करें जो **tree management** स्लाइडर मान को बार-बार जांचता है और दूसरे पेड़ को क्लोन करने से पहले गति को समायोजित करता है।

--- task ---

एक `repeat until`{:class="block3control"} ब्लॉक डालें इस शर्त`timer`{:class="block3sensing"} `>`{:class="block3operators"} `6` `-`{:class="block3operators"} `tree management`{:class="block3variables"} के साथ।  `repeat until`{:class="block3control"} ब्लॉक के भीतर `wait 1 seconds`{:class="block3control"} ब्लॉक जोड़ें:

![Tree स्प्राइट की छवि](images/tree-sprite.png)

```blocks3
when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
reset timer
+ repeat until {{(timer)>((6)-(tree management))}}
wait (1) seconds
end
create clone of [myself v]
end
```

--- /task ---

--- task ---

अपने सिमुलेशन का फिर से परीक्षण करें। सिमुलेशन में, **tree management** स्लाइडर नए पेड़ों के बढ़ने की गति को नियंत्रित करता है।

![व्यस्त जंगल की छवि](images/busy-forest.png)

--- /task ---

--- save ---
