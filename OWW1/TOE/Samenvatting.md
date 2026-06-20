---
title: Toepassing van onderzoeksmethoden en statistiek
---

> Deze is nog niet af. Ik verwacht 21 juni klaar te zijn. Deze samenvatting veronderstelt voorkennis van [KOM](../KOM/Samenvatting.md).

<br>

<style>
  main p span, main li span, main details span {
    font-family: sans-serif;
    font-size: 0.9em;
    display: inline-block;
    padding: 0px 5px;
    border: 1px solid #737373;
    border-radius: 4px;
  }
  main span.sub::before {
    content: "› ";
  }
  main span.root::before {
    content: "☰ ";
  }
  main span.current::before {
    content: "▼ ";
  }
  main span.check::before,
  main span.input::before,
  main span.opt::before {
    content: "☐ ";
  }
  .box {
    position: relative;
  }
  .box h4 {
    margin-top: 0;
    text-transform: uppercase;
    font-family: sans-serif;
    font-size: 0.7em;
  }
  .box h4.inline {
    display: inline-block;
    margin-right: 0.25em;
  }
  .box h4.inline::after {
    content: ":";
  }
  .box h4:not(.inline) {
    position: absolute;
    left: 15px;
    top: 15px;
  }
  .box h4 + ul {
    margin-top: 1.75em;
    margin-bottom: 0.5em;
    margin-left: 5px;
    padding-left: 0;
    list-style: none;
  }
</style>

## Beschrijvende statistieken

Je kan beschrijvende statistieken opvragen voor één of meer variabelen opvragen via <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>.

Het is ook mogelijk om te splitsen op een andere variabelen (via <span class="input">Split</span>). Deze variabele mag maximaal 10 niveau's hebben.

### Frequentietabellen

Onder <span class="current">Tables</span> <span class="sub">Frequency tables</span> is het mogelijk om frequentietabellen op te vragen. Ook hierbij mag de variabele maximaal 10 niveau's hebben.

### Grafieken

Je kan verschillende grafieken opvragen, afhankelijk van het meetniveau van de variabele:

- **Categorische variabelen** (nominaal, ordinaal)

  - Staafdiagram: <span class="current">Basic plots</span> <span class="sub">Distribution plots</span>
  - Cirkeldiagram: <span class="current">Basic plots</span> <span class="sub">Pie charts</span>

- **Schaal variabelen** (interval, ratio)

  - Histrogram: <span class="current">Basic plots</span> <span class="sub">Distribution plots</span>
  - Boxplots: <span class="current">Customizable plots</span> <span class="sub">Boxplots</span>
  - Spreidingsdiagram: <span class="current">Customizable plots</span> <span class="sub">Scatter plots</span>

## Databewerking

### Filteren

Het is mogelijk om rijen (bijv. uitschieters) uit de dataset te filteren. Klik daarvoor in het data-overzicht bovenin op <span><svg width="10px" height="10px" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M1 1H15V4L10 10V16H6V10L1 4V1Z" fill="#000000"/></svg></span>. Je kan dan R-code typen of visueel een filter samenstellen. Een filter kan bijv. zijn:

\\[(id \neq 12) \land (id \neq 16)\\]

### Ompolen

Het is mogelijk om nieuwe kolommen/variabelen te berekenen met een formule op basis van andere kolommen/variabelen, klik daarvoor <span>+</span> aan de rechterkant. Je kan dit gebruiken om variabelen om te polen. Dat doe je door deze formule:

\\[\text{minimale waarde} + \text{maximale waarde} - \text{naam van kolom}\\]

<details open>
  <summary>Voorbeeld</summary>
  Stel een item \(Q_5\) met een bereik van 3 tot 9. De formule voor \(Q_{5,R}\) is dan:
  \[3 + 9 - Q_5\]
</details>

### Schaalscores

Je kan dezelfde techniek gebruiken om kolommen/variabelen voor schaalscores toe te voegen. Er zijn twee soorten schaalscores:

- Een **somscore** (\\(\Sigma M\\)) bereken je door \\(Q_1 + Q_2 + Q_3 ... Q_n\\)
- Een **gemiddelde** (\\(\Sigma M/ n\\)) bereken je door \\((Q_1 + Q_2 + Q_3 ... Q_n) / n\\)

De R-code voor het berekenen van een somscore is:

```R
apply(data.frame(Q1, Q2, Q3), 1, mean, na.rm=True)
```

<!--
> Ik weet eerlijk gezegd niet wat het verschil is tussen dit en gewoon `Q1 + Q2 + Q3`.
-->

Het is ook mogelijk om een gewogen gemiddelde te berekenen. Daarbij tellen bepaalde vragen zwaarder mee dan anderen. Dit wordt niet behandeld bij TOE en is geen tentamenstof.

## Onderzoeksontwerp

- **Between-subjects** (dwarsdoorsnede<!--/cross-sectioneel--> panel): proefpersonen worden met elkaar vergeleken.

  <div class="box">
  <h4>Voordelen</h4>
  <ul>
  <li>Geen volgorde- of leereffecten.</li>
  <li>Lagere investering nodig<!--, lagere drempel voor deelname-->, minder uitval (attrition).</li>
  <li>Nuttig voor effecten op groepsniveau.</li>
  </ul>
  </div>

  <div class="box">
  <h4>Nadelen</h4>
  <ul>
  <li>Bestaande verschillen. Oplossingen: randomisatie en grotere steekproef.</li>
  <li>Lagere power, meer observaties nodig. Oplossingen: grotere steekproef.</li>
  </ul>
  </div>

- **Within-subjects** (longitudinaal panel): proefpersonen worden met zichzelf vergeleken.

  <div class="box">
  <h4>Voordelen</h4>
  <ul>
  <li>Controlleert voor bestaande verschillen.</li>
  <li>Kan leeftijds-, periode-, of cohort-effecten vinden.</li>
  <li>Hogere power, minder observaties nodig. Goedkoper.</li>
  <li>Nuttig voor effecten op individueel niveau.</li>
  </ul>
  </div>

  <div class="box">
  <h4>Nadelen</h4>
  <ul>
  <li>Volgorde-effecten. Oplossingen: counterbalancing.</li>
  <li>Leereffecten. Oplossingen: counterbalancing.</li>
  <li>Grotere investering nodig<!--, hogere drempel voor deelname-->, meer uitval (attrition). Oplossingen: beloningen.</li>
  </ul>
  </div>

  > Volgorde-effecten houdt in dat de scores van eerdere meetmomenten invloed hebben op de scores van latere meetmomenten. Leereffecten (aka "panel conditioning") houdt in dat de prestatie verbetert over tijd, los van manipulatie. Beide worden opgelost door counterbalancing: het randomiseren van de volgorde.
  
## Data-analyse

### Correlatie

Een correlatie gebruik je om het verband tussen twee variabelen te bepalen. Je doet dit aan de hand van een visuele check en een Pearson- of Spearman-correlatiecoëfficient.

Voordat je een correlatiecoëfficient mag berekenen moeten eerst de voorwaarden gecheckt worden:

<div class="box" style="width: 50%; float: left; border-right: 2px solid white;">
<h4>Voorwaarden Pearson-correlatie</h4>
<ul>
  <li>Aselecte steekproef</li>
  <li>Minimaal interval/ratio</li>
  <li>Linear verband</li>
</ul>
</div>

<div class="box" style="width: 50%; float: right; border-left: 2px solid white;">
<h4>Voorwaarden Spearman-correlatie</h4>
<ul>
  <li>Minimaal ordinaal, of:</li>
  <li>Ordinaal gemaakt met rangscores</li>
  <li>Monotoom verband</li>
</ul>
</div>

De voorwaardes van steekproef en meetniveau kan je bepalen zonder statistiek. Het soort verband bepaal je aan de hand van een spreidingsdiagram.

Dit doe je door: <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>, en kies twee variabelen. Plot daarna een spreidingsdiagram via <span class="current">Customizable plots</span> <span class="sub">Scatter plots</span>.

<div class="box">
  <h4>Instellingen</h4>
  <ul>
    <li><span class="opt">Graph right</span>: <kbd>None</kbd></li>
    <li><span class="opt">Graph above</span>: <kbd>None</kbd></li>
    <li><span class="opt">Regression line</span>: <kbd>None</kbd></li>
  </ul>
</div>

Als er sprake is van een linear verband mag je een Pearson-correlatie bepalen, anders alleen een Spearman-correlatie. Beide doe je via <span class="root">Regression</span> <span class="sub">Classical</span> <span class="sub">Correlation</span>. Je kiest dan onder <span>Sample Correlation Coefficient</span> (linkerkolom) voor <span class="check">Pearson's r</span> of <span class="check">Spearmans's rho</span>.

Na het selecteren van de variabelen zie je de correlatiematrix. Bij twee variabelen is die makkelijker leesbaar als je <span class="check">Display pairwise</span> aanvinkt. In de tabel staat de \\(r\\) of \\(\rho\\) met de bijbehorende \\(p\\)-waarde.

### Betrouwbaarheidsanalyse

Een betrouwbaarheidsanalyse gebruik je om de onderlinge samenhang van items in een meetinstrument (bijv. vragenlijst) te checken. Je doet dit aan de hand van Cronbach's alpha (\\(\alpha\\)).

Om een betrouwbaarheidsanalyse uit te voeren ga je naar <span class="root">Reliability</span> <span class="sub">Unidimensional Reliability</span>, en kies je alle variabelen van het meetinstrument.

<div class="box">
  <h4>Instellingen</h4>
  <ul>
    <li><span class="check">Coefficient \(\omega\)</span> uit</li>
    <li><span class="check">Coefficient \(\alpha\)</span> aan</li>
    <li><span class="check">Coefficient \(\alpha\) (if item dropped)</span> aan</li>
    <li><span class="check">Item-rest correlation</span> aan</li>
  </ul>
</div>

> Soms duurt het heel lang om de betrouwbaarheidsanalyse uit te voeren, of lukt het helemaal niet. Gebruik dan <span class="current">Advanced</span> <span class="sub">Confidence Intervals</span> <span class="check">Bootstrapped Interval</span>.

De betrouwbaarheidsanalyse geeft twee resultaten: een Cronbach's \\(\alpha\\) en een tabel met items. In de tabel laat de <span>item-rest correlation</span> (ookwel \\(rit\\)-waarde) zien hoe sterk een item samenhangt met de rest, en de <span>Cronbach's alpha if dropped</span> laat zien wat er \\(\alpha\\) zou gebeuren als het item verwijderd zou worden.

Als \\(rit < .20\\) en \\(\alpha\\) sterk stijgt bij verwijderen, moet een item verwijderd worden. Je haalt het item dan uit de betrouwbaarheidsanalyse, en neemt het niet meer mee in het berekenen schaal&shy;scores. Houdt hierbij wel rekening met de inhoudelijke en subjectieve relevantie van het item.

> Alle data in de tabel staat met elkaar in samenhang. Het is daarom uitermate belangrijk dat er <strong>maximaal één item per keer wordt verwijderd!</strong>

Voor de interpretatie van Cronbach's \\(\alpha\\) geldt binnen de sociale wetenschappen:

| Cronbach's \\(\alpha\\) | interpretatie |
|-------------------------|---------------|
| \\(< .70\\)             | slecht        |
| \\(< .80\\)             | gemiddeld     |
| \\(> .80\\)             | goed          |

> Dit is afhankelijk van de consequenties bij foute interpretatie. Voor medisch onderzoek zou je waarschijnlijk een hogere grenswaarde hanteren dan binnen de sociale wetenschappen.

### Regressie

Bij regressie maak je een model waarmee je op basis van één of meer predictorvariabelen voorspellingen kan doen over een andere variabele. We noemen de predictorvariabelen onafhankelijk (\\(x\\)-as), en de voorspelde variabele afhankelijk (\\(y\\)-as). Bij enkelvoudige regressie (<abbr title="Simple Linear Regression">SLR</abbr>) is één predictorvariabele, bij meervoudige regressie (<abbr title="Multiple Linear Regression">MLR</abbr>) zij er meerderen.

<details>
  <summary>Hoe werkt dit?</summary>
  <p>Een regressie bepaalt de meest accurate lijn door een puntenwolk, en drukt deze lijn uit als wiskundig verband. Dit noemen we functiefit. De techniek die hiervoor gebruikt wordt heet <em>least squares regression</em>. Daarbij wordt voor elke punt de afstand tot de lijn (&quot;residu&quot;) bepaald, en de lijn met de laagste som van gekwadrateerde residuen (&quot;sum of squared residues&quot;) wint. <!--(Het kwadraat is zodat positieve en negatieve residuen elkaar niet opheffen.)--></p>
  <ul>
  <li>Als er weinig spreiding is (kleine residuen), zijn voorspellingen nauwkeuriger.</li>
  <li>Als er meer spreiding is (grotere residuen), zijn de voorspellingen minder nauwkeurig.</li>
  </ul>
  <p>De standaardschattingsfout (\(\text{RMSE}\)) is de standaarddeviatie van de residuen, en drukt de nauwkeurigheid van voorspellingen uit.</p>
</details>

#### Assumpties

Voordat je een regressie mag uitvoeren moeten eerst de voorwaarden gecheckt worden:

<div class="box">
  <h4>Voorwaarden</h4>
  <ul>
    <li>Minimaal interval/ratio</li>
    <li>Geen uitschieters</li>
    <li>Normale verdeling van residuen</li>
    <li>Gelijke spreiding van residuen</li>
    <li>Linear verband<small><sup>*</sup></small></li>
  </ul>
</div>

> "Gelijke spreiding", "homogeniteit van variantie" en "homoscedasticiteit" betekenen hetzelfde. In deze samenvatting gebruik ik overal "gelijke spreiding" omdat ik dat het makkelijkst te begrijpen vind.

De voorwaarde van meetniveau kan je bepalen zonder statistiek. De uitschieters en spreiding kan je opvragen: (Over de normaliteit werd niks gezegd in het hoorcollege of de Grasples.)

- De lineariteit controlleer je via <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>. Kies de afhankelijke variabele en split op de onafhankelijke variabele (doe dit per predictorvariabele).

  > <small><sup>\*</sup></small>Deze voorwaarde is alleen geschonden als er *een duidelijk ander verband* zichtbaar is. Als er *geen verband* zichtbaar is is de voorwaarde *niet geschonden*.

- Uitschieters controlleer je via <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>. Kies de afhankelijke variabele. Vraag dan via <span class="current">Customizable plots</span> <span class="sub">Boxplots</span> een boxplot op, en doe een visuele check.

- De normaliteit controlleer je via <span class="current">Residual plots</span> <span class="sub">Residuals histogram</span> tijdens de analyse zometeen. Doe een visuele check op de histogram.

- De spreiding controlleer je via <span class="current">Residual plots</span> <span class="sub">Residuals vs. predicted</span> tijdens de analyse zometeen. Het is goed als er geen duidelijk patroon (bijv. driehoek, bowtie etc.) in de diagram zit.

#### Analyse uitvoeren

Je voert een regressie uit via <span class="root">Regression</span> <span class="sub">Classical</span> <span class="sub">Linear Regression</span>. Je kiest dan bij <span class="input">Dependent Variable</span> de afhankelijke variabele en bij <span class="input">Covariates</span> de onafhankelijken.

#### Resultaten interpreteren

De regressie geeft drie resultaten:

- In <span>Model Summary</span> zijn drie waardes te zien (gecorrigeerde \\(R^2\\) mag je negeren):

  - \\(R\\) is de Pearson-correlatiecoëfficient tussen de variabelen bij enkelvoudige regressie, en mag je negeren bij meervoudige regressie.
  - \\(R^2\\) is de effectgrootte: het percentage van de variantie (op de afhankelijke variabele) die door het model verklaard kan worden.
  - \\(\text{RMSE}\\) (Root Mean Squared Error) is de standaardschattingsfout, die aangeeft hoe accuraat de voorspellingen van ons model zijn.

  > De \\(\text{RMSE}\\) geeft de nauwkeurigheid van het model, de \\(R^2\\) geeft de relevantie.

- In <span>ANOVA</span> staat een \\(F\\)-toets die de significantie van het model checkt. <!-- VRAAG: welke variantie wordt hier berekend?? variantie waarvan?? -->

  <div class="box" style="margin-left: 2em"><h4 class="inline">Hypotheses</h4> \(H_0: \rho = 0\) en \(H_A: \rho > 0\)<!--<br><small>(de variantie kan nooit \(<small 0\) zijn, dus daarom een eenzijdige toets)</small>--></div>

- In <span>Coefficients</span> geeft ons coëfficienten per predictorvariabele:

  - **Unstandardized** (\\(b\\)) geeft aan hoeveel punten de afhankelijke variabele stijgt als de predictorvariabele met één punt toeneemt. We noemen dit de richtingscoëfficient.

  - **Standardized** (\\(\beta\\)) geeft aan hoeveel SD de afhankelijke variabele stijgt als de predictorvariabele met één SD toeneemt. Wordt gebruikt voor de \\(t\\)-toets, die aangeeft of de richtingscoëfficient invloed heeft (aka significant verschilt van nul).

    <div class="box"><h4 class="inline">Hypotheses</h4> \(H_0: \beta = 0\) en \(H_A: \beta \neq 0\)</div>

  Daarnaast staan er nog een aantal waardes in deze tabel:

  - **\\(M_0\\) (Intercept)** is de beste voorspelling *zonder predictorvariabelen*<!--; gemiddelde van alle \\(y\\)-waarden-->.
  - **\\(M_1\\) (Intercept)** is het snijpunt van het model en de \\(y\\)-as (later aangegeven met \\(b_0\\)).

Dus de \\(F\\)-toets uit <span>ANOVA</span> geeft de significantie van het *gehele model*, en de \\(t\\)-toets uit <span>Coefficients</span> geeft de significantie van *individuele predictorvariabelen*.

#### Formule opstellen

Mits significant, kan je het model weergeven als wiskundige functie in de vorm \\(y = ax + b\\):

\\[\hat{y} = b_0 + b_1 x_1 + b_2 x_2 + b_3 x_3 ... b_n x_n\\]

Waarbij \\(b_0\\) het snijpunt met de \\(y\\)-as is, \\(b_n\\) de richtingscoëfficient van de predictorvariabele, en \\(x_n\\) de waarde van de predictorvariabele. Het dakje geeft aan dat het om een voorspelling gaat.

<details open>
  <summary>Balans vinden tussen eenvoud en nauwkeurigheid</summary>
  <p>Het toevoegen van meer predictorvariabelen zal altijd zorgen voor een toename van \(R^2\) en een afname van \(\text{RMSE}\). Echter is het belangrijk om een balans te vinden tussen de hoeveelheid predictorvariabelen; het doel is een spaarzaam (‘parsimonious’) model dat eenvoudig én nauwkeurig is.</p>
</details>

### \\(t\\)-toets

Een \\(t\\)-toets gebruik je om twee groepen met elkaar te vergelijken, bij between-subjects designs. Als er sprake is van onafhankelijke groepen mag je de Indepentent Samples T-Test uitvoeren, bij afhankelijke groepen (bijv. bij gepaarde of herhaalde metingen) gebruik je de Paired Samples T-Test.

#### Assumpties

Voordat je een \\(t\\)-toets mag uitvoeren moeten eerst de voorwaarden gecheckt worden:

<div class="box" style="width: 50%; float: left; border-right: 2px solid white;">
<h4>Voorwaarden Independent T-Test</h4>
<ul>
  <li>Aselecte steekproef</li>
  <li>Onafhankelijke groepen</li>
  <li>Minimaal interval/ratio</li>
  <li>Normale verdeling</li>
  <li>Gelijke spreiding</li>
</ul>
</div>

<div class="box" style="width: 50%; float: right; border-left: 2px solid white;">
<h4>Voorwaarden Paired T-Test</h4>
<ul>
  <li>Aselecte steekproef</li>
  <li>Minimaal interval/ratio</li>
  <li>Normale verdeling</li>
</ul>
</div>

<div style="clear: both"></div>

De voorwaardes van steekproef, onafhankelijkheid en meetniveau kan je bepalen zonder statistiek. De verdeling en spreiding kan je opvragen:

- De normaliteit controlleer je via <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>. Kies de afhankelijke variabele en split op de onafhankelijke variabele. Vraag dan via <span class="current">Basic plots</span> <span class="sub">Distribution plots</span> een histogram op, en doe een visuele check.

- De spreiding controlleer je ook via <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>. Kies weer de afhankelijke variabele en split op de onafhankelijke variabele. Vraag nu een boxplot op via <span class="current">Customizable plots</span> <span class="sub">Boxplots</span>, en check of de IQR ongeveer gelijk zijn.

- Het is ook mogelijk om de spreiding te controlleren aan de hand van de \\(SD\\). Dit kan via <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span> of door zometeen bij de analyse <span class="check">Descriptives</span> aan te vinken. Als de \\(SD\\)'s ongeveer gelijk zijn is het goed.

<details open>
  <summary>Wat als voorwaarde van spreiding geschonden is?</summary>
  Het is niet super erg, want de \(t\)-toets (en straks ook ANOVA) zijn robuust tegen kleine schendingen. Je mag de toets nog steeds uitvoeren als:
  <ul>
    <li>De grootste groep maximaal 4x groter is dan de kleinste groep, en:</li>
    <li>de variantie (\(SD^2\)) van de grootste groep maximaal 10x groter.</li>
  </ul>
</details>

#### Analyse uitvoeren

Je voert een \\(t\\)-toets uit via <span class="root">T-Tests</span> <span class="sub">Classical</span> <span class="sub">Indepentent Samples T-Test</span> of <span class="sub">Paired Samples T-Test</span>. Je kiest dan bij <span class="input">Dependent Variables</span> de afhankelijke variabele en bij <span class="input">Grouping Variable</span> de onafhankelijke.

#### Resultaten interpreteren

De \\(t\\)-toets geeft een \\(t\\)-waarde en bijbehorende \\(p\\)-waarde. Deze interpreteer je aan de hand van het gekozen significantieniveau (\\(\alpha\\)). Bij een gerichte hypothese controlleer je eerst de richting en halveer je vervolgens de opgevraagde \\(p\\)-waarde.

Als het verschil significant is, kan je ook de effectgrootte opvragen door onder <span class="check">Cohen's d</span> aan te vinken onder <span>Additional Statistics</span> <span class="sub">Effect size</span>.

<div class="box"><h4 class="inline">Hypotheses</h4> \(H_0: \mu_1 = \mu_2\) en \(H_A: \mu_1 \neq \mu_2\) <small>(of een gerichte hypothese)</small></div>

Voor de interpretatie van effectgroottes geldt binnen de sociale wetenschappen:

| \\(d\\)   | interpretatie |
|-----------|---------------|
| \\(0.2\\) | klein         |
| \\(0.5\\) | matig         |
| \\(0.8\\) | groot         |

### ANOVA

Een ANOVA ('analysis of variance') gebruik je om meer dan twee groepen met elkaar te vergelijken, bij between- en within-subjects designs.

<details open>
  <summary>Waarom ANOVA?</summary>
  <p>Als je meer dan twee groepen hebt, kan je ze twee-bij-twee met elkaar vergelijken met een \(t\)-toets. Je moet dan \(k - 1\) toetsen uitvoeren, waarbij \(k\) het aantal groepen is. Echter, elke vergelijking heeft een kans op een type I fout, waardoor de totale kans op een type I fout sterk toeneemt. Dit noemen we kanskapitalisatie.</p>
  <p>Door de verhouding van variantie binnen en tussen groepen te berekenen, is het wél mogelijk om te bepalen of een groep significant van de andere groepen verschilt, zonder kanskapitalisatie. Dat is wat een ANOVA doet.</p>
</details>

#### Verschillende soorten ANOVA

Er zijn een aantal verschillende soorten ANOVA:

- **Een- vs meerweg**: Bij een eenweg ANOVA is er één onafhankelijke variabele met drie of meer niveaus. In een meerweg ANOVA zijn meerdere onafhankelijke variabelen.

  Meerweg ANOVA wordt niet behandeld in TOE en zijn geen tentamenstof.

- **Omnibus vs herhaald**: Bij een omnibus ANOVA moeten groepen onafhankelijk zijn. Je gebruikt dit voor between-subject designs. In het geval van afhankelijke groepen (bijv. bij gepaarde of herhaalde metingen) gebruiken we een ANOVA voor herhaalde metingen. Je gebruikt dit bij within-subject designs.

  De ANOVA voor herhaalde metingen wordt in een volgende sectie toegelicht.

- **Geplande contrasten**: Een ANOVA is standaard ongericht: je hebt vooraf geen verwachting welke groep van de rest zal verschillen. In een ANOVA met geplande contrasten heb je wél een verwachting. Je kan geplande contrasten gebruiken bij zowel een omnibus ANOVA als een ANOVA voor herhaalde metingen.

  De ANOVA met geplande contrasten wordt ook in een volgende sectie toegelicht.

#### Assumpties

Voordat je een ANOVA mag uitvoeren moeten eerst de voorwaarden gecheckt worden. Deze zijn hetzelfde als bij de \\(t\\)-toets.

<div class="box">
<h4>Voorwaarden omnibus ANOVA</h4>
<ul>
  <li>Aselecte steekproef</li>
  <li>Onafhankelijke groepen</li>
  <li>Minimaal interval/ratio</li>
  <li>Geen uitschieters</li>
  <li>Normale verdeling</li>
  <li>Gelijke spreiding</li>
</ul>
</div>

De voorwaardes van steekproef, onafhankelijkheid en meetniveau kan je bepalen zonder statistiek. De verdeling en spreiding vraag je op dezelfde manier op als bij een \\(t\\)-toets. De uitschieters lees je uit in de boxplot. Bij schending gelden ook dezelfde regels als bij de \\(t\\)-toets.

<details open>
  <summary>Wat als voorwaarde van normaliteit geschonden is?</summary>
  Het is niet super erg, want bij een steekproefgrootte van \(> 30\) is de ANOVA robuust tegen schending van normaliteit.
</details>

#### Analyse uitvoeren

Je voert een ANOVA uit via <span class="root">ANOVA</span> <span class="sub">Classical</span> <span class="sub">ANOVA</span>. Je kiest dan bij <span class="input">Dependent Variables</span> de afhankelijke variabele en bij <span class="input">Fixed Factors</span> de onafhankelijke.

> Het is ook mogelijk om de voorwaarden te checken via de ANOVA zelf. Klik daarvoor op <span class="current">Raincloud Plots</span>. In de raincloud zie je een scatterplot, boxplot en glooiende curves. Controlleer de spreiding met de IQR, de normaliteit met de glooiende curves, en uitschieters door te kijken of er punten buiten de "staart" van de boxplot liggen.

#### Resultaten interpreteren

De ANOVA geeft een \\(F\\)-waarde en bijbehorende \\(p\\)-waarde. Deze interpreteer je aan de hand van het gekozen significantieniveau (\\(\alpha\\)).

<details>
  <summary>Hoe werkt dit?</summary>
  <p>De eerste rij toont de variantie tussen groepen, en de tweede rij toont de variantie binnen groepen. De verhouding hiertussen bepaald de \(F\)-waarde.</p>
  <p>De \(df_1\)-waarde voor de eerste rij wordt berekend door \(k - 1\), waar \(k\) het aantal groepen is, en de \(df_2\)-waarde voor de tweede rij wordt berekend door \(N - k\). Samen geeft dit te totale vrijheidsgraden \(N - 1\). Op basis hiervan wordt de \(F\)-waarde berekend:</p>
  <p>\[MS_{\text{between}} = SS_{\text{between}} / df_1\]\[MS_{\text{within}} = SS_{\text{within}} / df_2\]</p>
  \[F = MS_{\text{between}} / MS_{\text{within}}\]
</details>

Als het verschil significant is, kan je ook de effectgrootte opvragen door onder <span class="check">\\(\eta^2\\)</span> aan te vinken onder <span>Estimates of effect size</span>.

<div class="box"><h4 class="inline">Hypotheses</h4> \(H_0: \mu_1 = \mu_2 = \mu_3 ... \mu_n\) en \(H_A: \text{minstens één verschilt van de rest}\)</div>

Voor de interpretatie van effectgroottes geldt binnen de sociale wetenschappen:

| \\(\eta^2\\)   | interpretatie |
|----------------|---------------|
| \\(0.01\\)     | klein         |
| \\(0.09\\)     | matig         |
| \\(0.24\\)     | groot         |

De ANOVA laat zien aan dat *een groep* verschilt van de rest, maar vertelt niet *welke groep* (of groepen). Om dit te bepalen gebruik je een post-hoc toets of geplande contrasten.

#### Post-hoc toetsen

Bij een ongerichte hypothese gebruik je een post-hoc toets om te bepalen welke groepen van de rest verschillen. Je voert een post-hoc toets uit via <span class="current">Post Hoc Tests</span>.

<details open>
  <summary>Hoe werkt dit?</summary>
  <p>Een post-hoc toets doet wél een twee-bij-twee vergelijking van alle groepen. Om kanskapitalisatie te voorkomen wordt er daarom gebruikt gemaakt van de Bonferroni-correctie. Daardoor neemt de power van de toets wel sterk af.</p>
</details>

De post-hoc toets geeft een tabel met een \\(p_{bonf}\\)-waarde per twee-bij-twee vergelijking. Deze interpreteer je aan de hand van het gekozen significantieniveau (\\(\alpha\\)). Bij een gerichte hypothese controlleer je eerst de richting en halveer je vervolgens \\(p_{bonf}\\).

#### Geplande contrasten

Bij een gerichte hypothese gebruik je geplande contrasten. Je vergelijkt dan alleen specifieke groepen. Je hoeft daardoor niet *alle* groepen met elkaar te vergelijken, waardoor er geen kanskapitalisatie is, en dus ook geen Bonferroni-correctie nodig is. Daardoor is de power van geplande contrasten veel hoger dan bij een post-hoc toets.

Voor contrasten kies je bij <span class="current">Contrasts</span> het type contrast. Er zijn drie soorten:

- **Simple contrasts**: alle groepen worden met één groep vergeleken, meestal de controlegroep. Je krijgt dan \\(n - 1\\) vergelijkingen (waar \\(n\\) het aantal groepen is).

- **Repeated contrasts**: alle groepen worden vergeleken met de volgende groep (bijv. A vs B, B vs C, C vs D), vooral nuttig voor onafhankelijke variabelen op ordinaal meetniveau. Je krijgt ook hier \\(n - 1\\) vergelijkingen (waar \\(n\\) het aantal groepen is).

- **Custom contrasts**: je bepaalt zelf welke groepen je met elkaar vergelijkt. Je gebruikt hiervoor contrastgewichten. Om dit te doen herleidt je je hypothese op nul, want een ANOVA kan alleen controlleren of iets nul is of groter dan nul.

  <details open>
    <summary>Voorbeeld</summary>
    \[H_0: \mu_1 > \mu_2 \implies\]
    \[H_0: \mu_1 - \mu_2 > 0\]
    <p>De contrast gewichten worden dan \(1\) voor \(M_1\), \(-1\) voor \(M_2\), en \(0\) voor alle anderen.</p>
  </details>

Als deze \\(p\\)-waarde van de ANOVA lager is dan het significantieniveau (\\(\alpha\\)) kan je de <span>Contrasts</span> tabel gebruiken om te zien welke contrasten significant zijn.

<!--
Een alternatief voor geplande contrasten is de GORIC. Deze wordt niet behandeld bij TOE is is geen tentamenstof.
-->

### ANOVA voor herhaalde metingen

Een ANOVA voor herhaalde metingen gebruik je om een groep met zichzelf te vergelijken.

[uitleggen waarvoor je een ANOVA voor herhaalde metingen gebruikt]

> De manier waarop de data gestructureerd is verschilt bij dit type ANOVA:
>
> - Bij een normale ANOVA worden proefpersonen met elkaar vergeleken. Er is kolom voor de score en voor de conditie, waarbij er drie of meer mogelijke waardes voor de conditie zijn, en de respondent bij één van deze condities hoort. Bijvoorbeeld:
>
>   | ID | Schaalscore | Conditie |
>   |--|--|--|
>   | 1 | 23 | Groep A |
>   | 2 | 42 | Groep C |
>   | 3 | 12 | Groep B |
>   | 4 | 18 | Groep B |
>
> - Bij een ANOVA voor herhaalde metingen worden proefpersonen met zichzelf vergeleken. Er is per conditie een kolom die de score bevat, en elke respondent hoort dus bij alle condities. Bijvoorbeeld:
>
>   | ID | Pretest | Posttest | Followup |
>   |--|--|--|--|
>   | 1 | 23 | 35 | 27 |
>   | 2 | 42 | 53 | 44 |
>   | 3 | 12 | 22 | 21 |
>   | 4 | 18 | 19 | 18 |

<!--
Het is ook mogelijk om de ANOVA voor herhaalde metingen te gebruiken voor een combinatie van within- en between-subjects designs (aka mixed ANOVA), maar dit wordt niet behandeld bij TOE en is geen tentamenstof.
-->

#### Assumpties

Voordat je een ANOVA voor herhaalde metingen mag uitvoeren moeten eerst de voorwaarden gecheckt worden. Deze verschillen deels van die voor een standaard ANOVA.

<div class="box">
  <h4>Voorwaarden</h4>
  <ul>
    <li>Aselecte steekproef</li>
    <li>Minimaal interval/ratio</li>
    <li>Geen uitschieters</li>
    <li>Normale verdeling</li>
    <li>Sfericiteit</li>
  </ul>
</div>

De eis voor homoscedasticiteit (homogeniteit van variantie) is vervangen met sfericiteit (homogeniteit van variantie van verschilscores).

- Bij **homoscedasticiteit** mogen de scores tussen respondenten binnen een conditie niet te sterk verschillen, maar tussen condities wel.

- Bij **sfericiteit** mogen de scores tussen respondenten binnen een conditie wél sterk verschillen, zolang het verschil tussen de condities maar ongeveer gelijk is.

Je controlleert de sfericiteit met een Mauchly-test. Als de Mauchly-test significant is, is de sfericiteit geschonden (dus je wil dat deze **niet significant is**).

De ernst van de schending wordt aangegeven door de effectgrootte \\(\epsilon\\), met \\(0 < \epsilon < 1\\), waarbij \\(\epsilon = 1\\) volledige sfericiteit is. Aan de hand van \\(\epsilon\\) worden verschillende correcties toegepast:

- **Greenhouse-Geisser correctie** voor ernstige schendingen (\\(\epsilon \leq 0.75\\)).
- **Huyn-Feldt correctie** bij gematigde schendingen (\\(\epsilon \gt 0.75\\)).

Een ander soort correctie is de MANOVA, maar deze wordt niet behandeld bij TOE is is geen tentamenstof.

#### Analyse uitvoeren

Je voert een ANOVA voor herhaalde metingen uit via <span class="root">ANOVA</span> <span class="sub">Classical</span> <span class="sub">Repeated Measures ANOVA</span>. Je sleept vervolgens de variabelen voor verschillende condities naar <span class="input">Repeated Measures Cells</span>.

Je voert de Mauchly-test uit via <span class="current">Assumption Checks</span> <span class="sub">Sphericity tests</span>. Je gebruikt de hoogste waarde voor \\(\epsilon\\) die in de resultatentabel staat. Als er een correctie nodig is kan je die ook onder <span>Sphericity tests</span> aanklikken.
