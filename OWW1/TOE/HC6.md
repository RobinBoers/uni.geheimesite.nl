nadelen van gepaarde t-toets:

- uitval
- ... (ik zat nie op te letten)

bedreigingen van interne validiteit:

- maturatie: natuurlijke interne ontwikkeling
- history: externe gebeurtenis van buitenaf
- regression to the mean: exttemen trekken bij tweede meting meestal richting gemiddelde, ongeacht ingreep

allemaal opgelost met: controle groep

- observer bias: onderzoeker 'wil' dat het onderzoek slaagt -> onderzoeker doet bewust of onbewust foute/subjectieve rapportage

- demand characteristics: deelnemers 'willen' dat het onderzoek slaagt -> anders gedragen zodat hypothese bevestigd

^anders dan placebo, maar placebo is onbewust

beide opgelost met: dubbelblind experiment (zowel groep als onderzoeker weet niet welke conditie welke is)

- placebo: deelnemers 'denken' dat er verandering is, maar er is geen verandering

opgelost met: blind experiment met controlegroep die een 'nep-behandeling' krijgt

- selectie-effecten: groepen verschillen al voor het experiment

oplossing: randomisatie

geen effect gevonden?
- er is geen effect
- weak manipulation: werkt wel in principe, maar niet goed genoeg toegepast
  (langer gebruiken, hogere dosering nodig etc.)
- power-probleem: niet genoeg data -> GROTERE STEEKPROEF

bedreigingen van interne validiteit bij gepaarde t-toets:

- testing-effect: respondenten kennen het meetinstrument de tweede keer al, dus vullen uit herinnering antwoorden in.
- intstrumentation-effect: als je een ander instrument gebruikt zijn de voor- en na-meting mogelijk niet meer vergelijkbaar.

als meerdere behandelingen: volgorde laten verschillen = counterbalancing (AB-BA), zodat tweede effect niet kleiner lijkt door cumulatief van eerste behandeling.

randomisatie is moeilijk bij te kleine steekproef, omdat het niet lukt om kenmerken eerlijk te verdelen over condities

soms is randomisatie niet ethisch of mogelijk

soms lukt het maar gaat het mis: contaminatie, of manipulatie mislukt doordat deelnemers zich niet aan de interventie houden, of de onderzoeker onbedoeld invloed heeft (eg. sturing).

---

maar wat als: meer dan twee condities

3 groepen -> per 2 de groepsgemiddelden vergelijken
=> niet handig want meer toetsen = meer kans op type I fout
(= kanskapitalisatie)

anova = analysis of variance
onafhankelijke variabele = gemiddelde rekenscore
afhankelijke variabele (factor) = groep/conditie

hypotheses:
H_0: mu_1 = mu_2 = mu_3
H_1: minimaal één van de variabelen is anders
(NIET mu_1 != mu_2 != mu_3, MAAR mu_1 != mu_2 V mu_1 != mu_3 V mu_2 != mu_3)

F-waarde -> p-waarde en dan gwn normaal significatieniveau check
(VRAAG: hoe weet je *welke* afwijkt? je weet nu alleen dat er een willekeurige afwijkt...)

effectgrootte = eta^2 = percentage verklaarde variantie

eta^2 = 0.01 - klein effect
eta^2 = 0.09 - gemiddeld effect
eta^2 = 0.24 - groot effect

^hoe je NIET uit je hoofd te weten, verschillen per vakgebied! krijg je erbij op het tentamen:)

je kan nu statistisch geen uitspraak doen over *welke* groep afwijkt, wel beschrijvend. later krijgen we nog hoe dat statistisch moet.

assumpties anova:

- aselecte steekproef (zoveel mogelijk)
- afhankelijke variabele van interval of ratio, onafhankelijke van nominaal of ordinaal
- onafhankelijke waarnemingen (geen herhaalde metingen)
- groepen onafhankelijk (losse groepen, geen overlap, geen contact)
- geen uitschieters <- milde uitschieters niet erg
- normaal verdeeld <- als N >= 30, schending van normaliteit is fiiiine
- gelijke spreiding/variantie <- alleen probleem als n van grootste groep min 4x zo groot is als n van kleinste of grootste variantie min 10x zo groot als kleinste variantie (variantie = SD^2)

twee rijen in jasp: conditie en residual
conditie = variantie tussen groepen
residual = variantie in groepen (ruis/kans)
de verhouding hiertussen bepaald of F groot of klein is

df (eerste) = aantal groepen, vrijheidsgraden is dan k - 1 (k = aantal groepen)
df (tweede) = totale sample - aantal groepen (N - k)

totale vrijheidsgrade = df_1 + df_2 = N - 1

MS_between = SS_between / df (corrigeert voor aantal groepen)
MS_within = SS_within / df (corrigeert voor aantal mensen)

F = MS_between / MS_within

F-verdeling hangt af van df, en is *altijd* groter dan 0 (want variantie)
