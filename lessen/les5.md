# Les 5: Functies met Parameters

## Onderwerpen

- Functies met parameters
- Lokale variabelen en scope
- Probleemoplossend denken (mini-case)

<!--

- Functies schrijven die input ontvangen
- Een probleem analyseren en oplossen met code

-->

<!-- TODO: naamgeving -->

## Functies met parameters

In les 2 hebben we functies gemaakt om code te groeperen. Dit waren functies waarbij niets tussen de haakjes stond,
zoals `allLedsRed()`. Op de CPX hebben we dit soort functies ook gezien, zoals `light.clear()`. Soms wil je een functie
informatie meegeven. Dit doe je met _parameters_ die je tussen de haakjes zet. De functie kan deze waarde dan
gebruiken. Op de CPX hebben we dit bijvoorbeeld gezien met `loops.pause(2000)` waarbij je tussen haakjes zet hoeveel
milliseconden je wil pauzeren. In onze eigen functies kunnen we dit

### Eenvoudig voorbeeld

```typescript
function sayHello(name: string) {
  console.log(`Hello, ${name}!`);
}

// Functie aanroepen met verschillende waarden
sayHello("Alex"); // Hello, Alex!
sayHello("Sarah"); // Hello, Sarah!
```

De waarde die je meegeeft (`"Alex"` of `"Sarah"`) noem je een _argument_. Dit wordt toegewezen aan de parameter `name`.

### Functie met meerdere parameters

```typescript
let studentName = "Tom";
let studentAge = 16;

function showMessage(name: string, age: number) {
  console.log(`${name} is ${age} years old`);
}

showMessage(studentName, studentAge); // Tom is 16 years old
showMessage("Lisa", 17); // Lisa is 17 years old
```

### Datatypes

Je ziet dat we bij elke parameter het _datatype_ aangeven:

- `string` voor tekst
- `number` voor getallen
- `boolean` voor true/false

In gewoon JavaScript doe je dit niet. Wij moeten dit wel doen, omdat de CPX eigenlijk met TypeScript werkt.

<!-- TODO: JS voorbeeld toevoegen? -->

## Lokale variabelen en scope (advanced)

Tot nu toe hebben we altijd globale variabelen gebruikt - variabelen die bovenaan de code staan en overal gebruikt
kunnen worden. Binnen functies kun je ook _lokale variabelen_ maken. Deze bestaan dan alleen binnen die functie, en
kunnen nergens anders gebruikt worden.

### Lokale variabelen

```typescript
let globalScore = 100; // Deze variabele bestaat overal

function calculateBonus(basePoints: number) {
  let bonus = basePoints * 2; // Deze variabele bestaat alleen in deze functie
  let message = `Je krijgt ${bonus} bonuspunten!`; // Ook lokaal

  console.log(message);
  return bonus;
}

calculateBonus(50); // Je krijgt 100 bonuspunten!
// console.log(bonus); // Dit zou een fout geven! bonus bestaat hier niet
```

### Scope (bereik)

_Scope_ betekent: waar kan een variabele gebruikt worden?

- **Globale scope**: Variabelen bovenaan je code kunnen overal gebruikt worden
- **Functie scope**: Variabelen binnen een functie kunnen alleen binnen die functie gebruikt worden

### Wanneer gebruik je lokale variabelen?

Gebruik lokale variabelen voor:

- Tijdelijke berekeningen binnen een functie
- Waarden die alleen binnen die functie nodig zijn
- Om te voorkomen dat je per ongeluk globale variabelen overschrijft

#### Opdracht 5.1

- Maak een variabele `playerName` met jouw naam
- Maak een variabele `playerScore` met waarde 85
- Schrijf een functie `showScore` die een naam (string) en score (number) als parameters heeft
- De functie toont: `"Alex heeft 85 punten"`
- Test de functie met je globale variabelen en met andere waarden

### LED op bepaalde positie aanzetten

```typescript
function turnOnLed(position: number, color: number) {
  light.setPixelColor(position, color);
}

// Gebruik van de functie
turnOnLed(0, Colors.Red); // LED 0 wordt rood
turnOnLed(5, Colors.Blue); // LED 5 wordt blauw
turnOnLed(9, Colors.Green); // LED 9 wordt groen
```

### LED laten knipperen

```typescript
function blinkLed(position: number, color: number) {
  light.setPixelColor(position, color);
  pause(200);
  light.setPixelColor(position, Colors.Black);
  pause(200);
}

// LED 3 laten knipperen in rood
blinkLed(3, Colors.Red);
```

#### Opdracht 5.2

- Schrijf een functie `setLedColor` die een positie en kleur als parameters heeft
- Test de functie door verschillende LED's verschillende kleuren te geven
- Schrijf een functie `blinkTwice` die een LED twee keer laat knipperen
- Test beide functies met verschillende posities en kleuren

## Functies met for-loops combineren

Je kunt parameters gebruiken in for-loops om flexibele functies te maken.

### Meerdere LED's aansturen

```typescript
function lightUpRange(startPos: number, endPos: number, color: number) {
  for (let i = startPos; i <= endPos; i++) {
    light.setPixelColor(i, color);
  }
}

// LED's 2 tot 5 worden geel
lightUpRange(2, 5, Colors.Yellow);
```

### LED patroon met snelheid

```typescript
let patternColor = Colors.Blue;
let patternSpeed = 100;

function showPattern(color: number, speed: number) {
  for (let i = 0; i < 10; i++) {
    light.setPixelColor(i, color);
    pause(speed);
  }
}

// Gebruik met globale variabelen
showPattern(patternColor, patternSpeed);
// Of met directe waarden
showPattern(Colors.Red, 500);
```

#### Opdracht 5.3

- Maak globale variabelen `startNumber` (waarde 5) en `ledColor` (waarde Colors.Green)
- Schrijf een functie `countdown` die een startgetal als parameter heeft
- De functie telt af van dat getal naar 0 en toont elk getal met console.log
- Schrijf een functie `lightShow` die een kleur en aantal herhalingen als parameters heeft
- De functie laat alle LED's het opgegeven aantal keer oplichten in die kleur
- Test beide functies met je globale variabelen

#### Opdracht 5.4

```typescript
let alarmActive = false;

function setAlarm(isActive: boolean) {
  alarmActive = isActive;
  if (alarmActive === true) {
    light.setAll(Colors.Red);
    music.playTone(800, 500);
  } else {
    light.clear();
  }
}
```

- Wat doet de variabele `alarmActive`?
- Wat gebeurt er als je `setAlarm(true)` aanroept?
- Wat gebeurt er als je `setAlarm(false)` aanroept?
- Waarom gebruikt de functie `===` in plaats van `=`?

#### Opdracht 5.5

```typescript
let currentLed = 0;

function moveLed(direction: number) {
  light.setPixelColor(currentLed, Colors.Black);
  currentLed = currentLed + direction;
  if (currentLed >= 10) {
    currentLed = 0;
  }
  if (currentLed < 0) {
    currentLed = 9;
  }
  light.setPixelColor(currentLed, Colors.Green);
}
```

- Wat doet deze code als je `moveLed(1)` aanroept?
- Wat doet deze code als je `moveLed(-1)` aanroept?
- Waarom zijn er twee if-statements?
- Wat is het doel van de globale variabele `currentLed`?

## Probleemoplossend denken

Als problemen groter worden, wordt het steeds lastiger om meteen met code te beginnen. Vandaar dat we vaak vooraf een
plan gemaakt hebben voor we gingen implementeren. Een truc om grote problemen kleiner te maken is door ze 'in stukken
te hakken', deze deelproblemen kan je dan vaak in een aparte functie plaatsen en oplossen, vandaar dat we een extra
stap toevoegen aan het plan.

### Stappenplan

1. **Probleem analyseren**: Wat moet er precies gebeuren?
2. **Bouwstenen herkennen**: Welke programmeertechnieken heb je nodig?
3. **Pseudocode schrijven (optioneel)**: Plan complexere oplossingen eerst (deels) in gewone taal
4. **Functies identificeren**: Welke deelproblemen kan je in een functie zetten?
5. **Implementeren**: Vertaal je plan naar echte code
6. **Testen**: Controleer of alles werkt zoals verwacht `if !ok { goto 1, 2, 3, 4, 5 }`

### Bouwstenen

| Probleem                                      | Oplossing                  |
| --------------------------------------------- | -------------------------- |
| Iets onthouden voor later                     | **Globale variabele**      |
| Vaste waarden                                 | **Constanten**             |
| Rekenen of dingen veranderen                  | **Operatoren**             |
| Keuzes maken                                  | **If-statement**           |
| Iets één keer doen                            | **Losse code**             |
| Iets meerdere keren (ongeveer) hetzelfde doen | **For-loop**               |
| Iets continu blijven herhalen                 | **Forever-loop**           |
| Reageren op (gebruikers)input                 | **Event handler**          |
| Gebruiken van input of output                 | **CPX functie**            |
| Hetzelfde doen op verschillende momenten      | **Functie**                |
| Hetzelfde doen met verschillende waarden      | **Functie met parameters** |

### Voorbeeld: Verkeerslicht simulator

**Probleem**: Maak een verkeerslicht dat rood, oranje en groen toont.

**Stap 1 - Analyseren**:

- 3 LED's gebruiken (bijvoorbeeld positie 0, 1, 2)
- Rood → Oranje → Groen → herhalen
- Elke kleur moet even blijven staan

**Stap 2 - Bouwstenen herkennen**:

- Waarden onthouden voor LED posities → **variabelen**
- Continu herhalen → **Forever loop**
- Dezelfde actie (LED aanzetten) met verschillende waarden → **Functie met parameters**
- LED aansturen → **CPX functie**

**Stap 3 - Pseudocode**:

```
variabelen:
    - redPosition = 0
    - orangePosition = 1
    - greenPosition = 2

functie showTrafficLight:
    - parameter: kleur, positie, tijd
    - alle LED's uit
    - zet LED op positie aan in kleur
    - wacht opgegeven tijd

hoofdprogramma:
    - herhaal voor altijd:
        - showTrafficLight rood, redPosition, 2 seconden
        - showTrafficLight oranje, orangePosition, 1 seconde
        - showTrafficLight groen, greenPosition, 2 seconden
```

**Stap 4 - Functies identificeren**:

- `showTrafficLight(color, position, duration)` - voor elke kleur

**Stap 5 - Implementeren**:

```typescript
let redPosition = 0;
let orangePosition = 1;
let greenPosition = 2;

function showTrafficLight(color: number, position: number, duration: number) {
  light.clear();
  light.setPixelColor(position, color);
  pause(duration);
}

forever(function () {
  showTrafficLight(Colors.Red, redPosition, 2000);
  showTrafficLight(Colors.Orange, orangePosition, 1000);
  showTrafficLight(Colors.Green, greenPosition, 2000);
});
```

**Stap 6 - Testen**:

- Controle of de juiste LED's aangaan
- Controle of de timing klopt
- Testen of het blijft herhalen

#### Opdracht 5.6

1. "Maak een digitale dobbelsteen die een willekeurig getal van 1-6 toont als LED's wanneer je schudt"

   - Welke bouwstenen herken je?
   - Schrijf pseudocode

2. "Tel hoeveel keer knop A is ingedrukt en toon dit met LED's"

   - Welke bouwstenen herken je?
   - Schrijf pseudocode

3. "Laat een LED rondjes maken, sneller als de temperatuur hoger is"
   - Welke bouwstenen herken je?
   - Schrijf pseudocode

## Mini-case: Alarmsysteem

**Probleem**: Maak een alarmsysteem, dat reageert op beweging. Wanneer je op knop A drukt, gaat het alarm aan (rode
knipperende LED's + geluid). Wanneer je op knop B drukt, gaat het alarm uit.

### Stap 1: Analyseer het probleem

- Wat moet er gebeuren bij knop A?
- Wat moet er gebeuren bij knop B?
- Welke input en output heb je?
- Wanneer gaat het alarm af?

### Stap 2: Patronen herkennen

- Welke programmeertechnieken heb je nodig volgens de patronentabel?
- Moet je iets onthouden over de status van het alarm?
- Hoe reageer je op de knoppen?

### Stap 3: Schrijf pseudocode

```
variabelen:
    - ...

functie ...:
    - parameters nodig?

event handlers:
    - ...
```

### Stap 4: Functies identificeren

- Welke functies ga je maken?
- Welke parameters hebben ze nodig?

### Stap 5: Implementeer je oplossing

Gebruik functies met parameters waar mogelijk.

### Stap 6: Test je oplossing

- Test of knop A het alarm aanzet
- Test of knop B het alarm uitzet
- Test of het alarm blijft werken na meerdere keren aan/uit

#### Opdracht 5.7: Basis functies met parameters

- Maak globale variabelen: `firstName` (jouw voornaam), `className` (jouw klas), `number1` (waarde 12), `number2`
  (waarde 8)
- Schrijf een functie `greetStudent` die een naam en klas als parameters heeft
- De functie toont: `"Hallo Alex uit klas 1A"`
- Schrijf een functie `calculateSum` die twee getallen als parameters heeft
- Deze functie toont de som van beide getallen met een template string
- Test beide functies met je globale variabelen

#### Opdracht 5.8: LED patronen

- Maak globale variabelen: `favoriteColor` (een kleur), `blinkCount` (waarde 3)
- Schrijf een functie `fillLeds` die een kleur als parameter heeft
- De functie zet alle LED's op die kleur
- Schrijf een functie `blinkPattern` die een kleur en aantal keren als parameters heeft
- Deze functie laat alle LED's het opgegeven aantal keer knipperen
- Test met je globale variabelen en andere waarden

#### Opdracht 5.9: Geluid en licht

- Maak globale variabelen voor verschillende toonhoogtes
- Schrijf een functie `ledAndSound` die een LED-positie, kleur en toonhoogte als parameters heeft
- De functie zet de LED aan en speelt tegelijk een toon af
- Schrijf een functie `playSequence` die 3 verschillende LED's na elkaar laat oplichten
- Elke LED heeft een andere kleur en speelt een andere toon
- Test je functies met verschillende combinaties

#### Opdracht 5.10: Code lezen

Bekijk deze code en beantwoord de vragen:

```typescript
let gameScore = 0;
let bonusPoints = 10;

function addScore(points: number) {
  gameScore = gameScore + points;
  console.log(`Score is now: ${gameScore}`);
}

function checkBonus() {
  if (gameScore >= 50) {
    addScore(bonusPoints);
    console.log("Bonus earned!");
  }
}
```

Vragen:

- Wat doet de functie `addScore`?
- Wanneer krijg je bonus punten?
- Wat gebeurt er als je `checkBonus()` aanroept terwijl `gameScore` 45 is?
- Wat gebeurt er als je `checkBonus()` aanroept terwijl `gameScore` 60 is?

#### Opdracht 5.11: Mini-case uitwerken

Kies één van deze problemen en werk het volledig uit volgens het stappenplan:

1. **Muziekinstrument**: Maak een soort theramin, waarmee je de toonhoogte kunt veranderen door de CPX schuin te houden
2. **Temperatuurmeter**: Toon met LED-kleuren hoe warm het is (blauw=koud, groen=normaal, rood=warm)
3. **LED-dimmer**: Laat alle LEDs op de CPX branden, door te schudden wordt de helderheid gewisseld tussen
   verschillende standen (vol, half, uit)

#### Zelfstudie 5

Bedenk van tevoren goed welke bouwstenen je nodig hebt en gebruik functies met parameters waar mogelijk:

- Verzin je eigen game op de Circuit Playground Express, waarin de speler een actie moet doen en daarmee punten kunt
  halen. Post het resultaat in het Teams kanaal, gebruik daarvoor de SHARE button in de makecode omgeving!
- Bereid je voor op de oefentoets
