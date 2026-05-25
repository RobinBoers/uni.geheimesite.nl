herhaalde metingen anova

anova binnen groepen ipv tussen groepen

twee soorten designs:

- between-subjects (onafhankelijke groepen, willekeurig toegewezen)
- within-subjects (gepaarde groepen, pre- en posttest)

quasi-experimenteel: verschillende groepen, maar geen randomisatie
meestal omdat je een bepaalde factor niet kan manipuleren

problemen:
- groepen niet gelijk (bestaande verschillen)
  (bijv: verdeling jongens/meiden, nadenken: is dit belangrijk/relevant)

corrigeren voor groepsverschillen:
extra factor (bijv: gender) toevoegen

dus ipv experimenteel vs controle

experimenteel (M) vs controle (M)
en
experimenteel (F) vs controle (F)

between = verschil tussen GROEPEN
within = verschil tussen MOMENTEN

repeated measures:
- dezelfde personen meerdere keren gemeten
- alle personen alle meetmomenten (complete dataset)
- vergelijken met dezelfde persoon voor/na etc.

kan meer dan meerdere niveaus hebben:
- meerdere tijdsmomenten (voor/mid/na/followup)
- volgorde verschillen??
- of condities -> maar dan toch between..???

standaard between design => evenveel datapunten als deelnemers (want maar 1 meting)

standaard between design => 3 kolommen: ID, conditie = nominaal, score = interval
standaard within design => 3(of meer) kolommen: ID, voor = inteval, ... na = inteval (dus elk 'niveau' is een kolom ipv een nominale waarde in conditiekolom)

within kan over *tijd* of *conditie*/*niveau* = onafhankelijke variabele
score = afhankelijke variabele

voordelen:
- controlleren voor bestaande verschillen tussen personen (want exact zelfde personen)
- minder mensen nodig, want elke persoon geeft meer data -> goedkoper
- grotere statistische power: mogelijkheid om effect te vinden; want meer observaties->minder 'error variance'(??)

nadelen:
- volgeorde of 'carry-over' effecten (leereffecten, verveeldheid, maar kan ook matureiteit zijn denk ik...)
  -> oplossing: counterbalancing (aka volgorde randomiseren)

- leereffecten: mensen worden 'vanzelf' beter
  -> oplossing: counterbalancing of contorlegroep

- grotere inspanning voor participanten -> grotere kans op uitval + je kan uitval niet makkelijk vervangen
  -> beloningen (per sessie + bonus aan het einde)

vb:
angstvermindering

twee approaches:

- naive benadering (exploratief):
  - geen voorkennis/hypothese
  - is er een verschil
  - gewoon twee metingen doen en kijken
  - omnibus

- geinformeerde benadering (confirmatief):
  - voorkennis/vermoeden/hypothese
  - is een verwacht verschil: na lager dan voor, en stabiel (dus bij followup ook; geen 'terugval')
  - constrasten

ombibus anova vw:
- meetniveaus: categorisch en interval/ratio
- onafhankelijke groepen
- geen uitschieters op afh var
- normaliteit van scores
- homoscedasiciteit (homogeniteit variantie)

herhaalde anova vw:
- meetniveaus: categorisch en interval/ratio
- geen uitschieters op afh var
- normaliteit van scores BINNEN ELK MEETMOMENT
- sfericiteit -> ...???

sfericiteit: homogeniteit variantie VAN VERSCHILSCORES

verschilscores (delta) tussen momenten

de variantie daarvan
PER MEETMOMENT
moet ongv gelijk zijn

dat komt neer op: A&B verschillen ongv net zo erg als B&C en A&C

dus TUSSEN TIJDSMOMENTEN mogen ze erg verschillen
als ze maar wel TUSSEN PERSONEN ongv evenveel blijven verschillen

aka als er een grote verandering is moet iedereen die grote verandering hebben
(in je conditie probs maar ok)

sfericiteit met Mauchly's test

je wil juist dat deze test NIET significant is (want je wil GEEN variantie)
maar ook correcties, afh van mate van schending (epsilon tussen 1 en 0):
- 1: volledige sfericiteit, geen schending
- > 0.75: matige schending, kleine correctie: Huynh-Feldt correctie
- < 0.75: ernstige schending, grote correctie: Greenhouse-Geisser correctie

jasp geeft twee epsilonwaardes, je mag hoogste gebruiken

posthoc op herhaalde anova doen we niet in toe

effectgrootes: eta^2 = proportie van variantie within-subjects verklaard door de onafh var
  (= gecorrigeerd voor verschillen tussen personen = optimistisch -> huh waarom ik niet snap)
               eta^2_G = proportie totale variantie verklaard door de onafh var
  (= conservatiever, dus beter te generaliseren naar andere studies)

bij specifieke verwactingen mogen we ombibus anova skippen!! yay
MAAR: WEL ASSUMPTIES EERST CHECKEN!!!!!

