# Les 1: Introductie

## Onderwerpen

- Programmastructuur
- Input/output
- Pseudocode
- on start, forever, en event-handlers
- Kleurdefinities

<!-- Waarschijnlijk beter om on start niet te benoemen, maar dan wel bedenken hoe dat in pseudocode te doen -->

<!--

- Kennismaken met de programmeeromgeving
- Eerste eenvoudige programma's schrijven
- Wat is programmeren? (logica + code)
-->

<!--

 TODO: hier al beginnen met planmatig werken voor opdrachten (analyse + bouwstenen).
 pseudocode alleen bij ingewikkelde dingen

-->

## Wat is programmeren

Programmeren is het stap voor stap bedenken en opschrijven van instructies die een computer kan uitvoeren.

- Je maakt een plan of schrijft pseudocode (de oplossing in gewone taal, logica).
- Daarna zet je dit plan om in code die de computer begrijpt (code).
- Je test en verbetert je programma totdat het werkt zoals je wilt (debuggen).

## Pseudocode

Pseudocode is een manier om je oplossing eerst in gewone taal op te schrijven, voordat je begint met programmeren. Je
beschrijft stap voor stap wat er moet gebeuren, zonder je druk te maken over de precieze code of syntax. Dit helpt je
om logisch na te denken over het probleem zonder dat (gebrek aan) kennis van de syntax je in de weg zit.

_Voorbeeld pseudocode voor een verkeerslicht:_

- Herhaal:
  - Zet het licht op rood
  - Wacht 10 seconden
  - Zet het licht op groen
  - Wacht 10 seconden
  - Zet het licht op oranje
  - Wacht 2 seconden

_Voorbeeld pseudocode voor een auto bij het verkeerslicht:_

- Rij richting het verkeerslicht
- Als het licht op rood staat:
  - Stop voor het stoplicht
- Als het licht op groen staat:
  - Rij door
- Als het licht op oranje staat:
  - Stop als je nog kunt, anders rij voorzichtig door

<!-- TODO: door de klas lopen toevoegen, metro er misschien uit of naar zelfstudie -->

#### Opdracht

- Schrijf pseudocode voor inchecken bij de metro:
  - Eerst voor een persoon die incheckt
  - Daarna het algoritme voor het poortje zelf

#### Opdracht

- Schrijf pseudocode om een vakje te kiezen met boter-kaas-eieren, wissel de pseudocode met een klasgenoot, en speel
  tegen elkaar om te zien wie de slimste pseudocode heeft

## Circuit Playground Express

De Circuit Playground Express (CPX) is een kleine programmeerbare computer (microcontroller) met ingebouwde sensoren
(o.a. knoppen, bewegingssensor en lichtsensor) en actuatoren (o.a. neopixel LED's en speaker).

## Adafruit MakeCode

Adafruit MakeCode is een online programmeeromgeving waarmee je programma’s kunt maken voor de Circuit Playground
Express. Je kunt kiezen tussen blokken (voor beginners) of tekst (JavaScript/TypeScript) om je code te schrijven. In
deze cursus gebruiken we de tekstmodus, zodat je leert programmeren met echte code.

https://makecode.adafruit.com/

## Waar zet je je code?

### De code moet 1x worden uitgevoerd

Soms wil je dat bepaalde code maar één keer wordt uitgevoerd, bijvoorbeeld om iets klaar te zetten of een beginwaarde
te geven. Dit de standaard voor code die je in een JavaScript programma zet, dus daar hoef je niks bijzonders voor te
doen.

**Voorbeeld:**

```typescript
// Zet de LED's op rood
light.setAll(Colors.Red);
```

<!-- In les light.setPixelColor en kleuren uitleggen -->

_Met `//` geef je aan dat de computer alles wat daarna komt op die regel over moet slaan. Je gebruikt dit om uitleg
(bij programmeren noemen we dit 'commentaar') toe te voegen aan je programma._

#### Opdracht

Zoek eerst uit welke functies van de CPX je nodig hebt, en schrijf daarna pas de code:

- Laat de bovenste twee LED's branden
- Maak een patroon met LED'jes

### De code moet steeds herhaald worden

Als je wilt dat code steeds opnieuw wordt uitgevoerd (bijvoorbeeld om iets te blijven controleren of een animatie te
maken), zet je deze in `forever`.

**Voorbeeld:**

```typescript
loops.forever(function () {
  // Speel oneidig keer een vervelend toontje
  music.baDing.play();
  pause(1000);
});
```

### Accolades

Accolades { } zijn speciale tekens die we gebruiken om codeblokken aan te geven. Je geeft hiermee aan dat deze code bij
elkaar hoort. Dit wordt erg veel gebruikt in programma's. Bij forever wordt alle code die tussen de accolades staat
oneindig herhaald.

#### Opdracht

Denk eerst goed na over wat er moet gebeuren, schrijf daarna pas de code:

- Laat alle LED's op de ring knipperen (zwart is uit)
- Laat een rood LED'je oneindig rondjes draaien

### De code moet uitgevoerd worden als er iets gebeurt (event)

Soms wil je dat code alleen wordt uitgevoerd als er iets gebeurt, bijvoorbeeld als je op een knop drukt. Hiervoor
gebruik je een **event-handler**. De syntax hiervan is best lastig, dus het is het makkelijkst om deze code te
'slepen'.

**Voorbeeld:**

```typescript
input.buttonA.onEvent(ButtonEvent.Click, function () {
  // Laat een animatie zien als je op A klikt
  light.showAnimation(light.rainbowAnimation, 500);
});
```

_Je ziet dat ook hier weer accolades gebruikt zijn om aan te geven wat er allemaal uitgevoerd moet worden als op A
geklikt wordt._

#### Opdracht

Denk eerst goed na over wat er moet gebeuren, zoek de juiste functies voor de CPX op, en schrijf daarna de code:

- Als je op A klikt wordt er een animatie getoond, als je op B klikt klinkt er een muziekje.
- Als je op A klikt gaan de LED's aan de linkerkant op groen, als je op B klikt de rechterkant. Let op, het moet niet
  kunnen dat alle LED's tegelijkertijd groen zijn.

## Kleuren

De Neopixels op de CPX werken met RGB-kleuren. Door rood, groen en blauw te 'mengen' kan je namelijk alle kleuren
maken. Er zijn verschillende manieren om aan te geven wat voor kleur je wilt.

```typescript
// Maak pixels 0, 1, 2, 3 rood

// Makkelijkst leesbaar en te onthouden
light.setPixelColor(0, Colors.Red);
// Zelfde als hiervoor, maar meer tikwerk
light.setPixelColor(1, light.colors(Colors.Red));
// Als je geen standaardkleur wilt gebruiken
light.setPixelColor(2, light.rgb(255, 0, 0));
// Als je handig bent met 'webcodes'
light.setPixelColor(3, 0xff0000);
```

## Planmatig werken

> Who's the (wo)man with the master plan

Omdat programmeren uit meer bestaat dan code schrijven, is het goed om voor je aan de code begint eerst een plan te
maken.

**Stap 1 - Analyseer het probleem**:

Lees de opdracht goed. Wat moet er precies gebeuren?

**Stap 2 - Bouwstenen herkennen**:

Alle programma's zijn opgebouwd met dezelfde 'bouwstenen'. Bedenk welke je nodig hebt, en zoek eventueel functies van
de CPX op die je nog niet kent.

De bouwstenen die we tot nu toe gehad hebben zijn:

| Probleem                                 | Oplossing                  |
| ---------------------------------------- | -------------------------- |
| Iets één keer doen                       | **Losse code**             |
| Iets continu blijven herhalen            | **Forever-loop**           |
| Reageren op (gebruikers)input            | **Event handler**          |
| Gebruiken van input of output            | **CPX functie**            |
| Hetzelfde doen op verschillende momenten | **Functie**                |
| Hetzelfde doen met verschillende waarden | **Functie met parameters** |

**Stap 3 - Pseudocode schrijven (optioneel)**

Voor kleine programma's vaak niet nodig, maar zelfs dan kan het helpen om wat stappen even uit te schrijven.

**Stap 4 - Implementeren**

Schrijf de code.

**Stap 5 - Testen**

Test je code.

Werkt het?

- ✅ 🎉
- ❌ 😭 ⬆️ (ga terug naar stap 1, 2, 3 of 4)

#### Zelfstudie

Ga bij de programmeeropdrachten steeds planmatig te werk:

- Laat de LEDs 1x knipperen
- Zet alle LEDs aan als je op A klikt, zet ze weer uit als je de CPX schudt
- De halve ring knippert, de andere helft zet je aan en uit met knop A en B

## Links

- [Circuit Playground Express overzicht](https://learn.adafruit.com/adafruit-circuit-playground-express/overview)
- [Adafruit Makecode](https://makecode.adafruit.com/)
