# Les 3: Operatoren, Vergelijkingen en If-statements

## Onderwerpen

- Operatoren
- Vergelijkingen
- If-statements

<!-- TODO: Boolean direct in if-statement -->
<!-- TODO: NOT ! -->

<!--

- Logische vergelijkingen maken
- Beslissingen nemen in code

-->

## Operatoren

_Operatoren_ zijn symbolen waarmee je bewerkingen (vaak berekeningen) kunt doen of waarden kunt vergelijken. Je kent ze
al van wiskunde, zoals `+` en `-`. In programmeren gebruiken we dezelfde symbolen, maar er zijn er nog meer.

<!-- TODO: Nog een modulus opdrachtje toevoegen -->

### Rekenoperatoren

Met rekenoperatoren kun je wiskundige berekeningen uitvoeren:

| Operator | Betekenis                 | Voorbeeld | Resultaat  |
| -------- | ------------------------- | --------- | ---------- |
| `+`      | Optellen                  | `5 + 3`   | `8`        |
| `-`      | Aftrekken                 | `10 - 4`  | `6`        |
| `*`      | Vermenigvuldigen          | `6 * 2`   | `12`       |
| `/`      | Delen                     | `15 / 3`  | `5`        |
|          |                           | `16 / 3`  | `5.333...` |
| `%`      | Modulus (rest bij deling) | `15 % 3`  | `0`        |
|          |                           | `16 % 3`  | `1`        |

Je kunt deze operatoren gebruiken met getallen en variabelen:

```typescript
let price = 10;
let discount = 2;
let finalPrice = price - discount; // finalPrice is nu 8

let total = 5 * 3; // total is nu 15
console.log(total);
```

### Math

JavaScript heeft een ingebouwd `Math` object met (heel veel) handige functies om met getallen te werken. Wij maken het
meest gebruik van onderstaande functies:

| Functie              | Betekenis                                                        | Voorbeeld                | Resultaat  |
| -------------------- | ---------------------------------------------------------------- | ------------------------ | ---------- |
| `Math.round()`       | Afronding naar dichtstbijzijnde gehele getal                     | `Math.round(4.7)`        | `5`        |
|                      |                                                                  | `Math.round(4.3)`        | `4`        |
| `Math.floor()`       | Afronding naar beneden                                           | `Math.floor(4.9)`        | `4`        |
| `Math.ceil()`        | Afronding naar boven                                             | `Math.ceil(4.1)`         | `5`        |
| `Math.random()`      | Willekeurig kommagetal tussen 0 en 1                             | `Math.random()`          | `0.247...` |
| `Math.randomRange()` | Willekeurig geheel getal in een range (bestaat alleen op de CPX) | `Math.randomRange(1, 6)` | `4`        |

Voorbeelden van gebruik:

```typescript
let price = 12.99;
let roundedPrice = Math.round(price); // 13

console.log(`Prijs: ${roundedPrice}`);
```

#### Opdracht 3.1

- Maak een variabele `number1` met waarde 20
- Maak een variabele `number2` met waarde 8
- Bereken de som, het verschil, het product (\*) en het quotiënt (/) van deze getallen
- Toon alle resultaten in de console met een net bericht
- Gebruik `Math` om bij de deling een geheel resultaat te tonen

## Vergelijkingsoperatoren

Met vergelijkingsoperatoren kun je waarden met elkaar vergelijken. Het resultaat is altijd een _boolean_: `true` (waar)
of `false` (niet waar):

| Operator | Betekenis             | Voorbeeld | Resultaat |
| -------- | --------------------- | --------- | --------- |
| `===`    | Gelijk aan            | `5 === 5` | `true`    |
| `!==`    | Niet gelijk aan       | `5 !== 3` | `true`    |
| `>`      | Groter dan            | `10 > 5`  | `true`    |
| `<`      | Kleiner dan           | `3 < 8`   | `true`    |
| `>=`     | Groter dan of gelijk  | `5 >= 5`  | `true`    |
| `<=`     | Kleiner dan of gelijk | `4 <= 7`  | `true`    |

Voorbeelden met variabelen:

```typescript
let age = 16;
let minAge = 18;

console.log(age >= minAge); // false
console.log(age < minAge); // true

let score1 = 85;
let score2 = 85;
console.log(score1 === score2); // true
```

## If-statements

Deze vergelijksoperatoren hebben we nodig om beslissingen te laten nemen door een programma. Hiervoor gebruik je een
_if-statement_. Een if-statement voert code alleen uit als een bepaalde voorwaarde waar is (`true`).

De basis structuur is:

```typescript
if (voorwaarde) {
  // code die uitgevoerd wordt als voorwaarde waar is
}
```

Voorbeelden:

```typescript
let age = 16;
let minAge = 18;

if (age < minAge) {
  console.log("Je bent te jong!");
}

let temperature = 30;
if (temperature > 25) {
  console.log("Het is warm buiten!");
}
```

### If-else

Je kunt ook code uitvoeren als de voorwaarde **niet** waar is met `else`:

```typescript
let score = 75;

if (score >= 80) {
  console.log("Goed gedaan!");
} else {
  console.log("Probeer het nog eens!");
}
```

#### Opdracht 3.2

- Maak een variabele `playerScore` met waarde 85
- Schrijf een if-statement dat "Je hebt gewonnen!" toont als de score hoger dan 80 is
- Voeg een else toe die "Probeer het nog eens!" toont als de score 80 of lager is
- Test met verschillende waardes

#### Opdracht 3.3

- Maak twee variabelen `temperature` (waarde 25) en `maxTemp` (waarde 30)
- Controleer of de temperatuur hoger is dan de maximale temperatuur
- Controleer of de temperatuur gelijk is aan 25
- Toon beide resultaten in de console

#### Opdracht 3.4

Maak een programma dat een LED bestuurt op basis van een getal:

- Maak een variabele `score` met een waarde naar keuze (bijvoorbeeld 15)
- Gebruik een if-statement om te controleren of `score` groter is dan 10
- Als het getal groter is dan 10: zet LED 0 aan (rood)
- Als het getal 10 of kleiner is: zet LED 0 uit
- Test je programma door de waarde van `score` te veranderen

#### Opdracht 3.5

Maak een LED die aan/uit gaat als je op de knop drukt:

- Maak een globale variabele `ledIsOn` met startwaarde `false`
- Maak een functie `toggleLED()` die:
  - Controleert met een if-statement of `ledIsOn` waar (`true`) is
  - Als de LED aan is: zet LED 0 uit en verander `ledIsOn` naar `false`
  - Als de LED uit is: zet LED 0 aan (rood) en verander `ledIsOn` naar `true`
- Roep deze functie aan wanneer knop A wordt ingedrukt
- Test door meerdere keren op knop A te drukken

#### Opdracht 3.6

Maak een geluksspel met scores en berichten:

- Maak een variabele `playerName` met je eigen naam als waarde
- Maak een variabele `randomScore` die een willekeurig getal tussen 0 en 100 krijgt
- Gebruik een if-statement om te controleren of `randomScore` 50 of hoger is
- Als de score 50 of hoger is: toon in de console `"Gefeliciteerd [naam]! Je hebt [score] punten behaald en gewonnen!"`
- Als de score lager dan 50 is: toon in de console
  `"Helaas [naam], je hebt [score] punten behaald. Probeer het nog eens!"`
- Gebruik string templates (`${}`) om de naam en score in de berichten te tonen
- Pas het programma aan zodat het gespeeld kan worden door op knop A te drukken

## Bouwstenen

| Probleem                                 | Oplossing             |
| ---------------------------------------- | --------------------- |
| Iets onthouden voor later                | **Globale variabele** |
| Vaste waarden                            | **Constanten**        |
| Rekenen of dingen veranderen             | **Operatoren**        |
| Keuzes maken                             | **If-statement**      |
| Iets één keer doen                       | **Losse code**        |
| Iets continu blijven herhalen            | **Forever-loop**      |
| Reageren op (gebruikers)input            | **Event handler**     |
| Gebruiken van input of output            | **CPX functie**       |
| Hetzelfde doen op verschillende momenten | **Functie**           |

#### Zelfstudie 3

Bedenk van tevoren goed welke bouwstenen je nodig hebt:

1. Maak een programma dat een LED laat "rondjeslopen" op de Circuit Playground
2. **Pokémon Vangst Spel** - Maak een digitale Pokédex:
   - Maak globale variabelen `totalPokemon` (waarde 141) en `pokemonCaught` (waarde 0)
   - **Knop A**: Probeer een Pokémon te vangen
     - Genereer een willekeurig getal tussen 1 en 6 met `Math.randomRange(1, 6)`
     - Als het getal 1 is: voeg 1 toe aan `pokemonCaught` en toon "Gefeliciteerd! Je vangt een nieuwe Pokémon!"
     - Anders: toon "Helaas, geen Pokémon gevangen dit keer"
     - Zorg dat je nooit meer dan 141 Pokémon kunt vangen
   - **Knop B**: Toon voortgang
     - Bereken het percentage gevangen Pokémon (delen door totaal × 100, afgerond)
     - Toon met string templates: `"Je hebt [aantal] van de [totaal] Pokémon gevangen ([percentage]%)"`
     - Als je precies de helft hebt: toon extra "Je bent halverwege!"
     - Als je alle 141 hebt: toon "Pokédex compleet! Je bent een Pokémon Master!"
3. Maak een LED-patroon dat continu heen en weer beweegt (denk hier eerst goed over na)
