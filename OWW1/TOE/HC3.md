enkelvoudige regressie =
1 voorspeller
1 uitkomst

meervoudige/multiple regressie =
1 variabele voorspellen
maar met meerdere voorspellers
aka wiskunde formule met meerdere argumenten

rsme = hoeveel je ernaast zit (lager is nauwkeuriger)

waarom regressiemodellen?
1. voorspellen van kenmerken (x gebruiken om y te voorspellen)
bijv. voor beoordelen of interventie/behandeling nodig is

2. beschrijven van werkelijkheid
hangen variabelen wel/niet samen?
fundamentele onderzoeksvragen

nauwkeurigigere voorspellingen doen? -> meer variabelen gebruiken

meerdere onafhankelijke vars of predictors (x1, x2, x3, ... xk)
y = b0 + b1x1 + b2x2 + b3x3 + ... bkxk

MLR-model wordt zelfde manier gedaan als SLR-model
(dus nog steeds least sum of squared roots)

meer dan 2 onafhankelijke variabelen -> figuur wordt 4D of 5D etc. dus visualiseren kan niet

meer onafhankelijke variabelen -> RSME wordt ALTIJD kleiner (misschien maar een klein beetje, maar wel lager)

gwn 30 miljoen variabelen tracken? -> nee, balans tussen simpel model en nauwkeurig model
is de toevoeging van extra variabelen wel nuttig? kan ook gwn ruis zijn die er niet *echt* toe doet.
beslissen op basis van literatuur etc.

stappenplan:
1. run regressie met alle mogelijk relevante predictorvariabelen
2. beoordeel of model significant is

F-toets: hoeveel spreiding kunnen we verklaren aan de hand van de predictor (R^2)
R^2 = coefficient of determination, gekwadrateerd correlatiecoefficient
percentage van verklaarde variantie
ook de effectgrootte bij regressie

meer onafhankelijke variabelen -> R^2 neemt ook altijd toe

griekse letters populatie

relevantie -> effectgrootte
nauwkeurigheid -> standaardschattingsfout

spaarzaam zijn (parsimonious)
nauwkeurig maar toch eenvoudig
predictorvariabelen alleen gebruiken als ze significant iets toevoegen aan voorspellingen

per onafhnakleijke variabele checken of de rc niet te dicht bij nul ligt
(mbv van een t-toets)

t = rc / SE in dit geval vgm

EEN VOOR EEN VERWIJDEREN (want alle variabelen onderling samenhangend)

je HOEFT niet alle niet-significante voorspellers te verwijderen

ongestandaardizeerd = rc, afhankelijk van originele schaal van de onafhankelijke variabelen

waarden zijn afhankelijk van de eenheden van predictorvariabelen, daardoor kunnen predictorvariabelen niet onderling vergeleken worden

gestandaardiseerd = alle variabelen casten naar de schaal van standaardafwijking
dus als iemand 1 SD hoger scoort dan andere mensen (dus verhouding tussen mensen blijft hetzelfde), hoeveel standaarddeviaties scoor je dan hoger of lager op de afhankelijke variabele

de grootste absolute gestandaardiseerde coefficient geeft aan welke voorspeller de meeste impact heeft op voorspellingen

gestandaardiseerd regressiecoefficient wordt OOK aangegeven met EEN FUCKING BETAAAAAAAAAAAA

why much word if little math do job

wanneer mag je regressieanalyse uitvoeren?
1. linearverband tussen predictorvariabelen xk en y
   controlleren met spreidinsdiagram
   alleen een schending als duidelijke ANDERE relatie
   GEEN relatie schendt deze voorwaarde NIET
2. afhankelijke en onafhankelijke variabelen op interval of ratio meetniveau
3. residuen normaal verdeeld
   controlleren aan de hand van histogram (van (gestandaardiseerde) residuen)
4. residuen gelijkmatig verdeeld (homoscedasticiteit)
   gelijke spreiding langs de regressielijn
   residuenplot (residual plot) -> x as heeft voorspelde waarden en y-as heeft residuen
   homoscedasticiteit = random ass, geen patroon
   homoscedasticiteit = pattron (bow tie of fan/driehoek bijv)
5. geen uitschieters
