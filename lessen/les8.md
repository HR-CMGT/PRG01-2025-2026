# Les 8: Herhaling

## Onderwerpen

- Herhaling
- Oefenen met alle onderwerpen

<!--

- Herhaling niet hier, maar in de slides
- Alle concepten in cases

-->

## Opdrachten

### Case 1: Pacman

In deze opdracht ga je de Circuit Playground Express programmeren voor een eenvoudige versie van Pacman. Geen doolhof,
geen gangen, alleen jij en een spook.

- Schrijf verzorgde code en gebruik functies om je code te structureren
- Werk alle stappen uit
- Test elke stap voordat je naar de volgende gaat

[Voorbeeld: Pacman IKEA lamp, gemaakt met adafruit led strip](https://www.youtube.com/watch?v=uA1B6-CTotE)

#### STAP 1: Het Spook

We beginnen met een spook. Het spook is een oranje led, dat continu rondjes tegen de klok in draait op de led-ring. Hij
doet dit met 1 ledje per seconde, en begint op led 0.

#### STAP 2: Pacman Beweegt

Pacman is ook een ledje op de ring (uiteraard geel), dat dezelfde kant op beweegt, maar alleen als je op A klikt. Hij
begint op led 5. Elke stap die Pacman zet levert een punt op. Na elke klik op A wordt in de console met een net bericht
getoond waar het spook is en waar Pacman is, en hoeveel punten je hebt.

#### STAP 3: Game Over Detectie

Als het spook Pacman vangt is het game over. Toon dit in de console, en reset de punten en de posities van het spook en
Pacman.

#### STAP 4: Animatie Functie

Schrijf een functie die één parameter van het type `number` verwacht. Op het moment dat je de functie aanroept kan je
dus een getal meegeven. Deze functie zet 1 voor 1 alle Leds op rood met een korte pauze ertussen, behalve het ledje met
het meegegeven getal. Daarna zet de functie de 10 leds weer 1 voor 1 uit, maar nu in omgekeerde volgorde.

#### STAP 5: Animatie bij Game Over

Gebruik de functie van stap 4 na een GameOver, waarbij de led waar Pacman doodgegaan is uit moet blijven.

#### STAP 6: Score Geschiedenis

Na een game over wordt jouw score getoond, en daaronder een lijst met alle scores die eerder behaald zijn met een
nummer ervoor.

#### STAP 7: Hoogste Score

Toon apart wat de hoogste score tot nu was. Gebruik hiervoor de lijst en geen aparte variabele.

#### STAP 8: Versnellend Spook

Laat het spook na elke stap een beetje sneller lopen. Na game over wordt hij weer net zo langzaam als in het begin.

#### STAP 9: Powerpill (expert)

Voeg een powerpil toe:

- Pacman heeft 3 powerpills. Als je op A+B drukt neemt pacman een powerpill in.
- De powerpill blijft 15 stappen actief.
- Zo lang de powerpill actief is, teken je het spookje blauw.
- Als de powerpill actief is, en het spook raakt pacman, dan krijg je 10 punten. Daarna is de powerpill uitgewerkt. Het
  spook spawnt 5 stappen voor Pacman.

### Case 2: Simon

Maak een spel om je geheugen te trainen. Bij dit spel gebruik je de linker helft van de ring om groen te laten zien en
de rechter voor rood.

**Spelregels:**

- De playground laat willekeurig de kleur rood of groen zien
- De gebruiker moet dit nadoen door op button A of B te drukken om de LEDs rood of groen te maken
- Pas als de speler genoeg kleuren ingedrukt heeft worden de kleuren gecontroleerd
- Als dit correct is ga je door naar de volgende ronde, waar de playground eerst weer dezelfde kleur zal laten zien,
  maar daarna een nieuwe (willekeurige)
- Steeds als de gebruiker de kleuren correct nadoet komt er één willekeurige kleur bij
- Als de gebruiker het fout doet begint het spel opnieuw

[Hoe werkt Simon?](https://www.youtube.com/watch?v=1Yqj76Q4jJ4)

- Schrijf verzorgde code en gebruik functies om je code te structureren
- Werk alle stappen uit
- Test elke stap voordat je naar de volgende gaat

#### STAP 1: Kleuren Tonen

Maak een lijst met 3 'kleuren' ("A", "A", "B"), en laat deze met korte pauzes ertussen zien op de ring (A = groen en
links, B = rood en rechts). De ring moet even uit gaan om te zien dat rood 2x in de lijst staat. Zet de code om dit te
laten zien in een functie.

#### STAP 2: Willekeurige Kleur Toevoegen

Laat de computer een random 'kleur' (A of B) kiezen en toevoegen aan de lijst. Daarna moet hij de kleuren weer tonen.
Tip: voeg deze code om een nieuwe kleur te kiezen toe aan de functie om de kleuren te laten zien.

#### STAP 3: Speler Input Controleren

Als de speler op A of B drukt controleer dan of dit goed is (A = groen, B = rood). Je moet hiervoor bijhouden op welke
positie in de lijst de speler is.

#### STAP 4: Fout Afhandelen

Als het fout is beginnen we opnieuw. De spelerpositie gaat terug naar 0, de lijst wordt leeggemaakt, en we gaan weer
terug naar de code van stap 2.

#### STAP 5: Volgende Ronde

Als de speler op de laatste positie is, en het is goed gaan we naar de volgende ronde. De spelerpositie gaat terug naar
0, en de computer is weer aan zet (stap 2).

#### Extra Uitdagingen (optioneel):

- **Vier kleuren (expert):** Gebruik niet twee kleuren en knoppen A en B, maar gebruik vier kleuren en touch pins A0,
  A3, A4 en A7
- **Geluid:** Voeg verschillende tonen toe om de gebruiker te helpen de reeks te onthouden
- **Feedback:** Geef feedback in de vorm van animaties/geluid bij game over
