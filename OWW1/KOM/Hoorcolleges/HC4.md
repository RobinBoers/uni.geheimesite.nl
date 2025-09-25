---
title: Hoorcollege 4
---

Kwantitatief onderzoek: correlationeel + experimenteel

signaalwoorden kwantitatief: samenhang, relatie, mate, toe/afname, meer/minder, lang(er)/kort(er)

correlationeel: samenhang/relatie/verband tussen variabelen/kenmerken/eigenschappen

theorie -> onderzoeksvraag (deductief)

hw: verschillen (2) in cyclus tussen kwalt. en kwant. onderzoek vinden

elementen correlationele onderzoeksvraag: CAPS

- **Constructs**: de variabelen/kenmerken waartussen je de relatie wil weten
  (tenminste 2, voor KOM ook max 2, meer kan wel in praktijk)
- **Association**: wat voor soort samenhang/relatie/verband verwacht wordt
- **Population**: welke doelgroep? (mensen, dieren, objecten etc.)
- **Setting**: specifieke plek/locatie (sociaal-economische context)

elementen (wederom) niet noodzakelijk, maar een goed handvat voor maken en herkennen
van onderzoeksvragen.

verschil: positieve/negatieve terugkoppeling/relatie (aka de rc van wisk)

scatterplot = spreidingsdiagram

kenmerken *hangt samen met* verandering in andere variabele => **correlatie**
als het kenmerk de verandering ook *veroorzaakt* (oorzaak-gevolg verband) => **causaliteit**

signaalwoorden causatie: beinvloedt, leiden tot

voorwaarden causaliteit:

- covariantie: ..????? - het moet gwn gecorreleerd zijn???
- temporal precedence: volgorde in tijd
- interne validiteit: alternatieve verklaringen uitgesloten

je kan op basis van grafiek alleen niet een causaal verband herkennen,
want je mis twee van de bovenstaande kenmerken

voor andere twee factoren is een heel gecoordineerde onderzoeksopzet nodig
-> komt later bij experimenteel onderzoek

soms is er een derde factor die beide factoren beinvloed waardoor er een causaal verband *lijkt* te zijn
bijv. meer ijsjes verkocht => meer mensen aangevallen door haaien. derde factor: lekker weer (dus meer mensen in de zee)

dataverzamelingsmethoden:

- observatie/etnografie -> niet beschrijvend, maar systematisch (gedragskenmerken tellen)
  het hoeft niet holistisch -> we gaan mensen en gedrag reduceren tot getallen
- bestaande (big) data
- surveys (vragenlijsten)

bestaande data:

- kwalitatief - aantekeningen leerkracht mbt gedrag en werkhouding
- kwantitatief - scores uit de periodieke CITO toetsen en leerlingvolgsysteem

vragenlijst - face-to-face, online, telefonisch (bijv. tentamen, cursusevaluatie)
nauwkeuriger als je meerdere vragen over hetelfde theoretische begrip stelt (meerdere aspecten)

hoe meten we
- fysieke kenmerken zijn eenvoudig te meten
- theoretische begrippen moeten meetbaar *gemaakt* worden (= operationalisatie)
  (bijv. plezier, agressie, perfectie etc.)

voor meten:
- conceptuele definitie nodig (moet eenduidig zijn) -> wat bedoelen we precies
  => komt voort uit literatuur en discussies met collega's etc; moet in samenwerking.
- hoe gaan we het daadwerkelijk (meestal indirect) meten -> operationele definitie

kenmerk --- operationaliseren --> variabele (neemt een waarde aan)

fysieke kenmerken hebben bijna altijd al een eenheid en meetinstrumenten

theoretische begrippen hebben vaak ook al een bestaande scoreschaal
- IQ test Wechsler Adult Intelligence Scale (60-140)
- Rosenberg's Self-Esteem Scale (0-30)
- Becks's Depression Scale (0-63)

gebruiken vaak een Likert schaal (strongly disagree, disagree, agree, strongly agree)

^^voorbeelden

operationaliseren/meetbaar maken is een volledig werkveld

vaak in een vragenlijst stellen we vragen is positieve/negatieve manier,
om mensen scherp te houden zodat ze de vragen blijven lezen

antwoorden platslaan tot totaalscore/soort cijfer (= schaalscore)

daarvoor moet een hoge score wel steeds hetzelfde betekenen -> ompolen

verschillende soorten waardes (= basically data types)

- getallen (= basically int/float) -> kwantatieve variabelen (scalars??)
- categorien (= basically enum) -> categorische variabelen
en denk ik: vrije tekst/open vraag (= basically str)

!!! meetniveaus -> zie slides (kan een coole tabel worden lol)

populatie
onderzoek op kleine groep (want gehele populatie onderzoeken is te duur/tijdsconsumerend/onmogelijk)
maar uitspraak over geheel doen

generaliseren naar gehele populatie = inferentie (van engelse 'to infer' probs)

dit gaat over externe validiteit (geldigheid) = meet je wat je wil meten,
  aka zijn deze resultaten geldig voor de gehele populatie.

mag alleen als de steekproef goed wordt getrokken
- populatie helder definiëren
- aselect: willekeurig (want representativiteit -> afspiegeling van geheel)

selecte steekproef (zoals gemakssteekproef) -> niet gebaseerd op kansen, dus
kan vertekening (= bias) veroorzaken, waardoor je niet kan generaliseren
(want externe validiteit laag)

aselecte steekproeven:

- enkelvoudig aselecte steekproef (simple random sample):
  je pakt willekeurig (met computer) mensen uit een lijst

  voordelen: elke participant gelijke kans
             elke combinatie gelijke kans

VRAAG: willekeur garandeerd toch geen representatieviteit
(aka je kan willekeurig perongeluk alleen sociale wetenschap studenten selecteren)

MAAR: soms is er geen lijst of is de lijst incompleet (= dekkingsfout -> leidt tot vertekening v. werkelijkheid)
(en dan mis je dus mensen als je een steekproef van die lijst doet)

je weet vaak niet hoe groot je dekkingsfout is.

dekkingsfout: je kan alleen generaliseren naar het deel van de populatie dat wél gedekt was

nog een probleem: weigeren mee te doen (non-response) -> incomplete dataset -> ook vertekening
(tevreden mensen de evualatie minder vaak in dan ontevreden mensen)

soms verschillen aantallen binnen de populatie drastisch, waardoor de kans dat je de kleine groep
in je steekproef hebt zitten vrij klein is. oplossing: twee steekproeven: 1 van de grote en 1 van de kleine groep
VRAAG: is het dan nog wel aselect??

^^andere soorten steekproeven: gestratificeerde steekproeven

representativiteit = kenmerken uit populatie in dezelfde verhouding terugzien in steekproef

- beschrijvende statistiek (populaties) = uitspraak doen op basis van gehele data
- inferentiële statistiek (steekproeven) = subset generaliseren naar gehele populatie (= inferentie)
