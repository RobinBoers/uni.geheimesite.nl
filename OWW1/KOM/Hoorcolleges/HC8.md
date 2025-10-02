causaliteit:

- correlatie (covariantie)
- tijdsvolgorde (temporal precedence)
- interne validiteit (alternatieve verklaringen uitsluiten)

begrijpen (basic), beinvloeden (applied) van de werkelijkheid => causaal verband nodig.

experimenteel onderzoek -> controle -> voorwaarden makkelijker voldoen

beste manier voldoen aan voorwaarden:
- gerandomiseerd onderzoek (vergelijking tussen 2 verondersteld gelijke groepen)
- onderzoeker manipuleert een variabele

PICO:

- Populatie
- Interventie: experimentele conditie, gemanipuleerde variabele (onafhankelijk)
- Comparison: van onderzoeksgroep en de controlegroep
- Outcome: wat gebeurd er met de gemeten variabele (afhankelijk)

heeft het tussentijds reviseren van aantekeningen effect op leerprestaties van studenten?

p = studenten
i = tussentijds reviseren van aantekeningen
c = ...
o = leerprestaties

correlationeel = invloed van natuurlijke variatie in variabelen meten
experimenteel = variabele manipuleren in een gecontrolleerde (lab)setting

temporal precedence verzekeren door te manipuleren te doen *voor* het meten van de afhankelijke variabele

uitsluiten alternatieve verklaringen => 

bedreigeingen van interne validiteit:
- design confounds: is de gemanipuleerde variabele het *enige* verschil in de *behandeling* van de groepen
- selectie effect: zijn de groepen überhaupt wel vergelijkbaar bij aanvang: zijn er geen grote verschillen in *samenstelling* van groepen

groep moet vergelijkbaar zijn mbt afhankelijke var. en *alle* andere var (want je weet niet of die effect zouden kunnen hebben)
indelen door:
- natuurlijke indeling (toevallige plekken bij binnenkomen, eigen keuze deelnemers)
- selectie op basis v persoonskenmerken
- willekeurige toewijzing (randomisatie)

!! welke typen groepen in een experiment

doel van randomisatie:
- gemiddelde en spreiding (scores)
- op alle variabelen (gemeten en ongemeten)
- bij aanvang vergelijkbaar

moet je checken of het 'gelukt' is? -> er is discussie over
  (hangt ook af van steekproefgrootte, maar je kan alleen bekende/gemeten variabelen checken)
  (want rechttrekken op basis van gemeten kenmerk kan op ongemeten kenmerk scheef trekken)
  (dus je *kan* niet zoveel met 'checken'; is alleen later voor interpretatie miss handig)

soms randomisatie niet mogelijk: niet ethisch of praktisch onhaalbaar
  (ethisch: bijv mogelijk betere behandeling niet geven in medisch onderzoek)
  (praktisch: bijv niet handig om de helft van een klas een andere methode te geven)

soms kan het maar gaat het mis:
- deelnemers in experimentele groep delen dingen met deelnemers in de controlegroep
  (= contaminatie, daarom blind)
- deelnemers houden zich niet aan de behandeling/instructies
- beinvloeding door de onderzoeker (zowel bewust als onbewust)
  (daarom dubbelblind)

^^vorm van design confounds

populatie --(aselecte steekproef)--> steekproef --(randomisatie)--> experimentele groep en controlegroep
            ^^externe validiteit                                    ^^interne validiteit

statistisch gezien is 2x aselecte steekproef hetzelfde als 1x aselect+randomisatie

wanneer mag generaliseren: steekproef -> populatie (mits interne en externe validiteit ok)

----
NHST
- formuleren hypotheses (h0 en ha)
- keuze & berekenen van een toetsingsgroothei
- kans bepalen op resultaat of nog extremer gegeven h0
- h0 wel of niet verwerpen
+ conclusie schrijven
----

als h0, dan geen verschil => manipulatie heeft geen effect

nieuwe soort hypothese = statistische hypothese (wiskundige repr. van h0 en ha)
h0 => \mu_{revisie} = \mu_{recopy}
ha => \mu_{revisie} > \mu_{recopy}

correlatie = r-toets, r_s-toets
causatie = t-toets (M1 - M2)

dus: mag generaliseren + is het verschil groot?

verschil afhankelijk van de meeteenheid en schaal
dus: relatief verschil tussen de groepen
- verschil in gem. M1 - M2
- spreiding in scores SD1 en SD2
- grootte van groepen n1 en n2

correlatie verschilt per steekproef. zelfde hier: M1 - M2 ook.
standaardfout (SE) berekenen aan de hand van de gegev. hierboven

t = (M1-M2)/SE

hierdoor cancellen we eenheden elkaar uit => zelfde schaal tussen ongv. -3 en 3
stap op de schaal is 1x de standaardfout

grotere t => grotere verschillen
(t = 1 is één standaardfout, dus dat is ongv de meest logische waarde in geval van h0)

in geval van nulhypothese:

- weinig verschillen tussen groepen
- dus t laag
- dus hoge t = goed, want dan nulhypothese niet geldig

(standaardfout correlationeel = gemiddelde steekproeffout)
(standaardfout experimenteel = ...???)

aan de hand van t kan de computer p berekenen
(want t = equivalent van r, dus gwn weer overschrijdingskans, opp voor extremer)
