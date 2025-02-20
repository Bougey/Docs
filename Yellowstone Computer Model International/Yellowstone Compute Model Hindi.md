![Image1forYellowstone](https://github.com/MorpheusAIs/Morpheus/assets/1563345/80a6c1cf-fe52-42ba-bfd4-91d9faf67f07)

# मॉर्फियस "येलोस्टोन" कंप्यूट मॉडल
### एरिक वूरहीस
### 3 जनवरी 2023

एक सुझावित संशोधन Morpheus टोकनॉमिक्स संरचना के लिए कंप्यूट प्रेरणा का मॉडल जो एक केंद्रीय ए.आई. नेटवर्क पर है।

Notion पर देखें: https://defiant-wolfsbane-830.notion.site/Morpheus-Yellowstone-Compute-Model-2ca9b4e7e1374c898937fdbd1b964cc1

## सारांश
येलोस्टोन कंप्यूट मॉडल में, Morpheus नेटवर्क केवल उस संगणना के लिए प्रदान किए जाने वाले प्रदाताओं को कम्पीटिटिव बिड प्रक्रिया के माध्यम से ही भुगतान करता है, और टोकन की अल्प उत्पाद को बैलेंस के आधार पर MOR टोकन धारकों को भुगतान के बजाय प्रातिष्ठानिक रूप से आवंटित करता है। यह उपयोगकर्ता अनुभव में वृद्धि करता है जबकि सिबिल सुरक्षा को कम करता है। येलोस्टोन ने उपयोगकर्ताओं को पूरी तरह से समयबद्ध और सटीक बनाए रखने के लिए समय और पास/फेल टेस्ट के महत्वपूर्ण मैट्रिक्स को भी अनुदित किया है। येलोस्टोन राउटर के माध्यम से कभी भी प्रॉम्प्ट या परिणाम नहीं भेजकर गोपनीयता को बनाए रखता है, और एक बड़े पैम्पल की अनुमति देने के लिए ब्लॉकचेन लेन-देन को कम से कम करता है। इस मॉडल के माध्यम से, MOR मौजूदा (हालांकि असीमित नहीं) अनुमति रखने में मौद्रिक मूल्य प्राप्त करता है, इन्फेरेंस प्रति लेन-देन की आवश्यकता के बिना अनिवार्य योग्य संगणन का स्थायी उपयोग करने की अनुमति देता है।

यदि इसे अपनाया जाता है, तो यह पेपर Morpheus के सफेदपत्र के "संगणन सिद्धांत, पंजीकरण और पुरस्कार" खंड को बदल देता है।
(https://github.com/MorpheusAIs/Morpheus/blob/main/WhitePaper.md)

## Background
मॉर्फियस, विकेन्द्रीकृत और अनुमतिहीन जेनेरेटिव AI के लिए पर्याप्त और स्केलेबल कम्प्यूट के संसाधन के लिए टोकनॉमिक्स का उपयोग करता है। इसके मूल संकल्पना में, मॉर्फियस ने 24% MOR उत्सर्जन को सीधे कंप्यूट प्रदाताओं को दिया, प्रत्येक के अनुसार अनुरोधित इन्फरेंस के आधार पर, और यह उन प्रदाताओं को इन्फरेंस अनुरोधों की प्राथमिकता देता था जिनके पास MOR की अधिक मात्रा थी।

मूल श्वेत पत्र से:
"प्रत्येक कंप्यूट प्रदाता द्वारा जलाए गए MOR लेन-देन शुल्कों का प्रो-राटा हिस्सा, कंप्यूट प्रदाताओं की स्थिति का प्रमाण के रूप में काम करता है और हर दिन MOR टोकन का एक अनुपात प्राप्त करता है।

उदाहरण के लिए, अगर नेटवर्क शुरू होने पर दिन 1 पर 100 कंप्यूट प्रदाता हैं, तो प्रत्येक को MOR शुल्कों के माध्यम से जलाए गए अनुपात के आधार पर प्रो-राटा इनाम मिलता है। इस मामले में, मान लें कि 100 कंप्यूट प्रदाताओं में से प्रत्येक ने 100 MOR जलाए, तो हर दिन 3,456 MOR टोकन का 1% = 34.56 MOR होगा।"

इस दृष्टिकोण की तीन प्रमुख समस्याएं हैं:
इसमें उपयोगकर्ताओं को प्रति-इन्फरेंस लेन-देन शुल्क देना पड़ता है। भले ही यह कम हो, यह काफी बाधा है और ओपनएआई के UX की तुलना में यह हमेशा हीन होगा। इसमें प्रत्येक इन्फरेंस के लिए कम से कम एक ब्लॉकचेन लेन-द

## पृष्ठभूमि
मॉर्फियस टोकनॉमिक्स का उपयोग स्थानीय और अनुमति रहित सृजनात्मक ए.आई. के लक्ष्य के लिए पर्याप्त और स्केलेबल संगणन को प्रोत्साहित करने के लिए करता है। इसके मूल रूप में, मॉर्फियस ने मॉर इमिशन्स के 24% को कम्प्यूट प्रदाताओं को सीधे जारी किया, इंफेरेंस रिक्वेस्ट्स के आधार पर प्रो-रेटा, और यह इंफेरेंस रिक्वेस्ट्स को उन प्रदाताओं को प्राथमिकता दी जो ने कितना मॉर होल्ड किया।

### मूल सफेदपत्र से:
"प्रत्येक कम्प्यूट प्रदाता द्वारा जलाए गए प्रो-रेटा MOR लेन-देन शुल्क से कम्प्यूट प्रदाता की स्थिति के प्रमाण के रूप में कार्य करता है और प्रतिदिन MOR टोकन का एक हिस्सा कमाता है।

उदाहरण के लिए, अगर नेटवर्क लॉन्च होने के दिन 1 पर 100 कम्प्यूट प्रदाता हैं, तो प्रत्येक कोई भी एक इसे जलाए गए MOR के मात्रा के आधार पर प्रो-रेटा पुरस्कृत होता है। इस मामले में, मान लो कि 100 कम्प्यूट प्रदाताएँ प्रत्येक दिन 100 MOR को जला रही हैं, तो दिन में 3,456 MOR टोकन का 1% = 34.56 MOR।"

### इस दृष्टिकोण के साथ तीन प्रमुख समस्याएँ हैं:
इसे उपयोगकर्ताओं को प्रत्येक इंफेरेंस लेन-देन शुल्क देने की आवश्यकता है। यह कितना भी कम हो, यह काफी रिस्ता है और खुद को OpenAI के उपयोगकर्ता अनुभव के साथ हमेशा एक हाजिरा निम्नता का कारण होगा। इसमें कम से कम एक ब्लॉकचेन लेन-देन प्रति इंफेरेंस की आवश्यकता है, जो शायद L2 पर भी स्केलेबल नहीं है। प्रत्येक इंफेरेंस घटना बहुत कम लागत में है, और यदि एक ब्लॉकचेन लेन-देन की आवश्यकता होती, तो इसका अर्थशास्त्र असंभाव होता।
यह मॉडल का सत्यापन किसी कोंप्यूट प्रदाताओं के लिए प्रत्याशित राजस्व वास्तविक संगणन लागत से कहीं अधिक है। एक प्रतिरक्षक इस प्रकार स्वयं के कम्प्यूट प्रदाता नोड पर स्पैम इंफेरेंस रिक्वेस्ट्स को भर सकता है, और एक अपेक्षित संबंधित नहीं करता है, तो यह हर दिन एक अच्छे हिस्से का MOR टोकन कमा सकता ह

यदि संयोजन अनुरोधों को प्रदाताओं द्वारा धारित MOR मात्रा के आधार पर प्राथमिकता दी जा रही है, तो नेटवर्क द्वारा प्रदर्शित की जाने वाली प्रदर्शन क्षमता (प्रतिसाद समय) और उनके संगणन लागूकरण की लागत को अनदेखा किया जा रहा है, और ये दो कारक हैं जिन्हें नेटवर्क को अनुकरण करना चाहिए (प्रतिसाद समय और कंप्यूट लागूकरण को न्यूनतम से न्यूनतम ले जाना चाहिए). यदि सबसे अधिक MOR धारित प्रदाता अपने कॉलेज के दिनों से $200 के GPU को चला रहा हो, तो कई उपयोगकर्ताओं के लिए प्रदर्शन क्षमता अत्यंत खराब होगी. प्राथमिकता को बोली कीमत और प्रदर्शन के आधार पर होनी चाहिए, MOR धारण नहीं।

नीचे "येलोस्टोन" मॉडल प्रस्तुत है जो Morpheus टोकनॉमिक्स को कम्प्यूट प्राविधि के लिए उपरोक्त मुद्दों का सामना करने के लिए संशोधित करता है। इस मॉडल का कार्य करने के लिए यह कोई चार मिलाकर नहीं देखेगा कि आवंटित उत्सर्जन का कौन-सा हिस्सा कंप्यूट को समर्पित किया गया है, और हम 24% कुल उत्सर्जन का स्थिति दृढ़ मानते हैं।

### लक्ष्य हैं:
उपयोगकर्ताओं को इनफेरेंस प्रति भुगतान करने की अनुमति देना (आशावादी रूप से, बिलकुल भी ना भुगतान करना)
अनुमति रहित कम्प्यूट संसाधन का कुशल, स्केलेबल, और सतत प्रदान हासिल करना बिना इसके लिए अधिशेष भुगतान करना
कंप्यूट प्रदाताओं के बीच कम प्रतिसाद समय और लागत प्रतियोगिता को प्रोत्साहित करना
ब्लॉकचेन लेन (L2 या अन्य) की न्यूनतम संख्या को कम करना
MOR के लिए एक आर्थिक रूप से साउंड मौद्रिक मांग को प्रदर्शित करना

## येलोस्टोन मॉडल
चार घटक शामिल हैं:

### उपयोगकर्ता
* पूछताछ हैं
* नि: शुल्क और संसोधन / निगरानी के बिना तेज / सटीक कम्प्यूट चाहते हैं
### प्रदाता
* कम्प्यूट है
* पैसे चाहते हैं (MOR)
### राउटर
* उच्च थ्रूपट प्रोसेसिंग इंजन
* पहले से बाहर थोड़ा केंद्रीकृत हो सकता है, अंत में इसे बिकेंद्रीकृत करने की आवश्यकता है


## मानक तौल और माप
एकात्मक इनफेरेंस की एक इकाई है जो AI में होती है, जो इनफेरेंस प्रति सेकंड (IPS) में मापित होती है। यह सांकेतिक रूप से ब्लॉकचेन पर वे इकाईयों के साथ तुलना की जा सकती है। इनफेरेंस Yellowstone राउटर में दरें परिभाषित करने के लिए इस्तेमाल होती हैं। एक मॉर्फियस ए.आई. इकाई का वजन इसलिए एक इनफेरेंस है। अनुरोध के प्रकार के आधार पर, इसे किसी भी कम्प्यूट कार्य में लागू किया जा सकता है।

जब AI और ब्लॉकचेन समाहित होते हैं, मॉर्फियस दोनों AI और ब्लॉकचेन द्वारा इस्तेमाल किए जाने वाले शब्दावली को स्पष्ट करने के लिए मापों का एक ओपन-सोर्स मानक प्रदान करने का प्रयास कर रहा है।




दो प्रकार के प्रॉम्प्ट्स होते हैं, जो एक मॉडल द्वारा वापसी की जाने वाली प्रतिक्रिया के आकार द्वारा परिभाषित होते हैं:

***निर्धारित लंबाई के प्रॉम्प्ट्स***, जहां प्रतिक्रिया को वापस लौटाने के लिए प्रतिक्रिया की लंबाई को ध्यान में लेते हैं। इसके उदाहरण हैं:
- चैट/छवि निर्माण
- रोग निदान
- वस्तु पहचान
- धनधारी पहचान

**अनिर्धारित लंबाई के प्रॉम्प्ट्स** उत्तर करने के लिए संसाधनों की आवश्यकता है जो केवल उत्तर बनाए जाने के बाद ज्ञात होते हैं। इसके उदाहरण हैं:
- स्पैगेटी के बारे में सोनाटा गाओ।
- एक खुशी का जन्मदिन वीडियो बनाएं
- मॉडल X को मॉडल Y के साथ कम्बाइन करें
- एक 3D मॉडल को एक .stl फ़ाइल में स्लाइस करें

येलोस्टोन निर्धारित लंबाई के प्रॉम्प्ट्स पर ध्यान केंद्रित करता है। जिस तरह का राउटर वर्णित किया गया है, वह भविष्य में अनिर्धारित प्रॉम्प्ट्स को संबोधित करने के लिए निर्मित होगा, लेकिन आज इन्हें सेवा करने के लिए नहीं। इसे पूरा करने के लिए हम एक डिसेंट्रलाइज्ड ए.आई. का मानकीकृत माप का उपयोग करते हैं।

### प्रति सेकंड इनफेरेंस के अभिव्यक्तियाँ:

| प्रकार | प्रतिक्रिया | दर |
|------|----------|------|
| निर्धारित | भाषा | प्रति सेकंड अनुमानित टोकन्स (TPS)|
| अनिर्धारित - मीडिया | ऑडियो | प्रति सेकंड अनुमानित सैम्पल्स (ISPS) |
| अनिर्धारित - मीडिया | वीडियो | प्रति सेकंड अनुमानित फ्रेम्स (IFPS) |
| अनिर्धारित - भविष्य की तकनीक | अज्ञात भविष्य फॉर्मेट | NA |

येलोस्टोन राउटर के लिए इनफेरेंस का पहला माप टोकन होगा। अन्य इनफेरेंस फॉर्मेट्स भी आगे आएंगे।

### समय

इनफेरेंस के लिए ब्लॉक समय 12 सेकंड है, यानी प्रति मिनट 5 बार इनफेरेंस लेन का एक ब्लॉक प्रकाशित और लेखा किया जाता है।  

### कंप्यूट कॉन्ट्रैक्ट
*अनुमति रहित स्मार्ट कॉन्ट्रैक्ट जो MOR के उत्सर्जन को प्राप्त करता है, प्रदाताओं के साथ श्रेय और ऋण का ट्रैकिंग करता है, और जब आवश्यक हो तो प्रदाताओं को भुगतान करता है।

"उपयोगकर्ता": इसे उस किसी भी एंटिटी के रूप में परिभाषित किया गया है जिसके पास MOR पता है और राउटर को अनुरोध भेजती है, कंप्यूट का उपयोग करती है। यह एक विशिष्ट व्यक्ति हो सकता है जो Morpheus डेस्कटॉप नोड से अनुरोध भेजता है, या यह एक बॉट हो सकता है, या यह एक कंपनी या 3आ र्ड पार्टी वेबसाइट हो सकती है जो अपने अंतयः-उपयोगकर्ताओं के प्रति Morpheus नेटवर्क के साथ इंटरएक्ट करती है (इनफेरेंस का उपयोग नहीं किया जाता है या उसे कंप्यूट कॉन्ट्रैक्ट में शामिल नहीं किया गया है, केवल जब एक इनफेरेंस असफल होता है)।


"प्रदाता": इसे किसी भी एंटिटी के रूप में परिभाषित किया गया है, जो कम्प्यूट संसाधन प्रदान करने वाला एक नोड चला रही है, जिसके पास MOR पता है और राउटर के माध्यम से टोकन बोलियाँ करती है। जब राउटर से प्रदाता बोली जीतता है, तो प्रदाता विभिन्न ए.आई. मॉडल्स के लिए उपयोगकर्ता को कम्प्यूट संसाधन (जीपीयू, आदि) प्रदान करता है।

"राउटर": इसे एक सॉफ़्टवेयर एप्लिकेशन के रूप में परिभाषित किया गया है जिसके पास MOR पता है और यूज़र और प्रदाता के बीच का 2-पक्षीय बाजार बातचीत करता है। राउटर प्रदाता पते और बोलियों को पंजीकृत और ट्रैक करता है, उपयोगकर्ताओं से अनुरोध प्रक्रिया करता है, प्रोसेस्ड अनुरोधों की [मिलीसेकंड] और पास/फेल टेस्ट को रिकॉर्ड करता है, और योग्य प्रदाताओं को MOR में भुगतान के लिए कंप्यूट कॉन्ट्रैक्ट को निर्देशित करता है। राउटर कभी भी MOR लेन-देन (ना ही किसी भी ब्लॉकचेन पर लेन-देन) नहीं करता है। राउटर कभी भी एक अनुरोध के सामग्री या प्रतिसाद को नहीं देखता है।

"कंप्यूट कॉन्ट्रैक्ट": इसे एक स्मार्ट कॉन्ट्रैक्ट के रूप में परिभाषित किया गया है जिसके पास MOR पता है, जो कंप्यूट बकेट के लिए आवंटित सभी निकाले गए MOR को प्राप्त करता है, योग्य प्रदाताओं को ऋणों का ट्रैकिंग करता है, और प्रदाताओं से MOR को मांग पर भुगतान करता है।

"टोकन" ("टी"): राउटर के माध्यम से बोली गई पत्रकों की सबसे छोटी मात्रा है। अक्सर यह टेक्स्ट के लगभग ~4 अक्षर होता है, या छवि के 5x5 पिक्सेल्स होते हैं, आदि। इसे ब्लॉकचेन "टोकन्स" जैसे ERC20 टोकन्स या MOR टोकन इत्यादि से गलत समझना नहीं चाहिए।

"टोकनमैक्स" नीचे राउटर द्वारा भुगतान के लिए स्वीकृत की जाने वाली टोकनों की अधिकतम संख्या को सूचित करता है।

"आरएफसी": "कंप्यूट के लिए अनुरोध" का संक्षेप है। एक उपयोगकर्ता एक आरएफसी को राउटर को भेजता है, और उपयोगकर्ता इच्छा करता है कि वह [LLM] तक पहुँचने के लिए और [टोकनमैक्स] के रूप में उपयोग करेगा, जो प्रतिसाद में स्वीकार्य LT की एक कैप है। उपयोगकर्ता इसे कैप करना चाहेगा क्योंकि उच्च संख्याएँ = उत्तर के लिए लंबे प्रतीक्षा समय का कारण हो सकती हैं, और यह प्रतिदिन सीमित होने वाले उपयोगकर्ता की अधिकतम संख्या के प्रति अधिक गिनी जाएगी।

### कॉन्ट्रैक्ट सुरक्षा

किसी भी अटैक को रोकने के लिए जो कम्प्यूट का कोई अप्रयुक्त उपयोग करके MOR की संख्या को घटित कर सकता है, इसके लिए कम्प्यूट प्रदाताओं को आवंटित अप्रयुक्त MOR का पूल एक ब्लॉक दिन में अधिकतम 1% तक कम किया जा सकता है। यह सामान्य कंप्यूट इमीशन्स + 1% के बराबर है।

### कंप्यूट बूटस्ट्रैपिंग प्रोत्साहन

"कैपिटल कॉन्ट्रैक्ट" के बूटस्ट्रैपिंग अवधि के बाद पहले वर्ष के लिए, शीर्ष 100 कंप्यूट प्रदाताओं को 2.4% MOR इमीशन की संप्राप्ति के अधिकार होंगे। इसे राउटर्स द्वारा गणना की जाती है और कंप्यूट कॉन्ट्रैक्ट में लेखा किया जाता है।



## कार्यप्रवाह
1) उपयोगकर्ता, प्रदाता, और राउटर सभी MOR पब्लिक की सृष्टि करते हैं (यह उनकी पहचान है, सभी संदेश इस रूप में हस्ताक्षरित किए जाते हैं)। 
2) यदि उपयोगकर्ता के पास MOR का कोई शेष रहता है, तो उपयोगकर्ता राउटर को "प्रोसेसिंग के लिए अनुरोध" ("RFP") संदेश को हस्ताक्षरित करके भेज सकता है। उपयोगकर्ता [LLM] और [टोकनमैक्स] को निर्दिष्ट करता है। 
3) राउटर उपयोगकर्ता के MOR शेष के आधार पर RFP को प्राथमिकता देता है (सिबिल मुद्दे को हल करता है)। 
4) राउटर वह प्रदाता को चयन करता है जो [LLM] का समर्थन करता है, MOR में प्रति टोकन की सबसे कम बोली के आधार पर प्राथमिकता देता है। 
5) राउटर प्रदाता को जीवंतता जाँच भेजता है। अगर पास होता है, तो
6) राउटर उपयोगकर्ता को प्रदाता से जोड़ता है
7) उपयोगकर्ता प्रदाता को क्वेरी ([LLM], [पॉम्प्ट]) भेजता है 
8) प्रदाता क्वेरी की गणना करता है, परिणाम को उपयोगकर्ता को भेजता है
9) उपयोगकर्ता रूटर को स्टेप 4 और 5 के बीच समय [मिलीसेकंड], [टोकन] वितरित, और पास/फेल की रिपोर्ट करता है
10) राउटर निर्देशित करता है कि यदि [मिलीसेकंड] प्रति [टोकन] पिछले Z क्वेरी के लिए उस [LLM] के मीन के X% नीचे है और यदि उपयोगकर्ता [पास] रिपोर्ट करता है, तो कंप्यूट कॉन्ट्रैक्ट को प्रदाता को MOR से

![ComputeContractImage2](https://github.com/MorpheusAIs/Morpheus/assets/1563345/e66ea20c-9851-4f9e-9caa-66c6d798c462)



## परिणाम
* उपयोगकर्ता ने अपने प्रश्न के लिए त्वरित परिणाम प्राप्त किया, और कुछ भी नहीं भुगतान किया (यह अद्भुत यूज़र अनुभव और इसलिए अपनाई जाने वाली बातों में से एक है)। लक्ष्य 1 को हल किया गया।
* कॉम्प्यूट कॉन्ट्रैक्ट ने एक प्रतिस्पर्धी बोली प्रक्रिया के माध्यम से कंप्यूट के लिए भुगतान किया, और उसे आदेश देने वाले उपयोगकर्ता की गुणवत्ता/संतुष्टि की जाँच के लिए एक चेक मिली। लक्ष्य 2 को हल किया गया।
* प्रदाता ने प्रतिस्पर्धी मूल्य के माध्यम से कॉम्प्यूट के लिए (MOR) पैसे प्राप्त किए हैं, जब तक प्रतिस्पर्धी प्रतिक्रिया तेज है। प्रदाता ने उसी को प्रदान करने के लिए पूरी तरह से प्राप्त किया है जो उसने कॉम्प्यूट के लिए मांग की थी। यदि उसकी मांग बहुत उच्च है, तो दूसरे कम बोली देंगे, इस प्रकार प्रणाली कुशल है और प्रदाता कीमतों को बेस इलेक्ट्रिसिटी की लागत की दिशा में घटाएगी। लक्ष्य 3 को हल किया गया।
* ऑन-चेन लेन-देन की संख्या को कम से कम किया गया (बहुत से हजारों प्रश्न एक सिंगल ऑन-चेन TX के बिना बह सकते हैं)। लक्ष्य 4 को हल किया गया।
* तेज, मुफ्त कंप्यूट प्राप्त करने की क्षमता से MOR टोकन की मांग को बढ़ावा मिलता है। लक्ष्य 5 को हल किया गया।
* स्टेप 6 और 7 ने सार्थक गोपनीयता प्रदान की (क्वेरी कभी भी राउटर को छूने का संभावना नहीं है, न ही परिणाम)। प्रदाता थोड़ी बहुत यात्रा के रूप में चयन किए जाते हैं, और कभी भी उपयोगकर्ता की पहचान को आईपी पते के अलावा कभी नहीं जानते हैं। बेहतर गोपनीयता को बाद में टीओआर + एफएचई के साथ हासिल किया जा सकता है
* कंप्यूट कॉन्ट्रैक्ट से MOR शेष था। कॉन्ट्रैक्ट मौद्रिक रहेगा जब तक कि हर अवधि से अर्जित MOR < अवधि से मिले गए MOR हों।
* यदि उपयोगकर


—-------------


## कंप्यूट बजट
मॉर्फियस नेटवर्क को यह तय करना होगा कि यह कितना MOR कंप्यूट में खर्च करने के लिए इच्छुक है एक निर्दिष्ट अवधि में (जैसे कि प्रतिदिन), इसे कंप्यूट बजट कहा जाता है। प्रति अवधि, कंप्यूट कॉन्ट्रैक्ट द्वारा इस राशि तक का MOR खर्च किया जा सकता है। इस राशि को MOR मूल्य से गुणित किया जाना, हर दिन कंप्यूट प्राप्ति के लिए हमें एक डॉलर बजट देता है।

खुला प्रश्न 1: कंप्यूट बजट को कैसे निर्धारित किया जाए? सबसे सरल विचार है कि कंप्यूट बजट = कंप्यूट कॉन्ट्रैक्ट में निर्गमन किया गया MOR सेट करें। इस प्रकार, कंप्यूट कॉन्ट्रैक्ट कभी भी टोकन की कमी नहीं करेगा। लेकिन उपयोग नहीं किए गए टोकनों के साथ क्या करना है, क्योंकि प्रतिदिन अधिकतम कभी भी उपयोग नहीं होगा? शायद इन्हें मौद्रिक रूप से वर्तमान MOR टोकन धारकों को प्रदान किया जा सकता है। या, इन्हें जला दिया जा सकता है। या, इन्हें कंप्यूट कॉन्ट्रैक्ट में अपयुक्त रूप में रखा जा सकता है, जिसे भविष्य में कंप्यूट पर खर्च किया जा सकता है (लेकिन यह बहुतायत प्रशासन प्रश्न खोलता है)।



## एक्सेस दर
मॉर्फियस नेटवर्क एलटी उत्पाद की स्थानीय संसाधन को "एक्सेस दर" के अवधारित के माध्यम से आवंटित करता है। एक्सेस दर तय करती है कि प्रति दिन प्रति MOR टोकन द्वारा कितने एलटी तक पहुंचा जा सकता है। अयोग्य पहुंच संचित नहीं होती है। एक्सेस दर हमेशा 1 MOR टोकन प्रति LT की मात्रा के रूप में प्रदर्शित की जाती है (जैसे कि 1 MOR = 15,000 LT)। एक्सेस दर मैक्सएलटी द्वारा कुछ हिस्से में निर्धारित की जाती है, जो नेटवर्क प्रति दिन खरीद सकता है LT की अधिकतम मात्रा को निर्दिष्ट करता है।

एक्सेस दर = (1/MOR आपूर्ति) * MaxLT
MaxLT = ((MOR कंप्यूट बजट * MOR मूल्य) / LT मूल्य) * 1000
UserMax = MaxLT * User MOR शेष

### उदाहरण के अनुमान:
MOR आपूर्ति = 10,000,000 MOR टोकन
MOR कंप्यूट बजट = प्रतिदिन 3,000 MOR टोकन
MOR मूल्य = $20
LT मूल्य = $0.002 प्रति 1000 LT
User शेष = 5 MOR टोकन

### उदाहरण परिणाम:
MaxLT = 30,000,000,000 LT (यह नेटवर्क प्रति दिन खरीद/उत्पाद कर सकता है की अधिकतम LTs)
AccessRate = 3,000 (इस प्रकार प्रत्येक MOR टोकन 3,000 LTs प्रतिदिन तक पहुंच प्रदान करता है)
UserMax = 15,000 (5 MOR टोकन के साथ एक उपयोगकर्ता प्रतिदिन तक 15,000 LTs तक पहुंच सकता है)


प्रति अवधि (प्रतिदिन), मॉर्फियस एक नेटवर्क के रूप में कंप्यूट प्रदाताओं से X संख्या की LTs खरीदने के लिए पर्याप्त धन होता है। X मॉर कंप्यूट कॉन्ट्रैक्ट द्वारा खर्च करने के लिए तैयार है (कंप्यूट बजट) की मात्रा की एक कार्य है, जो वर्तमान MOR मूल्य से भाग किया गया है LT के बाजार दर से विभाजित किया जाता है।
यदि कंप्यूट बजट 3,000 MOR है, और प्रत्येक $20 का है, तो नेटवर्क उस दिन तक अधिकतम $60,000 के LTs (उत्पाद) खरीद सकता है। यदि 1,000 LTs का जाने वाला मूल्य $0.002 है, तो नेटवर्क उस दिन तक 30 अरब LTs (30m x 1000 LTs) तक खरीद सकता है।
उस संभावित उत्पाद को 30 अरब LT का MOR शेष, प्रो राटा से आवंटित किया जाता है। मान लें कि मौजूदा में 10,000,000 MOR हैं। 500 MOR टोकनों के साथ एक उपयोगकर्ता (कुल का 0.005%) उस दिन तक 1.5m LTs तक मुक्तीपूर्ण रूप से पहुंच सकता है।
जब तक कंप्यूट बजट निर्गमन स्तर पर हो, कंप्यूट कॉन्ट्रैक्ट MOR से खत्म नहीं हो सकता है।
वास्तविकता में, अधिकांश टोकन बटुओं और एक्सचेंजों में बैठेंगे, और केवल एक हिस्सा LT उत्पाद की मांग के लिए उपयोग होगा।


## नोट्स
* MOR की मौलिक मांग उन उपयोगकर्ताओं से होती है जो मॉर्फियस नेटवर्क पर जनरेटिव AI और अन्य प्रकार के कंप्यूट तक पहुंच प्राप्त करना चाहते हैं।

* प्रदाता की हार्डवेयर प्रकार नेटवर्क के लिए अमूर्त है, जब तक वे उपयोगकर्ता के पास/फेल परीक्षण को संतुष्ट कर दें। कोई भी प्रदाता जो वह वहन कर सकता है से अधिक प्रश्नों पर बोल रहा है उन्हें इस परीक्षण को अच्छी तरह से प्रोसेस करने की आवश्यकता है, वह इस परीक्षण में असफल होगा।

* ऊपर का मॉडल विशेष रूप से प्रदाताओं को केवल तब पैसे देता है जब उनके कंप्यूट की मांग होती है। यह उस स्थिति को रोकता है जहां नेटवर्क को इसकी आवश्यकता नहीं होने पर MOR के बड़े हिस्से को पहले ही जारी नहीं किया जाता है।



* प्रदाताओं को एक निर्दिष्ट LLM होने का साबित करने की आवश्यकता होगी, अपनी कुंजी के साथ LLM मॉडल के हैश को साइन करके। यह साबित नहीं करता कि उन्होंने इसे उपयोग किया है, लेकिन यह साबित करता है कि उन्होंने इसे डाउनलोड और स्थापित किया है, जो काम को प्रतिष्ठान, इस प्रकार से कुछ सिबिल-संवेदनशील धरोहर के प्रकारों को रोकता है। यदि प्रदाता उपयोगकर्ता को कूड़े के परिणाम प्रदान करता है, तो उपयोगकर्ता रूटर के पास [असफल] के साथ [मिलीसेकंड] भेज सकता है, और प्रदाता को उस कंप्यूट के लिए क्रेडिट नहीं किया जाएगा। मॉर्फियस को सभी जवाब सही होने की आवश्यकता नहीं है... इसकी आवश्यकता है केवल इसके लिए कि पर्याप्त जवाबें होनी चाहिए, प्रतिस्पर्धी विकल्पों के साथ तुलनात्मक रूप से काफी होनी चाहिए।

* RFC के साथ नेटवर्क को बहप्रवाह करने की सिबिल हमले से बचा जाता है AccessRate के द्वारा। RFC भेजने का "लागत" MOR टोकन प्राप्त करने की लागत है, जो इसके लिए जमा किए गए RFCs की संख्या से विभाजित की जाती है। लागत कभी भी शून्य नहीं है, और फिर भी एक उपयोगकर्ता को प्रति बार RFC बनाने पर कभी भी नुकसान महसूस नहीं होता है।

* Pass/Fail को उपयोगकर्ता द्वारा तय किया जाता है, और इसमें कुछ हद तक गुणवत्ता की पुलिस होती है। उपयोगकर्ता [मिलीसेकंड] के साथ पास/फेल परिणाम को रूटर को वापस भेजता है। अगर असफल, तो या तो कोई पुरस्कार होता है या दंडात्मक अंक (टीबीडी)। प्रदाता को बगैर किसी भी लाभ के एक प्रदाता को झूठा असफल नहीं करने के लिए कोई प्रेर



* सभी चार पक्ष (उपयोगकर्ता, प्रदाता, राउटर, और कंप्यूट कॉन्ट्रैक्ट) को उनकी पहचान के रूप में एकदिवसीय MOR पता है। पक्षों के बीच सभी संदेश हस्ताक्षर की आवश्यकता है (लेकिन अधिकांश को ब्लॉकचेन ट्रांजैक्शन की जरूरत नहीं है)।

* प्रदाताओं को सिबिल हमले से निराश करने के लिए एक गैर-शून्य शेष रखना आवश्यक है।

* यदि [मिलीसेकंड] मानक बढ़ी जाती है, तो नेटवर्क सामान्यत: तेज होगा, लेकिन यह छोटे प्रदाताओं को निराश करेगा।

* धीमे परिणाम प्रदान करने के लिए एक प्रतिस्पर्धा बढ़ावा है (परिणाम की प्रक्रिया के बाद कोई आय नहीं)।

* शुरूआत में केंद्रीय होस्टेड राउटर संभावना से ठीक है (धीरे-धीरे राउटर को अकेला बनाएं (आईपीएफएस? या पोज समूह नोड?))
