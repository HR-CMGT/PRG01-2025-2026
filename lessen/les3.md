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

**Operatoren** zijn symbolen waarmee je bewerkingen (vaak berekeningen) kunt doen of waarden kunt vergelijken. Je kent
ze al van wiskunde, zoals `+` en `-`. In programmeren gebruiken we dezelfde symbolen, maar er zijn er nog meer.

<!-- TODO: Nog een modulus opdrachtje toevoegen -->
<!-- TODO: Math.round/floor/ceil en random toevoegen -->

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

#### Opdracht

- Maak een variabele `number1` met waarde 20
- Maak een variabele `number2` met waarde 8
- Bereken de som, het verschil, het product en het quotiënt van deze getallen
- Toon alle resultaten in de console

## Vergelijkingsoperatoren

Met vergelijkingsoperatoren kun je waarden met elkaar vergelijken. Het resultaat is altijd een **boolean**: `true`
(waar) of `false` (niet waar):

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
**if-statement**. Een if-statement voert code alleen uit als een bepaalde voorwaarde waar is (`true`).

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

#### Opdracht

- Maak een variabele `playerScore` met waarde 85
- Schrijf een if-statement dat "Je hebt gewonnen!" toont als de score hoger dan 80 is
- Voeg een else toe die "Probeer het nog eens!" toont als de score 80 of lager is
- Test met verschillende waardes

- Maak twee variabelen `temperature` (waarde 25) en `maxTemp` (waarde 30)
- Controleer of de temperatuur hoger is dan de maximale temperatuur
- Controleer of de temperatuur gelijk is aan 25
- Toon beide resultaten in de console

## Opdrachten

- Schrijf een programma dat controleert of een variabele groter is dan 10
- Led een rondje
- Heen en weer
- Toggle led
- Gebruik een if-statement om een LED aan of uit te zetten
- Rekenopdrachtjes met tekst

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

<!-- TODO: Opdrachten toevoegen -->
<!-- TODO: shorthand notaties? -->
