---
title: Toepassing van onderzoeksmethoden en statistiek
---

> Deze is nog niet af. Ik verwacht 21 juni klaar te zijn.

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

## Data-analyse

### Correlatie

Een correlatie gebruik je om het verband tussen twee variabelen te bepalen. Je doet dit aan de hand van een visuele check en een Pearson- of Spearman-correlatiecoëfficient.

Voordat je een correlatiecoëfficient gaat berekenen is het eerst belangrijk om te kijken of er überhaupt een verband is tussen twee variabelen, en welke richting dit verband heeft.

Dit doe je door: <span class="root">Descriptives</span> <span class="sub">Descriptive Statistics</span>, en kies twee variabelen. Plot daarna een spreidingsdiagram via <span class="current">Customizable plots</span> <span class="sub">Scatter plots</span>.

<div class="box">
  <h4>Instellingen</h4>
  <ul>
    <li><span class="opt">Graph right</span>: <kbd>None</kbd></li>
    <li><span class="opt">Graph above</span>: <kbd>None</kbd></li>
    <li><span class="opt">Regression line</span>: <kbd>None</kbd></li>
  </ul>
</div>

Als er sprake is van een linear verband mogen we een Pearson-correlatie bepalen, anders alleen een Spearman-correlatie. Beide doen we via <span class="root">Regression</span> <span class="sub">Classical</span> <span class="sub">Correlation</span>. Je kiest dan onder <span>Sample Correlation Coefficient</span> (linkerkolom) voor <span class="check">Pearson's r</span> of <span class="check">Spearmans's rho</span>.

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

Als \\(rit < .20\\) en \\(\alpha\\) stijgt bij verwijderen, moet een item verwijderd worden. Je haalt het item dan uit de betrouwbaarheidsanalyse, en neemt het niet meer mee in het berekenen schaalscores.

> Alle data in de tabel staat met elkaar in samenhang. Het is daarom uitermate belangrijk dat maar <strong>één item per keer wordt verwijderd!</strong>
