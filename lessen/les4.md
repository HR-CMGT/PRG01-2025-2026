# Les 4: For-loops

## Onderwerpen

- Logische operatoren (&&, ||)
- Shorthand
- For-loops

<!--
- Herhaling in code toepassen

 -->

## Logische operatoren

In les 3 heb je geleerd hoe je vergelijkingen maakt en if-statements gebruikt. Soms wil je meerdere voorwaarden
combineren. Hiervoor gebruik je _logische operatoren_.

### AND operator (&&)

De `&&` operator betekent "EN". Hiermeee kan je controleren of twee dingen allebei waar zijn.

Voorbeeld:

```typescript
let age = 20;
let hasLicense = true;

if (age >= 18 && hasLicense === true) {
  console.log("Je mag autorijden!");
}
```

### OR operator (||)

De `||` operator betekent "OF". Je kunt dit in een if-statement gebruiken om te testen of één van de twee opties waar
is.

Voorbeeld:

```typescript
let isWeekend = false;
let isVacation = true;

if (isWeekend === true || isVacation === true) {
  console.log("Je hoeft niet naar school!");
}
```

#### Opdracht 4.1: Logische operatoren

1. Maak een programma dat controleert of het perfect weer is om naar buiten te gaan (temperatuur tussen 15-25 graden EN
   geen regen)
2. Maak een programma dat een groene LED aanzet als het weekend is OF het na 20:00 's avonds is.

## Shorthand

Programmeurs maken schrijven programma's het liefst zo kort mogelijk. Dit voorkomt fouten en maakt het ook makkelijker.
Omdat variabelen vaak aangepast worden op basis van de huidige waarde (maak een waarde 1 hoger, lager etc.), zijn daar
speciale _shorthand operatoren_ voor bedacht.

| Shorthand | Uitgeschreven variant | Betekenis                   |
| --------- | --------------------- | --------------------------- |
| `x += 5`  | `x = x + 5`           | Tel 5 op bij x              |
| `x -= 3`  | `x = x - 3`           | Trek 3 af van x             |
| `x *= 2`  | `x = x * 2`           | Vermenigvuldig x met 2      |
| `x /= 4`  | `x = x / 4`           | Deel x door 4               |
| `x++`     | `x = x + 1`           | Tel 1 op bij x (increment)  |
| `x--`     | `x = x - 1`           | Trek 1 af van x (decrement) |

Voorbeelden:

```typescript
let score = 10;
score += 5; // score is nu 15
score *= 2; // score is nu 30
score--; // score is nu 29

let counter = 0;
counter++; // counter is nu 1
counter += 10; // counter is nu 11
console.log(`Eindstand: ${counter}`);
```

#### Opdracht 4.2: Rekenopgaven met shorthand

Gebruik variabelen, shorthand notatie waar mogelijk en `${}` syntax om de resultaten te tonen met `console.log`:

1. Er zijn 15 mensen, verdubbel dit, haal er 6 af en deel dit door 3. Hoeveel zijn er nu?
2. Je begint met 100 euro, hier komt 5 bij, daarna wordt het drie keer zoveel en dan gaat er 1 af en als laatste wordt
   het gedeeld door 5. Hoeveel heb je nu?
3. Er zijn 17 knikkers, je wil ze met drie mensen delen. Hoeveel knikkers kan je niet verdelen?

## For-loops

Soms wil je een stukje code meerdere keren uitvoeren. In plaats van dezelfde code telkens opnieuw te schrijven (daar
houden programmeurs niet van) kan je een _for-loop_ gebruiken. Een for-loop herhaalt code een bepaald aantal keren.

De basis structuur van een for-loop is:

```typescript
for (let i = 0; i < numberOfRepeats; i++) {
  // code die wordt herhaald
}
```

- `let i = 0`: Start met variabele `i` op waarde 0
- `i < aantal`: Herhaal zolang `i` kleiner is dan het numberOfRepeats
- `i++`: Tel 1 bij `i` op na elke herhaling

### Voorbeeld

```typescript
for (let i = 0; i < 5; i++) {
  console.log("Herhaling nummer: " + i);
}
```

Dit toont:

```
Herhaling nummer: 0
Herhaling nummer: 1
Herhaling nummer: 2
Herhaling nummer: 3
Herhaling nummer: 4
```

#### Opdracht 4.3

```typescript
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

Wat toont deze code in de console?

#### Opdracht 4.4

- Maak een for-loop die "Hallo!" 3 keer toont in de console
- Maak een for-loop die van 0 tot 7 telt en elk getal toont in de console
- Maak een for-loop die van 1 tot 5 telt en elk getal toont in de console

## For-loops met LED's

Op de Circuit Playground Express kun een for-loop gebruiken om de LED's aan te zetten.

### Alle LED's aanzetten

```typescript
for (let i = 0; i < 10; i++) {
  light.setPixelColor(i, Colors.Red);
}
```

<!-- TODO: dit voorbeeld er misschien niet bij zetten? -->

### LED's één voor één laten oplichten

```typescript
for (let i = 0; i < 10; i++) {
  light.setPixelColor(i, Colors.Blue);
  pause(200); // Wacht 200 milliseconden
}
```

#### Opdracht 4.5

- Maak een for-loop die alle LED's groen maakt
- Maak een for-loop die de LED's één voor één rood laat oplichten met een pauze van 300 milliseconden
- Maak een for-loop die de eerste 5 LED's blauw maakt

#### Opdracht 4.6

Voor elk van de volgende problemen, schrijf eerst op welke techniek je zou gebruiken (variabele, if-statement,
for-loop, etc.) en waarom:

1. "Tel hoeveel keer de A knop is ingedrukt"
2. "Laat alle LED's 3 keer achter elkaar knipperen"
3. "Als het licht is, zet dan een groene LED aan, anders een rode"
4. "Maak een patroon met alle LED's"
5. "Laat een LED knipperen zolang het programma draait"
6. "Speel een geluid af wanneer de temperatuur boven 30 graden komt"
7. "Zet alle LED's uit wanneer er op knop B wordt gedrukt"
8. "Tel af van 10 naar 0 en speel bij 0 een geluid af"

Kies er 3 uit, maak het plan af en implementeer deze.

## Geavanceerde for-loop voorbeelden

### For-loop met if-statement combineren

```typescript
for (let i = 0; i < 10; i++) {
  if (i < 5) {
    light.setPixelColor(i, Colors.Red);
  } else {
    light.setPixelColor(i, Colors.Blue);
  }
}
```

### Variabele gebruiken in for-loop

```typescript
let counter = 5;

for (let i = 0; i < 5; i++) {
  counter = counter + 1;
  console.log("Counter is nu: " + counter);
}
```

#### Opdracht 4.7

Wat doen bovenstaande for-loop voorbeelden?

#### Opdracht 4.8

- Maak een variabele `ledCount` met waarde 8
- Gebruik een for-loop die van 0 tot `ledCount` loopt

#### Opdracht 4.9

- Zet de eerste helft van de LED's op groen, de tweede helft op rood
- Gebruik een if-statement om te bepalen welke kleur elke LED krijgt

#### Opdracht 4.10: Knipperend patroon

Maak een programma dat:

1. Alle LED's aanzet
2. Wacht 500 milliseconden
3. Alle LED's uitzet
4. Wacht 500 milliseconden
5. Dit 5 keer herhaalt

## Bouwstenen

| Probleem                                      | Oplossing             |
| --------------------------------------------- | --------------------- |
| Iets onthouden voor later                     | **Globale variabele** |
| Vaste waarden                                 | **Constanten**        |
| Rekenen of dingen veranderen                  | **Operatoren**        |
| Keuzes maken                                  | **If-statement**      |
| Iets één keer doen                            | **Losse code**        |
| Iets meerdere keren (ongeveer) hetzelfde doen | **For-loop**          |
| Iets continu blijven herhalen                 | **Forever-loop**      |
| Reageren op (gebruikers)input                 | **Event handler**     |
| Gebruiken van input of output                 | **CPX functie**       |
| Hetzelfde doen op verschillende momenten      | **Functie**           |

#### Zelfstudie 4

Gebruik for loops om onderstaande teksten te tonen (ze staan hier naast elkaar, maar op de CPX komen ze natuurlijk
onder elkaar)

1. 8x "Hoi": `"Hoi"` `"Hoi"` `"Hoi"` `"Hoi"` `"Hoi"` `"Hoi"` `"Hoi"` `"Hoi"`

2. Getallen 0 t/m 4 tonen: `0` `1` `2` `3` `4`

3. Even getallen van 0 t/m 12: `0` `2` `4` `6` `8` `10` `12`

4. Tafel van 4: `1 maal 4 is 4` `2 maal 4 is 8` `3 maal 4 is 12` `4 maal 4 is 16` `5 maal 4 is 20` `6 maal 4 is 24`

Bedenk van tevoren goed welke bouwstenen je nodig hebt:

5. Schrijf een countdown-timer die van 10 naar 0 telt en bij 0 een geluid afspeelt
6. Maak een programma dat een LED-ring laat "ademhalen" door alle LED's langzaam aan en uit te laten gaan

7. **Stappenteller met LED-display** - Maak een digitale stappenteller:
   - Maak een globale variabele om het aantal stappen dat iemand zet bij te houden
   - Bij elke stap (`onGesture`) tel je daar 1 bij op, en toon je het aantal stappen in de console
   - **Knop A**: Toon tientallen stappen als blauwe LED's (64 stappen = 6 blauwe LED's)
   - **Knop B**: Toon resterende stappen als groene LED's (64 stappen = 4 groene LED's na 6 tientallen)
   - **Doel bereikt**: Voeg een constante toe met het stappendoel. Speel een melodie en toon een LED-animatie als het
     doel bereikt wordt
