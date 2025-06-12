# Les 2: Variabelen en Functies zonder Parameters

## Onderwerpen

- Variabelen
- Zelf gedefinieerde functies zonder parameters

<!--

- Begrijpen wat variabelen zijn en hoe je ze gebruikt
- Functies maken en aanroepen

-->

## Variabelen

Een variabele gebruik je om een waarde op te slaan in je programma. Een beetje zoals je rekent met letters bij wiskunde
`x=1`, maar in een programma kan je ook langere namen gebruiken en andere dingen opslaan. Als je een nieuwe variabele
maakt, gebruik je het keyword `let`.

Bijvoorbeeld:

```typescript
let price = 10;
let name = "Super";
```

De waarde kan je later veranderen (vandaar de naam: variabele). Omdat de variabele al bestaat, hoef je geen `let` meer
te gebruiken, en mag het ook niet meer!

```typescript
price = 20; // price is nu: 20
name = name + "man"; // name is nu: Superman
```

### Waarde tonen met console.log

Met `console.log()` kun je de waarde van een variabele laten zien in de console. Dit is handig om te controleren of je
code werkt zoals je verwacht.

Voorbeeld:

```typescript
let age = 16;
console.log(age); // laat 16 zien in de console
```

#### Opdracht

- Maak een variabele `counter` aan en toon hem in de console.
- Tel er 1 bij op, en check of het goed gegaan is in de console.

## Datatypes

In JavaScript kun je verschillende soorten waarden opslaan in variabelen. Dit noem je datatypes. De belangrijkste
datatypes zijn:

- **Getallen** (numbers): bijvoorbeeld `10`, `3.14`, `-5`
- **Tekst** (strings): bijvoorbeeld `"Hallo"`, `"Superman"`
- **Boolean** (waar of niet waar): `true` of `false`

Voorbeelden:

```typescript
let age = 16; // number
let studentName = "Alex"; // string
let isFinished = false; // boolean
```

### Strings

Een string is een stukje tekst. In JavaScript zet je een string altijd tussen aanhalingstekens: enkele (' '), dubbele
(" ") of backticks (` `). Bijvoorbeeld:

```typescript
let studentName = "Alex";
let message = "Hallo";
let sentence = `Dit is een string`;
```

Je mag zelf kiezen welke je gebruikt, maar ze moeten altijd aan het begin en einde hetzelfde zijn.

### Backticks

Backticks (` `), zoom even in en zoek ze op op je toetsenbord, lijken op enkele aanhalingstekens, maar hebben een extra
functie: je kunt er variabelen en stukjes code direct in de tekst zetten. Dit heet een string template. Je gebruikt dan
`${ }` om een variabele of code in te voegen.

Voorbeeld:

```typescript
let name = "Alex";
let message = `Hello, ${name}!`;
// Hello, Alex!
let answer = `1 + 1 = ${1 + 1}`;
// 1 + 1 = 2
```

Met gewone aanhalingstekens (' ' of " ") kan dat niet, dan wordt alles letterlijk als tekst gezien.

#### Opdracht

- Maak een variabele `studentName` aan en geef deze een waarde.
- Maak een variabele `score` aan en geef deze een getal.
- Gebruik een string template om een bericht met `console.log()` te tonen: `Alex heeft 5 punten gehaald.` Gebruik
  hiervoor de variabelen.
- Verander de waarde van `score` en laat het nieuwe bericht opnieuw zien.

#### Opdracht: Cookie clicker

Schrijf eerst pseudocode, en daarna de echte code:

Maak het spelletje button-clicker. Hierbij klikt iemand zo snel mogelijk op button A, en toont de computer hoe vaak je
geklikt hebt.

Expert: maak een twee speler versie met A en B.

## Opdrachten

- Schrijf een functie die een LED aanzet
- teller
- Steeds de volgende LED aan
