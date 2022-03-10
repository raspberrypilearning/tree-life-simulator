## చెట్ల నిర్వహణ

కొత్త చెట్లు పెరిగే రేటు వాతావరణ పరిస్థితులు, నేల నాణ్యత, వ్యాధులు, సూర్యకాంతి మరియు నీరు వంటి అనేక అంశాలపై ఆధారపడి ఉంటుంది. ఈ దశలో, ఈ పరిస్థితులను నిర్వహించడం ప్రాంతంలోని చెట్ల సంఖ్యను ఎలా ప్రభావితం చేస్తుందో ప్రదర్శించడానికి మీరు స్లయిడర్‌ను జోడిస్తారు.

పెరుగుతున్న వేగం `tree management`{:class="block3variables"} అని పిలువబడే `variable`{:class="block3variables"} లో నిర్వహించబడుతుంది.

--- task ---

కొత్త వేరియబుల్ సృష్టించడానికి, `Variables`{:class="block3variables"} బ్లాక్స్ మెనుపై క్లిక్ చేయండి.

**Make a Variable** బటన్ పై క్లిక్ చేయండి.

మీరు మీ `variable`{:class="block3variables"}కి పేరు పెట్టవచ్చు. దీనిని `tree management` పిలవండి.

--- /task ---

మీ కొత్త `variable`{:class="block3variables"} Stage పై కనిపిస్తుంది. తర్వాత, మీ సిమ్యులేషన్ లో వేగాన్ని నియంత్రించడానికి స్లయిడర్‌ను సృష్టించండి.

--- task ---

Stage పైన `tree management`{:class="block3variables"} వేరియబుల్‌పై రైట్-క్లిక్ చేయండి మరియు మెను కనిపిస్తుంది.

మెనులో **slider** ను ఎంచుకోండి.

--- /task ---

ప్రస్తుతానికి, `tree management`{:class="block3variables"} పరిధి చాలా విస్తృతంగా ఉంది.

--- task ---

Stage పై **tree management**{: class="block3variables"} స్లయిడర్‌పై రైట్-క్లిక్ చేసి, **change slider range** ని సెలెక్ట్ చేయండి.

పరిధిని `0` మరియు `5`మధ్యకు మార్చండి.

--- /task ---

simulation లో, **tree management** స్లయిడర్ కొత్త చెట్లు పెరిగే వేగాన్ని నియంత్రిస్తుంది. మీరు స్లయిడర్‌ను కుడివైపుకు తరలించినట్లయితే, అది పెరుగుదల ని వేగవంతం చేస్తుంది; మీరు దానిని ఎడమ వైపుకు తరలించినట్లయితే, అది పెరుగుదలను తగ్గిస్తుంది.

స్లయిడర్ కుడివైపు (5) ఉన్నప్పుడు, ఒక చెట్టును నాటడానికి అనుకరణ ఒక సెకను వేచి ఉంటుంది మరియు ఎడమవైపు (0) ఉన్నప్పుడు చెట్టును నాటడానికి ఆరు సెకన్లు వేచి ఉంటుంది.

**tree management** స్లయిడర్‌లో మార్పుకు ప్రతిస్పందనగా ఉందని నిర్ధారించుకోవడానికి మీరు బ్లాక్‌ల సమితిని జోడిస్తారు.

--- task ---

`timer`{:class="block3sensing"} బ్లాక్ ఎలా పనిచేస్తుందో మీరు ఇందులో చూస్తారు. Stage మీద టైమర్ చూపించడానికి`Sensing`{:class="block3sensing"} బ్లాక్‌ల మెనుకి వెళ్లి, `timer`{:class="block3sensing"} బ్లాక్ పక్కన ఉన్న చెక్‌బాక్స్‌పై క్లిక్ చేయండి.

ఆకుపచ్చ జెండాపై క్లిక్ చేయండి మరియు టైమర్ వెంటనే లెక్కించడం ప్రారంభించడాన్ని మీరు గమనించవచ్చు. టైమర్‌ కనిపించకుండా మళ్లీ చెక్‌బాక్స్‌పై క్లిక్ చేయండి.

--- /task ---

ఫ్లాగ్‌ని క్లిక్ చేసిన ప్రతిసారీ టైమర్‌ని సున్నాకి రీసెట్ చేయండి.

--- task ---

`reset timer`{:class="block3sensing"} బ్లాక్‌ను మీ `when green flag clicked`{:class="block3events"} స్క్రిప్ట్‌లో **Tree** sprite కు చొప్పించండి, తద్వారా కొత్త చెట్టును క్లోన్ చేసిన ప్రతిసారీ టైమర్ రీసెట్ అవుతుంది:

![Tree sprite యొక్క చిత్రం](images/tree-sprite.png)

```blocks3
when flag clicked
hide
forever
go to x:(pick random (-150) to (200)) y:(pick random (-120) to (120))
+ reset timer
create clone of [myself v]
end
```

--- /task ---

స్లయిడర్‌కు శీఘ్ర ప్రతిస్పందనను సృష్టించండి, తద్వారా యూజర్ వారి పరస్పర చర్య యొక్క ప్రభావాన్ని వెంటనే చూస్తారు. **tree management** స్లయిడర్ విలువను తరచుగా తనిఖీ చేసే లూప్‌ను సెటప్ చేయండి మరియు మరొక చెట్టును క్లోనింగ్ చేయడానికి ముందు వేగాన్ని సర్దుబాటు చేయండి.

--- task ---

`timer`{:class="block3sensing"} `>`{:class="block3operators"} `6` `-`{:class="block3operators"} `tree management`{:class="block3variables"} అనే కండిషన్ తో `repeat until`{:class="block3control"} బ్లాకును చొప్పించండి.  `repeat until`{:class="block3control"} బ్లాక్ లోపల, `wait 1 sec`{:class="block3control"} బ్లాక్‌ని జోడించండి:

![Tree sprite యొక్క చిత్రం](images/tree-sprite.png)

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

మీ సిమ్యులేషన్ ను మళ్లీ పరీక్షించండి. **tree management** స్లయిడర్ కొత్త చెట్లు పెరిగే వేగాన్ని నియంత్రించాలి.

![బిజీగా ఉన్న అడవి యొక్క చిత్రం](images/busy-forest.png)

--- /task ---

--- save ---
