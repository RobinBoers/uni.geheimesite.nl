wanneer goede meetmethode? -> (begrips)validiteit en betrouwbaarheid

betrouwbaarheid = cobsistentie van meting
validiteit = correctheid meting

lage betrouwbaarheid => altijd lage validiteit!!

begripsvaliditeit:
- indruk: lijkt in orde (experts)
- inhoud: alle aspecten?
- convergent: correleert met andere metingen van zelfde construct?
- divergent/distrciminant: correleert niet met andere metingen van een ander construct
- criterium: correleert het met een criteriumvariabele? (voorspellend)

criterium vind ik NOG STEEDS onduidelijk

nog meer kom herhaling:

pearson correlatiecoëfficient: sterkte en richting van linear verband
waarde tussen -1 (negatief verband), 0 (geen verband) en 1 (positief verband)

test-hertest betrouwbaarheid

cronbach's alpha voor interne betrouwbaarheid:
mate van correlatie tusse items binnen de vragenlijst
(aka kan je vragen verwijderen zonder dat je meting naar de tering gaat)

items moeten dezelfde richting hebben: OMPOLEN!!

alpha < 0.7 -> slecht
alpha > 0.8 -> goed

maar natuurlijk afhankelijk van wat je aan t meten bent
(bij medische diagnose neem je een veel hogere waarde bijv)

"item-rest correlatie" of "item-total correlatie" (rit-waarde) = samenhang van item met alle anderen

rit < 0.2 => item correleert niet met schaal van andere items, past niet goed, eventueel verwijderen?

als verwijderen => gaat dan de cronbach's alpha omhoog?
- "cronbach's alpha if item dropped"
- als heel erg omhoog -> dan verwijderen
- MAAR: alleen als inhoud en subjectieve belang van item niet heel groot

stappen van variabele creeeren:
- ompolen
- betrouwbaarheidsanalyse (mogelijk items droppen)
- schaalscore berekenen

kunnen we uit data een verband halen om een relatie te *voorspellen*?

correlatie = sterkte en richting
regressie = lineare relatie als vergelijking -> voorspellingen
"kan een variable worden voorspeld uit een andere variabele?"

variabele die we voorspellen = afhankelijk (y-as)
variabele die we gebruiken = onafhankelijk (x-as) of predictor

twee stappen:
- lijn door punten bepalen
- formule van de lijn bepalen (functiefit)
techniek: least squares regression

residuen = afstand van individuele datapunten tot regressielijn
residu is groter of kleiner afhankelijk van de lijn
dus programma tekent dertig miljoen lijnen ofz en kijkt dan naar de residuen, en kiest die met de minste residuen

lijn met kleinste som van gekwadrateerde residuen wint (kwadraat zodat - en + altijd + worden want statici snappen nog steeds absolute waarden niet)
sum of squared residues (SSR)

weinig spreiding (kleine residuen) => voorspellingen zeer nauwkeurig
meer spreiding (grote residuen) => voorspellingen minder nauwkeurig -> grotere onzekerheid

hoe nauwkeurig zijn voorspellingen? -> standaardschattingsfout
(de standaardfout van regressie = standaardafwijking van residuen)
= grofweg de gemiddelde grootte van fouten die we maken als we voorspellingen doen voor een individu

in JASP: RSME = root mean square error
(gekwadrateerde gemiddelde standaardfout)

regressievergelijking: y = ax + b (maar dan ˆy = b0 + b1x)

dakje (^) betekent schatting
b0 = geschatte waarde van y als x = 0
b1 = richtingscoëfficient

twee modellen: M0 is zonder de X (dus gewoon gemiddelde van alle y's)
               M1 is met de X (dus positie op de regressielijn)
de RSME van M1 zou lager moeten zijn dan bij M0 (aka regressielijn is betere voorspelling dan gemiddelde)
