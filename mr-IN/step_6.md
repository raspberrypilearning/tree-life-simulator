## झाडांच्या स्तराचे निरीक्षण करा

जमिनीवरील आपल्या जीवनमानासाठी झाडे अत्यंत महत्त्वाची आहेत. झाडांपासून, लोकांना खाण्यासाठी फळे, निरोगी जीवनासाठी तेल आणि हवामानापासून निवारा मिळतो. झाडे कार्बन डायऑक्साइड शोषून घेतात आणि जगभरात उत्सर्जित होणाऱ्या CO2 चा दर कमी करण्यास मदत करतात. ते प्राण्यांच्या विविध प्रजातींचे निवासस्थान देखील आहेत. झाडे आपल्या ग्रहाचे संरक्षण करण्यास मदत करतात!

या टप्प्यात, तुम्ही झाडांच्या संख्येचे निरीक्षण करण्यासाठी कोड जोडाल आणि वृक्ष क्षेत्र निरोगी किंवा खूप लहान आहे हे सांगण्यासाठी मेसेज जोडाल.

सिम्युलेशन सुरू झाल्यावर वृक्ष व्यवस्थापन पातळी शून्यावर सेट करा.

--- task ---

**Maya** स्प्राईटवर क्लिक करा. कोड क्षेत्रामध्ये तुम्हाला काही ब्लॉक्स आधीपासूनच दिसतील. हे Maya ला यूजर साठी काही टेक्स्टसह सिम्युलेशन सुरू करण्यास सांगतात. `set tree management to 0`{:class="block3variables"} ब्लॉक जोडा.

![Maya स्प्राईटची इमेज](images/maya-sprite.png)

```blocks3
when flag clicked
+ set [tree management v] to (0)
go to [front v] layer
say [Looking after trees slows down global warming & protects our planet] for (4) seconds
```

--- /task ---

सिम्युलेशन ला कोड जोडा जेणेकरून **Maya** स्प्राईट सर्व झाड केव्हा गेले ते सांगतो.

--- task ---

`forever`{:class="block3control"} ब्लॉक जोडा, त्यानंतर `if ... then`{:class="block3control"} ब्लॉक आत इंसर्ट करा. स्थिती जोडा, `mature trees`{:class="block3variables"} `=`{:class="block3operators"} `0`. `say for 2 seconds`{:class="block3looks"} ब्लॉक जोडा आणि टाईप करा: `Our planet needs more trees.`:

![Maya स्प्राईटची इमेज](images/maya-sprite.png)

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

![गेलेल्या झाडांच्या मेसेजची इमेज](images/trees-gone-message.png)

--- /task ---

CO2 चे स्तर धोकादायक दिसत असल्यास वैज्ञानीक त्यांच्या निरीक्षणांचा वापर करतात. अलर्ट जोडा जेणेकरून **Maya** स्प्राईट पुरेशी झाडे नसल्यास चेतावणी देईल.

जेव्हा शिल्लक मोठ्या झाडांची संख्या `0` पेक्षा मोठी असेल आणि `10` पेक्षा कमी असेल तेव्हा दिसण्यासाठी मेसेज सेट करा.

--- task ---

`if ... then`{:class="block3control"} ब्लॉक तुमच्या `forever`{:class="block3control"} ब्लॉकच्या आत जोडा.

तुमच्या गणनेसाठी काही ऑपरेटर जोडा. प्रथम `and`{:class="block3operators"} ब्लॉक जोडा, त्यानंतर `greater than`{:class="block3operators"} ब्लॉक, आणि `less than`{:class="block3operators"} ब्लॉक जोडा. गणना सेट करा `mature trees`{:class="block3variables"} `greater than`{:class="block3operators"} `0` `and`{:class="block3operators"} `mature trees`{:class="block3variables"} `less than`{:class="block3operators"} `10`. इंसर्ट करा `say`{:class="block3looks"} `Global warming is at dangerous levels.` `for 2 seconds`{:class="block3looks"}:

![Maya स्प्राईटची इमेज](images/maya-sprite.png)

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

दुसरा निरीक्षण संदेश जोडा.

--- task ---

शेवटच्या `if ... then`{:class="block3control"} ब्लॉकवर राईट-क्लिक करा, आणि मेनू मधून **Duplicate** निवडा. तुमचे डुप्लीकेट केलेले ब्लॉक `if ... then`{:class="block3control"} ब्लॉकच्या खाली इंसर्ट करा, आणि व्हॅल्यू `0` आणि `10` to `50` and `60` दरम्यान बदला. `say`{:class="block3looks"} ब्लॉकमध्ये दिसण्यासाठी सूचना मेसेजचा विचार करा:

![Maya स्प्राईटची इमेज](images/maya-sprite.png)

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

तुमचे सिम्युलेशन रन करा. झाडांची संख्या तुमच्या `if ... then`{:class="block3control"} ब्लॉक्सच्या रेंज मध्ये असल्यावर, **Maya** स्प्राईट निरीक्षणात्मक मेसेज सांगेल.

--- /task ---

--- save ---
