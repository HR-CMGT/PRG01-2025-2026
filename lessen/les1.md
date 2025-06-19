# Les 1: Introductie

## Onderwerpen

- Programmastructuur
- Input/output
- Pseudocode
- on start, forever, en event-handlers
- Kleurdefinities

<!-- Waarschijnlijk beter om on start niet te benoemen -->

<!--

- Kennismaken met de programmeeromgeving
- Eerste eenvoudige programma's schrijven
- Wat is programmeren? (logica + code)

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

#### Opdracht

- Schrijf pseudocode voor inchecken bij de metro:
  - Eerst voor een persoon die incheckt
  - Daarna het algoritme voor het poortje zelf

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

<!-- Ook comments al uitleggen? -->

```typescript
// Zet de LED's op rood
light.setAll(Colors.Red);
```

<!-- In les light.setPixelColor en kleuren uitleggen -->

_Met `//` geef je aan dat de computer alles wat daarna komt op die regel over moet slaan. Je gebruikt dit om uitleg
(bij programmeren noemen we dit 'commentaar') toe te voegen aan je programma._

#### Opdracht

Schrijf eerst pseudocode, en daarna de echte code:

- Laat de bovenste twee LED's branden
- Maak een patroon met LED'jes

### De code moet steeds herhaald worden

Als je wilt dat code steeds opnieuw wordt uitgevoerd (bijvoorbeeld om iets te blijven controleren of een animatie te
maken), zet je deze in `forever`.

#### Opdracht

Schrijf eerst pseudocode, en daarna de echte code:

- Laat alle LED's op de ring knipperen (zwart is uit)
- Laat een rood LED'je oneindig rondjes draaien

**Voorbeeld:**

```typescript
forever(function () {
  // Speel oneidig keer een vervelend toontje
  music.baDing.play();
  pause(1000);
});
```

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

#### Opdracht

Schrijf eerst pseudocode, en daarna de echte code:

- Als je op A klikt wordt er een animatie getoond, als je op B klikt klinkt er een muziekje.
- Als je op A klikt gaan de LED's aan de linkerkant op groen, als je op B klikt de rechterkant. Let op, het moet niet
  kunnen dat alle LED's tegelijkertijd groen zijn.

#### Zelfstudie

Schrijf bij programmeeropdrachten steeds eerst pseudocode, en daarna de echte code:

- Laat de LEDs 1x knipperen
- Zet alle LEDs aan als je op A klikt, zet ze weer uit als je de CPX schudt
- Schrijf pseudocode om een vakje te kiezen met boter-kaas-eieren, wissel de pseudocode met een klasgenoot, en speel
  tegen elkaar om te zien wie de slimste pseudocode heeft
- De halve ring knippert, de andere helft zet je aan en uit met knop A en B
- Reactiespel?
<!-- TODO: Ga ik hier misschien weer te hard voor les 1? -->

## Links

- [Circuit Playground Express overzicht](https://learn.adafruit.com/adafruit-circuit-playground-express/overview)
- [Adafruit Makecode](https://makecode.adafruit.com/)
