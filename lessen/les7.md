# Les 7: Arrays

## Onderwerpen

- Arrays
- Arrays en for-loops

<!--

- Werken met lijsten van waarden
- Herhalen over een array met een for-loop
-->

## Arrays

Een _array_ is een speciaal datatype waarin je meerdere waarden kunt opslaan. In plaats van losse variabelen voor elke
waarde, kun je alles in één lijst zetten. Arrays zijn handig als je met veel vergelijkbare data werkt.

### Array maken

```typescript
let numbers = [1, 2, 3, 4, 5];
let colors = [Colors.Red, Colors.Blue, Colors.Green];
let names = ["Alex", "Sarah", "Tom"];
```

### Waarden uit array halen

Je kunt waarden uit een array halen met de _index_ (positie). Let op: arrays beginnen bij 0!

```typescript
let fruits = ["apple", "banana", "orange"];
console.log(fruits[0]); // apple
console.log(fruits[1]); // banana
console.log(fruits[2]); // orange
```

### Waarden toevoegen

```typescript
let scores = [10, 20, 30];
scores.push(40); // voegt 40 toe aan het einde
console.log(scores); // [10, 20, 30, 40]
```

### Array lengte

```typescript
let myArray = [1, 2, 3];
console.log(myArray.length); // 3
```

#### Opdracht 7.1

- Maak een array `ledPositions` met de waarden 0, 2, 4, 6, 8
- Toon de eerste en laatste waarde in de console
- Voeg het getal 9 toe aan de array
- Toon de lengte van de array
- Gebruik de lengte om de laatste waarde uit de array te tonen

## Arrays en for-loops

In [les 4](les4.md) heb je geleerd over for-loops. Voor-loops zijn perfect om door arrays te gaan. Je gebruikt de index
om bij elke waarde in de array te komen.

### Basis patroon

```typescript
let myArray = [10, 20, 30, 40];

for (let i = 0; i < myArray.length; i++) {
  console.log(myArray[i]);
}
// toont: 10, 20, 30, 40
```

### LED's met array

```typescript
let colors = [Colors.Red, Colors.Blue, Colors.Green];

for (let i = 0; i < colors.length; i++) {
  // positie in de array is positie van de LED
  // waarde inde array is de kleur van de LED
  light.setPixelColor(i, colors[i]);
}
```

#### Opdracht 7.2

- Maak een array `myNumbers` met de waarden 5, 10, 15, 20
- Gebruik een for-loop om elk getal te tonen in de console
- Maak een array `ledColors` met 3 verschillende kleuren
- Gebruik een for-loop om LED's 0, 1, 2 in deze kleuren aan te zetten

## Praktische voorbeelden

### Som van getallen berekenen

```typescript
let scores = [85, 92, 78, 95, 88];
let total = 0;

for (let i = 0; i < scores.length; i++) {
  total = total + scores[i];
}

console.log(`Totaal: ${total}`);
console.log(`Gemiddelde: ${total / scores.length}`);
```

### LED patroon met array

```typescript
let pattern = [Colors.Red, Colors.Blue, Colors.Red, Colors.Blue, Colors.Red];

function showPattern() {
  for (let i = 0; i < pattern.length; i++) {
    light.setPixelColor(i, pattern[i]);
  }
}

showPattern();
```

### Animatie met array

```typescript
let animation = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

function runAnimation() {
  for (let i = 0; i < animation.length; i++) {
    light.clear();
    light.setPixelColor(animation[i], Colors.Green);
    pause(200);
  }
}

runAnimation();
```

#### Opdracht 7.3

- Maak een array `temperatures` met de waarden 18, 22, 25, 30, 35
- Bereken het gemiddelde van deze temperaturen met een for-loop
- Maak een array `melody` met verschillende toonhoogtes
- Speel de melodie af met een for-loop

## Arrays en functies combineren

### Array als parameter

```typescript
function playMelody(notes: number[]) {
  for (let i = 0; i < notes.length; i++) {
    music.playTone(notes[i], 300);
    pause(100);
  }
}

let happyTune = [262, 294, 330, 349];
playMelody(happyTune);
```

### LED-show met array

```typescript
let rainbowColors = [Colors.Red, Colors.Orange, Colors.Yellow, Colors.Green, Colors.Blue, Colors.Purple];

function showRainbow(colorList: number[]) {
  for (let i = 0; i < colorList.length; i++) {
    if (i < 10) {
      light.setPixelColor(i, colorList[i]);
    }
  }
}

showRainbow(rainbowColors);
```

#### Opdracht 7.4

- Schrijf een functie `countValues` die een array van getallen ontvangt
- De functie telt hoeveel waarden groter zijn dan 10
- Test met verschillende arrays
- Schrijf een functie `lightUpLeds` die een array van LED-posities ontvangt
- Alle LED's op die posities worden groen

## Bouwstenen

| Probleem                                      | Oplossing                     |
| --------------------------------------------- | ----------------------------- |
| Iets onthouden voor later                     | **Globale variabele**         |
| Vaste waarden                                 | **Constanten**                |
| Rekenen of dingen veranderen                  | **Operatoren**                |
| Keuzes maken                                  | **If-statement**              |
| Iets één keer doen                            | **Losse code**                |
| Iets meerdere keren (ongeveer) hetzelfde doen | **For-loop**                  |
| Iets continu blijven herhalen                 | **Forever-loop**              |
| Reageren op (gebruikers)input                 | **Event handler**             |
| Gebruiken van input of output                 | **CPX functie**               |
| Hetzelfde doen op verschillende momenten      | **Functie**                   |
| Hetzelfde doen met verschillende waarden      | **Functie met parameters**    |
| Meerdere vergelijkbare waarden opslaan        | **Array**                     |
| Door alle waarden in een lijst gaan           | **For-loop met array.length** |

#### Opdracht 7.5

Voor elk probleem, identificeer welke bouwstenen je nodig hebt:

1. "Bewaar de scores van 5 spelers en toon de hoogste score"
2. "Speel een lijst van noten af als melodie"
3. "Zet LED's aan op posities die in een lijst staan"
4. "Tel hoeveel temperatuurmetingen boven 25 graden zijn"

#### Opdracht 7.6: Basis arrays

- Maak een array `studentNames` met 4 namen
- Maak een array `testScores` met 4 cijfers
- Toon alle namen met een for-loop
- Bereken het gemiddelde van alle toetsen (moet ook werken voor meer dan 4)

#### Opdracht 7.7: LED patronen

- Maak een array `ledSequence` met posities 0, 2, 4, 6, 8
- Maak een array `sequenceColors` met 5 verschillende kleuren
- Gebruik for-loops om de LED's op die posities in die kleuren aan te zetten
- Maak een functie `clearPattern` die alle LED's op de posities uitzet

#### Opdracht 7.8: Muziek en geluid

- Maak een array `alarmTones` met 3 verschillende toonhoogtes
- Schrijf een functie `playAlarm` die alle tonen afspeelt
- Maak een array `buttonSounds` met verschillende geluiden
- Laat knop A door de array heen gaan en elk geluid afspelen

#### Opdracht 7.9: Data verwerken

- Maak een array `dailyTemperatures` met 7 temperatuurwaarden
- Bereken de gemiddelde temperatuur
- Tel hoeveel dagen warmer dan 20 graden waren
- Zoek de hoogste temperatuur
- Toon alle resultaten met template strings

#### Opdracht 7.10: Interactief spel

Maak een geheugenspel:

- Maak een array met een reeks LED-posities
- Laat het patroon zien (elke LED kort oplichten)
- Speler moet het patroon herhalen met knoppen
- Gebruik arrays om zowel het patroon als de input op te slaan

Schrijf eerst pseudocode voordat je begint!

#### Zelfstudie 7

Bedenk van tevoren goed welke bouwstenen je nodig hebt en gebruik arrays waar mogelijk:

- Maak een LED-piano waarbij elke touch sensor een andere noot speelt en de bijbehorende LED oplicht
- Schrijf een data-logger die sensorwaarden opslaat in een array en statistieken berekent

<!-- TODO: meer opdrachten met sensoren, minder console? -->
<!-- TODO: geheugenspel aanpassen, of als case voor les 8? -->
