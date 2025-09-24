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

- Maak een array `temperatures` met de waarden 18, 31, 25, 30, 17
- Bereken het gemiddelde van deze temperaturen met een for-loop (denk hier eerst over na)
- Vind ook de hoogste waarde in de array

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

- Maak een lege array `diceValues`
- Vul deze met 1000 random waarden van 1 t/m 6.
- Schrijf een functie `countValues` die een array van getallen ontvangt, en een bepaalde waarde.
- De functie telt hoe vaak deze waarde voorkomt in de array.
- Test met verschillende waarden.

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

#### Opdracht 7.5: Basis arrays

- Maak een array `studentNames` met 4 namen
- Maak een array `testScores` met 4 cijfers
- Toon alle namen, en cijfers met een for-loop
- Bereken het gemiddelde van alle toetsen (moet ook werken voor meer dan 4)

#### Opdracht 7.6: LED patronen

- Maak een array `ledSequence` met posities 0, 2, 4, 6, 8
- Maak een array `sequenceColors` met 5 verschillende kleuren
- Gebruik for-loops om de LED's op die posities in die kleuren aan te zetten
- Maak een functie `clearPattern` die alle LED's op de posities uitzet

#### Opdracht 7.7: Case - Tekenen op de CPX

Deel 1

- Schrijf een programma om te ‘tekenen’ op de Circuit Playground Express. Als het programma start staan alle LEDs op de
  ring uit (zwart).

Stap 1

- Je kunt met de A knop een LED (0 t/m 9) selecteren. In de console laat je zien bij welke LED je bent.

Stap 2

- Als een LED geselecteerd is, kan je hem met B aan en uit zetten (kleur mag je zelf kiezen, maar geen wit).

Stap 3

- Als je op A klikt, flitst de nieuwe (!) geselecteerde LED kort (wit, zwart en terug naar de kleur die hij was) om te
  laten zien waar je op de ring zit.

Deel 2

- Als je schudt, dan draait de tekening een heel rondje, daarna kan je verder met tekenen.

#### Zelfstudie 7

1. Maak een array met 5 getallen en toon elk getal in de console met een for-loop.
2. Maak een array met 3 kleuren en zet elke LED op de ring achtereenvolgens op die kleur (gebruik een for-loop).
3. Maak een lege array en voeg er 3 namen aan toe. Toon alle namen in de console.
4. Maak een array met 10 getallen. Tel alle getallen bij elkaar op en toon het totaal in de console.

5. **Raadspel** - Maak een spel waarbij de computer links/rechts kiest:
   - Computer kiest willekeurig links of rechts, speler raadt met knop A (links) en B (rechts)
   - LED's aan de kant die de speler kiest gaan 1 seconde branden in een kleur naar keuze
   - Goed geraden: vrolijk geluid + LED draait een rondje op de CPX
   - Fout geraden: zoemer geluid
   - Console toont na elke gok hoeveel keer je goed en fout hebt gegokt
   - Na elke gok kiest de computer opnieuw een willekeurige kant
   - Extra: houd bij hoeveel keer op rij goed gegokt, LED draait dat aantal rondjes bij winst
   - Extra: cheat mode bij A+B indrukken: verraadt welke kant de computer gaat kiezen
