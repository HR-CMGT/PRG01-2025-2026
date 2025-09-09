# Les 2: Variabelen en Functies

## Onderwerpen

- Variabelen
- Zelf gedefinieerde functies maken

<!--

- Begrijpen wat variabelen zijn en hoe je ze gebruikt
- Functies maken en aanroepen

-->

## Variabelen

Een _variabele_ gebruik je om een waarde op te slaan in je programma. Een beetje zoals je rekent met letters bij
wiskunde `x=1`, maar in een programma kan je ook langere namen gebruiken en andere dingen opslaan. Als je een nieuwe
variabele maakt, gebruik je het keyword `let`. We noemen dit het **declareren** van een variabele. Voor het eerst een
waarde in een variabele zetten noemen we **initialseren**. Zoals je hieronder kan zien declareren en initialiseren we
variabelen meestal tegelijkertijd.

Bijvoorbeeld:

```typescript
let price = 10;
let status = "playing";
```

De waarde kan je later veranderen (vandaar de naam: variabele). Omdat de variabele al bestaat, hoef je geen `let` meer
te gebruiken, en dat mag ook niet meer!

```typescript
price = 20; // price is nu: 20
status = "gameover"; // status is nu: gameover
```

### Declaratie

We declareren variabelen bij deze cursus voorlopig altijd bovenaan ons programma. Hierdoor worden de variabelen
_globaal_, waardoor je ze overal in je programma kunt gebruiken. In les 5 zullen we hier verder op in gaan.

### Naamgeving

Geef variabelen altijd een naam die aangeeft waar de variabele voor is in het Engels. Variabelen beginnen we altijd met
een kleine letter, en we gebruiken hoofdletters om aan te geven dat er meerdere woorden gebruikt zijn (er mag namelijk
geen spatie in de naam van een variabele), bijvoorbeeld: `numberOfStudents`.

### Waarde tonen met console.log

Met `console.log()` kun je de waarde van een variabele laten zien in de console. Dit is handig om te controleren of je
code werkt zoals je verwacht.

Voorbeeld:

```typescript
let age = 16;
console.log(age); // laat 16 zien in de console
```

#### Opdracht 2.1

- Maak een variabele `counter` aan en toon hem in de console.
- Tel er 1 bij op, en check of het goed gegaan is in de console.
- Pas de code aan zodat er elke seconde 1 bij opgeteld wordt.

## Datatypes

In JavaScript kun je verschillende soorten waarden opslaan in variabelen. Dit noem je _datatypes_. De belangrijkste
datatypes zijn:

- **Getallen** (numbers): bijvoorbeeld `10`, `3.14`, `-5`
- **Tekst** (strings): bijvoorbeeld `"Hallo"`, `"Superman"`
- **Boolean** (waar of niet waar): `true` of `false` (hierover in les 3 meer)

Voorbeelden:

```typescript
let age = 18; // number
let studentName = "Alex"; // string
let isFinished = false; // boolean
```

### Strings

Een string is een stukje tekst. In JavaScript zet je een string altijd tussen aanhalingstekens: enkele (' '), dubbele
(" ") of backticks (\` \`). Bijvoorbeeld:

```typescript
let studentName = "Alex";
let sentence = `Dit is een string`;
```

Je mag zelf kiezen welke je gebruikt, maar ze moeten altijd aan het begin en einde hetzelfde zijn.

### Backticks

Backticks (\` \`), zoom even in en zoek ze op op je toetsenbord, lijken op enkele aanhalingstekens, maar hebben een
extra functie: je kunt er variabelen en stukjes code direct in de tekst zetten. Dit heet een string template. Je
gebruikt dan `${ }` om een variabele of code in te voegen.

Voorbeeld:

```typescript
let name = "Alex";
let message = `Hallo, ${name}!`;
// Hallo, Alex!
let answer = `1 + 1 = ${1 + 1}`;
// 1 + 1 = 2
```

Met gewone aanhalingstekens (' ' of " ") kan dat niet, dan wordt alles letterlijk als tekst gezien.

#### Opdracht 2.2

- Maak een variabele `studentName` aan en geef deze een waarde.
- Maak een variabele `score` aan en geef deze een getal.
- Gebruik een string template om een bericht met `console.log()` te tonen: `Alex heeft 5 punten gehaald.` Gebruik
  hiervoor de variabelen.
- Verander de waarde van `score` en laat het nieuwe bericht opnieuw zien.

## Constanten

Soms wil je een waarde opslaan die niet meer mag veranderen tijdens je programma. Hiervoor gebruik je een _constante_
in plaats van een variabele. Je maakt een constante met het keyword `const` in plaats van `let`.

```typescript
const maxScore = 100;
const gameName = "Super Quiz";
const numberOfLeds = 10;
```

Een constante moet altijd meteen een waarde krijgen wanneer je hem aanmaakt. Je kunt de waarde later niet meer
veranderen:

```typescript
const pi = 3.14;
// pi = 3.14159; // Dit geeft een fout, als je dat later in het programma doet!
```

### Wanneer gebruik je constanten?

Gebruik constanten voor waarden die in je hele programma hetzelfde blijven.

Dit maakt je code duidelijker dan wanneer je de waarde zelf in je programma zet omdat je aan de naam ziet waar iets
voor is. Ook voorkomt het tikfouten, of dat je per ongeluk belangrijke waarden verandert.

#### Opdracht 2.3

Gebruik telkens de bestaande variabelen om de ontbrekende (…) variabelen te vullen. Verander `let` in `const` waar dat
logischer is.

Toon het resultaat met `console.log`, en gebruik hierbij alle variabelen en de `${}` syntax.

```typescript
let numberOfStudents = 50;
let numberOfTeachers = 10;
let numberOfChairs = ...;
// hoeveel stoelen zijn er nodig?

let rentPerMonth = 420;
let numberOfMonths = 5;
let totalRent = ...;
// hoeveel huur moet ik betalen?

let subscriptionPerMonth = 20;
let extraCostsPerMonth = 5;
let costsPerMonth = ...;
let costsPerYear = ...;
```

#### Opdracht 2.4: Cookie clicker

Maak eerst een plan en bedenk welke variabelen je nodig hebt, schrijf daarna de code:

Maak het spelletje button-clicker. Hierbij klikt iemand zo snel mogelijk op button A, en toont de computer hoe vaak je
geklikt hebt.

Expert: maak een twee speler versie met A en B.

## Functies

Een _functie_ is een stukje code dat je een naam geeft. Je kunt de functie later aanroepen door de naam te gebruiken.
Dit houd je code overzichtelijk en voorkomt dat je dezelfde code meerdere keren moet schrijven, als je programma op
verschillende plekken hetzelfde moet doen. Ook is het makkelijker om fouten in je programma te vinden, omdat alle code
voor een bepaalde _functionaliteit_ van je programma bij elkaar staat.

```typescript
function functionName() {
  // code die uitgevoerd wordt
}

// Functie aanroepen
functionName();
```

### Naamgeving

Namen van functies schrijven we net als bij variabelen altijd met een kleine letter aan het begin, en met hoofdletters
om verschillende woorden aan te geven. De functienaam moet ook duidelijk, in het Engels, beschrijven wat de functie
doet.

### Voorbeeld

```typescript
function sayHello() {
  console.log("Hello, world!");
}

// Functie aanroepen
sayHello(); // toont: Hello, world!
```

Je kunt een functie zo vaak aanroepen als je wilt:

```typescript
sayHello();
sayHello();
sayHello();
// toont drie keer: Hello, world!
```

### Functie met LED's

```typescript
function turnOnRedLed() {
  light.setPixelColor(0, Colors.Red);
}

function turnOffAllLeds() {
  light.clear();
}

// Gebruik van de functies
turnOnRedLed();
pause(1000);
turnOffAllLeds();
```

### Functie met variabelen

Functies kunnen ook je globale variabelen gebruiken:

```typescript
let counter = 0;

function incrementCounter() {
  counter = counter + 1;
  console.log(`Counter is now: ${counter}`);
}

// Test de functie
incrementCounter(); // Counter is now: 1
incrementCounter(); // Counter is now: 2
```

#### Opdracht 2.5

- Schrijf een functie `showWelcome` die een welkomstbericht toont
- Schrijf een functie `lightRedLed` die LED 0 rood maakt
- Schrijf een functie `lightBlueLed` die LED 1 blauw maakt
- Test alle functies door ze aan te roepen

#### Opdracht 2.6

```typescript
let currentLed = 0;

function nextLed() {
  light.setPixelColor(currentLed, Colors.Black);
  currentLed = currentLed + 1;
  light.setPixelColor(currentLed, Colors.Green);
}

function resetLeds() {
  light.clear();
  currentLed = 0;
}

// Gebruik van de functies
resetLeds();
nextLed(); // LED 0 wordt groen
nextLed(); // LED 1 wordt groen
```

Lees bovenstaande code. Leg in één zin uit wat dit programma doet. Bestudeer de functie `nextLed()`, begrijp je waar
elke regel voor is?

#### Opdracht 2.7

- Maak een globale variabele `ledPosition` met waarde 0
- Schrijf een functie `lightCurrentLed` die de LED op positie `ledPosition` geel maakt
- Schrijf een functie `moveToNextLed` die `ledPosition` met 1 verhoogt
- Schrijf een functie `moveToPreviousLed` die `ledPosition` met 1 verlaagt
- Zorgt dat knop A `moveToNextLed` en knop B `moveToPreviousLed` aanroept.

#### Opdracht 2.8

Bekijk deze code en probeer te begrijpen wat er gebeurt:

```typescript
let score = 0;

function addPoint() {
  score = score + 1;
  console.log(`Score: ${score}`);
}

function resetGame() {
  score = 0;
  console.log("Game reset!");
  light.clear();
}

function showScore() {
  console.log(`Current score: ${score}`);
}
```

- Wat doet de functie `addPoint`?
- Wat doet de functie `resetGame`?
- Wat doet de functie `showScore`?
- Wat gebeurt er als je `addPoint()` drie keer aanroept?

#### Opdracht 2.9

- Schrijf een functie `allLedsRed` die alle LED's rood maakt
- Schrijf een functie `allLedsOff` die alle LED's uitzet
- Schrijf een functie `firstThreeLedsBlue` die de eerste 3 LED's blauw maakt
- Test alle functies

## Bouwstenen

| Probleem                                 | Oplossing             |
| ---------------------------------------- | --------------------- |
| Iets onthouden voor later                | **Globale variabele** |
| Vaste waarden                            | **Constanten**        |
| Iets één keer doen                       | **Losse code**        |
| Iets continu blijven herhalen            | **Forever-loop**      |
| Reageren op (gebruikers)input            | **Event handler**     |
| Gebruiken van input of output            | **CPX functie**       |
| Hetzelfde doen op verschillende momenten | **Functie**           |

<!-- Opdrachten uitdunnen / aanpassen, meer op bouwstenen schrijven? -->

#### Zelfstudie 2

Bedenk van tevoren goed welke bouwstenen je nodig hebt.

1. Schrijf een programma met een teller. Als je op A klikt komt er 1 bij, klik je op B dan gaat er 1 af. Maak een
   functie die de waarde van de teller in een net bericht toont, en gebruik deze voor zowel knop A als B.
2. Schrijf een programma met een teller die elke seconde 1 groter gemaakt wordt en de huidige waarde laat zien in de
   console. Als je op A klikt begint de teller opnieuw.

3. Maak een stappenplan voor een programma dat een LED laat branden op de Circuit Playground. Met knop A kan je hem
rechtsom laten bewegen, met knop B linksom. Als je met De CP schudt gaat hij terug naar de startpositie. Schrijf daarna
de code. Tip: Je hebt `light.setpixelcolor()` nodig
<!-- TODO: voeg animatie toe -->

4. Zoek uit hoe randomRange (te vinden onder Math) werkt: https://makecode.adafruit.com/reference/math/random-range
   Gebruik randomRange om een willekeurige LED te laten branden als je op A klikt. Werkt het programma zoals je
   verwacht had?

5. Gebruik telkens de bestaande variabelen om de ontbrekende (…) variabelen te vullen. Verander `let` in `const` waar
   dat logischer is. Toon alle resultaten met `console.log` en gebruik hierbij de `${}` syntax:

```typescript
let pricePerKG = 2.15;
let weightInGrams = 150;
let totalPrice = ...; // bereken de totaalprijs (let op: gewicht is in grammen!)

let firstName = "Ash";
let lastName = "Ketchum";
let message = ...; // maak een bericht: "Hallo, Ash Ketchum!"

let hamburger = 4.20;
let fries = 1.80;
let numberOfBurgers = 3;
let numberOfFries = 5;
let totalBill = ...; // bereken de totale rekening
```
