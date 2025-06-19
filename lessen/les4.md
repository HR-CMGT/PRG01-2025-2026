# Les 4: For-loops en Patroonherkenning

## Onderwerpen

- For-loops
- Patroonherkenning

<!--
- Herhaling in code toepassen
- Patronen herkennen en programmeren

Met patronen herkennen wordt bij deze cursus bedoeld dat je begrijpt wanneer een bepaalde techniek (variabele, if statement, loop etc) gebruikt moet worden -->

## For-loops

Soms wil je een stukje code meerdere keren uitvoeren. In plaats van dezelfde code telkens opnieuw te schrijven (daar
houden programmeurs niet van) kun je een **for-loop** gebruiken. Een for-loop herhaalt code een bepaald aantal keren.

De basis structuur van een for-loop is:

```typescript
for (let i = 0; i < numberOfRepeats; i++) {
  // code die wordt herhaald
}
```

Uitleg van de onderdelen:

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

#### Opdracht

```typescript
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

Wat toont deze code in de console?

#### Opdracht

- Maak een for-loop die "Hallo!" 3 keer toont in de console
- Maak een for-loop die van 0 tot 7 telt
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

#### Opdracht

- Maak een for-loop die alle LED's groen maakt
- Maak een for-loop die de LED's één voor één rood laat oplichten met een pauze van 300 milliseconden
- Maak een for-loop die de eerste 5 LED's blauw maakt

## Patroonherkenning

Met **Patroonherkenning** bedoelen we dat je leert herkennen wanneer je een bepaalde programmeertechniek moet
gebruiken. Dit is een belangrijke vaardigheid in programmeren.

### Wanneer gebruik je wat?

| Probleem                                      | Oplossing             |
| --------------------------------------------- | --------------------- |
| Iets onthouden voor later                     | **Globale variabele** |
| Rekenen of dingen veranderen                  | **Operatoren**        |
| Keuzes maken                                  | **If-statement**      |
| Iets meerdere keren (ongeveer) hetzelfde doen | **For-loop**          |
| Iets continu blijven herhalen                 | **Forever-loop**      |
| Reageren op (gebruikers)input                 | **Event handler**     |
| Gebruiken van input of output                 | **CPX functie**       |
| Hetzelfde doen op verschillende momenten      | **Functie**           |

### Voorbeelden van patroonherkenning

**Probleem**: "Laat 5 keer achter elkaar een LED knipperen" **Patroon**: Gebruiken output → **functie CPX**, Herhaling
→ **for-loop**

**Probleem**: "Monitor de temperatuur en zet een rode LED aan als deze hoger is dan 25" **Patroon**: Continu herhalen →
**forever**, Gebruiken input → **functie CPX**, Beslissing → **if-statement**

**Probleem**: "Onthoud hoeveel keer er op een knop is gedrukt" **Patroon**: Reageren op input → **event**, Waarde
opslaan → **variabele**

#### Opdracht: Patroonherkenning oefenen

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

Kies er 3 uit, schrrijf daar pseudocode voor en implementeer deze in echte code.

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

#### Opdracht

Wat doen bovenstaande for-loop voorbeelden?

#### Opdracht: Combinatie-oefening

- Maak een variabele `ledCount` met waarde 8
- Gebruik een for-loop die van 0 tot `ledCount` loopt
- Zet de eerste helft van de LED's op groen, de tweede helft op rood
- Gebruik een if-statement om te bepalen welke kleur elke LED krijgt

## Opdrachten

Begin bij elke opdracht met te bedenken welke patronen je nodig hebt, en schrijf pseudocode.

<!-- TODO: pseudocode optioneel maken? -->

### Opdracht 1: Tel van 1 tot 10

Maak een programma dat van 1 tot 10 telt en elk getal toont in de console.

### Opdracht 2: LED's één voor één oplichten

Maak een programma dat alle LED's op de Circuit Playground Express één voor één aan zet, met een pauze tussen elke LED.

### Opdracht 3: Knipperend patroon

Maak een programma dat:

1. Alle LED's aanzet
2. Wacht 500 milliseconden
3. Alle LED's uitzet
4. Wacht 500 milliseconden
5. Dit 5 keer herhaalt

### Opdracht 4: Regenboog maken

Zet alle LED's één voor één aan, en geef daarbij elke LED een andere kleur.
