## చెట్లను లెక్కించండి

శాస్త్రవేత్తలు చెట్లు మరియు వన్యప్రాణులను పర్యవేక్షిస్తారు. వారు చెట్లు మరియు పరిసర ప్రాంతాల కవర్ (పరిమాణం), వైవిధ్యం మరియు ఆరోగ్యాన్ని నమోదు చేస్తారు. ఇలా చేయడం ద్వారా, వారు అటవీ నిర్మూలన యొక్క నిజమైన ప్రభావాన్ని చూడగలరు. గాలిలోని విమానాలు మరియు ఉపగ్రహాల నుండి, అలాగే భూమిపై ఉన్న సెన్సార్లు మరియు వ్యక్తుల నుండి పరిశీలనలను తీసుకోవచ్చు. చెట్లను రక్షించడానికి అదనపు చర్యలు ఎక్కడ అవసరమో చూడడానికి ప్రజలు తమ పరిశీలనలను ఉపయోగించవచ్చు. ఉదాహరణకు, చెట్లు వృద్ధి చెందడానికి అడవి చుట్టూ కంచెల నిర్మాణం లేదా మంటలను కనుగొని ఆపడంలో సహాయపడటానికి ఎక్కువ మంది అగ్నిమాపక సిబ్బందిని నియమించడం.

ఈ దశలో, చెట్ల సంఖ్యను నిల్వ చేసే మరియు పర్యావరణంలో మార్పులను ప్రతిబింబించే వేరియబుల్ ద్వారా మీరు మీ సిమ్యులేషన్ లోని చెట్లను పర్యవేక్షిస్తారు.

--- task ---

పూర్తిగా పెరిగిన చెట్ల సంఖ్యను నిల్వ చేయడానికి కొత్త `variable`{:class="block3variables"}ని సృష్టించండి. ఈ వేరియబుల్ ను`mature trees`{:class="block3variables"} అని పిలవండి.

--- /task ---

సిమ్యులేషన్ `0` వద్ద ప్రారంభమైనప్పుడు చెట్ల సంఖ్యను రీసెట్ చేయండి.

--- task ---

`when green flag clicked`{:class="block3events"} బ్లాక్‌ కింద గల, `mature trees`{:class="block3variables"} వేరియబుల్‌ను `0` కు సెట్ చేయండి:

![Tree sprite యొక్క చిత్రం](images/tree-sprite.png)

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

సిమ్యులేషన్ నడుస్తున్నప్పుడు మీ కౌంటర్ ఎన్ని చెట్లు సృష్టించబడిందో నిర్ధారించుకోండి.

--- task ---

మీ `when I start as a clone`{:class="block3control"} స్క్రిప్ట్‌ ని ప్రారంభించినప్పుడు `change mature trees by 1`{:class="block3variables"} బ్లాక్‌ ని చివర్లో జోడించండి:

![Tree sprite యొక్క చిత్రం](images/tree-sprite.png)

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

ఇప్పుడు మీరు మీ కొత్త చెట్లను లెక్కించవచ్చు, అయితే ఆ చెట్లన్నీ మనుగడ సాగించవు. కొత్త చెట్ల మనుగడ రేటు 80 శాతంగా అంచనా వేయబడింది, అంటే నాటిన ప్రతి 10 చెట్లలో 2 చెట్లు పూర్తిగా ఎదగకముందే సహజ కారణాల వల్ల చనిపోతాయి. మీరు దీన్ని మీ సిమ్యులేషన్ లో ప్రతిబింబించరు, కానీ కొత్త చెట్లన్నీ సహజంగా మనుగడ సాగించవని తెలుసుకోవడం ముఖ్యం.

మానవుల అటవీ నిర్మూలన ద్వారా ఎదిగిన చెట్లను కూడా నరికివేయవచ్చు. ఏదైనా చెట్టుని, **Tree feller** sprite తాకినట్లయితే, ఎదిగిన చెట్ల గణనను తగ్గించండి.

--- task ---

మీ కోడ్ చివరన, `wait until`{:class="block3control"} బ్లాక్ ని జోడించండి మరియు దాని లోపల `touching Tree Feller`{:class="block3sensing"} బ్లాక్‌ను జోడించండి. `change mature trees by 1`{:class="block3variables"} బ్లాక్ ని జోడించండి మరియు దాని విలువను `-1`కి మార్చండి. చెట్టును తొలగించడానికి, `delete this clone`{:class="block3control"} బ్లాక్‌ను జోడించండి:

![Tree sprite యొక్క చిత్రం](images/tree-sprite.png)

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

సహజమైన అటవీ నిర్మూలన వల్ల కూడా చెట్లు చనిపోతాయి, అవి పరిపక్వం చెందినా లేదా ఇంకా పెరుగుతున్నాయి. దీన్ని చూపించడానికి, చెట్టును **Natural Disaster** sprite చెట్టుని తాకినట్లయితే మీ చెట్ల సంఖ్యను తగ్గించండి.

--- task ---

`when i start as a clone`{:class="block3control"} బ్లాక్‌తో కొత్త స్క్రిప్ట్‌ను ప్రారంభించండి. `wait until`{:class="block3control"} బ్లాక్ ని మీ కోడ్ చివర జోడించండి, మరియు దాని లోపల `touchind Natural Disaster`{:class="block3sensing"} బ్లాక్‌ను జోడించండి. `size`{:class="block3looks"} `=`{:class="block3operators"} `20` కండిషన్తో `if ... then`{:class="block3control"} బ్లాక్‌ని జోడించండి .

`if ... then`{: class = "block3control"} బ్లాక్ లోపల, ఒక జోడించండి `change mature trees by 1`{:class="block3variables"} బ్లాక్ ను జోడించండి, తద్వారా పూర్తిగా పెరిగితేనే, పరిపక్వ చెట్ల సంఖ్య తక్కువవుతుంది.,. చెట్టును తొలగించడానికి, `delete this clone`{:class="block3control"} బ్లాక్‌ను జోడించండి:

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
