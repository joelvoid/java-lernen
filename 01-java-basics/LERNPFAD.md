# Phase 1: Java Basics - Vollstaendiger Lernpfad
## 8 Lektionen mit Minecraft-Beispielen fuer Anfaenger (12+)

**Dauer:** 4-5 Wochen (ca. 1 Stunde pro Tag, 4-5x pro Woche)
**Voraussetzungen:** Keine! Du faengst bei Null an.
**Ziel:** Einfache Java-Programme selbst schreiben koennen.

---

## Gamification System

**Freischalten der Lektionen:**
- Lektion 1: FREIGESCHALTET
- Lektion 2: Schaltet frei wenn L1 bestanden
- Lektion 3: Schaltet frei wenn L2 bestanden
- Lektion 4: Schaltet frei wenn L3 bestanden
- Lektion 5: Schaltet frei wenn L4 bestanden
- Lektion 6: Schaltet frei wenn L5 bestanden
- Lektion 7: Schaltet frei wenn L6 bestanden
- Lektion 8: Schaltet frei wenn L7 bestanden
- ABSCHLUSSPROJEKT: Schaltet frei wenn L8 bestanden

**Punkte pro Lektion:** 100 XP
**Abschlussprojekt:** 500 XP

---

## Lektion 1: Was ist ein Programm?

### Konzept

Ein **Programm** ist eine Liste von Anweisungen fuer den Computer. Wie ein Rezept beim Kochen: Schritt fuer Schritt sagt man dem Computer, was er tun soll.

**Minecraft-Bezug:**
Wenn du in Minecraft einen Ofen benutzt, folgt das Spiel einem Programm:
1. Pruefe: Ist Brennstoff vorhanden?
2. Pruefe: Ist ein Item zum Schmelzen da?
3. Wenn ja: Starte den Schmelzvorgang
4. Warte die Zeit ab
5. Gib das Ergebnis aus

Das ist ein Programm! Und genau so schreibst du bald eigene Programme.

### Wichtige Begriffe

| Begriff | Erklaerung | Minecraft-Beispiel |
|---------|-----------|-------------------|
| Programm | Eine Liste von Anweisungen | Crafting-Rezept |
| Compiler | Uebersetzt deinen Code fuer den Computer | Wie ein Uebersetzer |
| Terminal | Schwarze Box zum Ausfuehren von Befehlen | Chat-Fenster in MC |
| Datei | Wo dein Code gespeichert wird | Eine .java Datei |

### Dein erstes Programm anschauen

Oeffne `src/HelloWorld.java` und schau dir den Code an:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hallo Welt! Mein erstes Java-Programm!");
    }
}
```

**Was passiert hier?**
- `public class HelloWorld` - Das ist der Name deines Programms
- `public static void main(String[] args)` - Hier startet das Programm (immer gleich!)
- `System.out.println(...)` - Gibt Text auf dem Bildschirm aus

### Aufgabe 1.1: HelloWorld ausfuehren

**Ziel:** Dein erstes Programm kompilieren und starten.

**Schritte:**
1. Oeffne das Terminal in VS Code (Strg + OE)
2. Tippe: `javac src/HelloWorld.java` und druecke Enter
3. Tippe: `java -cp src HelloWorld` und druecke Enter
4. Du solltest sehen: `Hallo Welt! Mein erstes Java-Programm!`

**Erwartete Ausgabe:**
```
Hallo Welt! Mein erstes Java-Programm!
```

### Aufgabe 1.2: Text aendern

**Ziel:** Den Text in HelloWorld.java aendern und neu ausfuehren.

**Schritte:**
1. Aendere den Text in den Anfuehrungszeichen zu: `"Ich lerne Java fuer Minecraft!"`
2. Speichern mit Strg + S
3. Kompilieren: `javac src/HelloWorld.java`
4. Starten: `java -cp src HelloWorld`

**Erwartete Ausgabe:**
```
Ich lerne Java fuer Minecraft!
```

### Aufgabe 1.3: Mehrere Zeilen ausgeben

**Ziel:** Erstelle eine neue Datei `MeinStart.java` die 3 Zeilen ausgibt.

**Was du schreiben sollst:**
1. Erstelle `src/MeinStart.java`
2. Schreibe das Geruest (public class... main...)
3. Schreibe 3x `System.out.println(...)` mit verschiedenen Texten

**Erwartete Ausgabe (ungefaehr):**
```
=== Mein erstes eigenes Programm ===
Ich heisse [dein Name]
Ich will Minecraft-Mods programmieren!
```

**Hinweis:** Der Klassenname MUSS gleich heissen wie die Datei! `MeinStart.java` braucht `public class MeinStart`.

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/MeinStart.java`
3. Starten: `java -cp src MeinStart`

### Quiz Lektion 1

**Frage 1:** Was macht `System.out.println()`?
- A) Loescht eine Datei
- B) Gibt Text auf dem Bildschirm aus
- C) Startet Minecraft
- D) Erstellt eine Variable

**Frage 2:** Was macht `javac`?
- A) Startet das Programm
- B) Loescht die Datei
- C) Kompiliert (uebersetzt) den Code
- D) Oeffnet VS Code

**Frage 3:** Welche Dateiendung haben Java-Dateien?
- A) .txt
- B) .py
- C) .java
- D) .minecraft

**Frage 4:** Was passiert wenn der Klassenname nicht zur Datei passt?
- A) Es funktioniert trotzdem
- B) Es gibt einen Fehler
- C) Java aendert den Namen automatisch
- D) Der Computer stuerzt ab

**Antworten:** 1-B, 2-C, 3-C, 4-B

### Checkliste Lektion 1

- [ ] HelloWorld.java erfolgreich ausgefuehrt
- [ ] Text in HelloWorld.java geaendert und neu ausgefuehrt
- [ ] MeinStart.java erstellt mit 3 Ausgabezeilen
- [ ] Verstanden was ein Programm ist
- [ ] Terminal-Befehle javac und java verstanden

---

## Lektion 2: System.out.println() - Ausgabe meistern

### Konzept

`System.out.println()` ist DER wichtigste Befehl am Anfang. Er gibt Text auf dem Bildschirm aus. `println` steht fuer "print line" - also "drucke eine Zeile".

**Minecraft-Bezug:**
Stell dir vor, du baust ein Info-Schild in Minecraft. Jedes `println` ist eine neue Zeile auf dem Schild.

### Varianten

```java
// Mit Zeilenumbruch am Ende (println)
System.out.println("Hallo");    // Hallo
System.out.println("Welt");     // Welt  (neue Zeile)

// Ohne Zeilenumbruch (print)
System.out.print("Hallo ");     // Hallo Welt (gleiche Zeile)
System.out.print("Welt");

// Leere Zeile
System.out.println();           // Nur ein Zeilenumbruch
```

### Sonderzeichen

```java
System.out.println("Zeile 1\nZeile 2");   // \n = neue Zeile
System.out.println("Tab\thier");           // \t = Tabulator
System.out.println("Er sagte \"Hallo\"");  // \" = Anfuehrungszeichen im Text
```

### Aufgabe 2.1: Minecraft-Steckbrief

**Ziel:** Erstelle `src/Steckbrief.java` und gib einen Minecraft-Steckbrief aus.

**Erwartete Ausgabe:**
```
=============================
    MINECRAFT STECKBRIEF
=============================
Spielername: [dein Name]
Lieblings-Mob: [dein Mob]
Lieblings-Block: [dein Block]
Spielstunden: [eine Zahl]
=============================
```

**Hinweise:**
- Nutze `System.out.println()` fuer jede Zeile
- Die `===` Linie kannst du einfach als Text schreiben

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/Steckbrief.java`
3. Starten: `java -cp src Steckbrief`

### Aufgabe 2.2: ASCII-Art

**Ziel:** Erstelle `src/AsciiArt.java` und zeichne ein Creeper-Gesicht mit Zeichen.

**Erwartete Ausgabe (ungefaehr):**
```
 ########
 #  ##  #
 #  ##  #
 ## ## ##
  # ## #
  ######
  #    #
  # ## #
  ######
```

**Hinweis:** Jede Zeile ist ein eigenes `System.out.println()`.

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/AsciiArt.java`
3. Starten: `java -cp src AsciiArt`

### Aufgabe 2.3: print vs println

**Ziel:** Erstelle `src/PrintTest.java`. Experimentiere mit `print` und `println`.

**Schreibe Code der diese Ausgabe erzeugt:**
```
Hallo Welt
HalloWelt
Hallo     Welt
```

**Hinweise:**
- Zeile 1: Zwei separate `println` oder ein `println` mit Leerzeichen
- Zeile 2: Zwei `print` ohne Leerzeichen, dann ein `println()`
- Zeile 3: Nutze `\t` fuer den Tabulator

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/PrintTest.java`
3. Starten: `java -cp src PrintTest`

### Quiz Lektion 2

**Frage 1:** Was ist der Unterschied zwischen `print` und `println`?
- A) Kein Unterschied
- B) println macht eine neue Zeile, print nicht
- C) print ist schneller
- D) println kann nur Zahlen drucken

**Frage 2:** Was gibt `System.out.println("Hallo\nWelt");` aus?
- A) Hallo\nWelt
- B) HalloWelt
- C) Hallo (neue Zeile) Welt
- D) Einen Fehler

**Frage 3:** Wie schreibt man Anfuehrungszeichen IN einem Text?
- A) "Er sagte "Hallo""
- B) "Er sagte \"Hallo\""
- C) "Er sagte 'Hallo'"
- D) Geht nicht

**Frage 4:** Was passiert bei `System.out.println();` ohne Text?
- A) Fehler
- B) Gibt "null" aus
- C) Nur eine leere Zeile
- D) Nichts passiert

**Antworten:** 1-B, 2-C, 3-B, 4-C

### Checkliste Lektion 2

- [ ] Steckbrief.java erstellt und laeuft
- [ ] AsciiArt.java erstellt mit Creeper-Gesicht
- [ ] PrintTest.java: print vs println verstanden
- [ ] \n und \t verstanden
- [ ] Anfuehrungszeichen escapen (\" ) verstanden

---

## Lektion 3: Variablen - Daten speichern

### Konzept

Eine **Variable** ist wie eine Box mit einem Namen. Du legst etwas rein und kannst es spaeter wieder rausholen.

**Minecraft-Bezug:**
- `int health = 20;` ist wie die Herzen-Anzeige: 20 Lebenspunkte
- `String name = "Steve";` ist wie dein Spielername
- `double speed = 4.317;` ist wie deine Laufgeschwindigkeit

### Die wichtigsten Typen

```java
int alter = 12;              // Ganze Zahlen (integer)
double preis = 9.99;         // Kommazahlen (mit Punkt!)
String name = "Steve";       // Text (immer in "...")
boolean lebt = true;         // Wahr oder Falsch (true/false)
```

### Variablen verwenden

```java
int leben = 20;
String spieler = "Steve";

System.out.println("Spieler: " + spieler);
System.out.println("Leben: " + leben);

// Wert aendern
leben = 15;
System.out.println("Nach Schaden: " + leben);
```

### Aufgabe 3.1: Spieler-Profil

**Ziel:** Erstelle `src/SpielerProfil.java` mit Variablen fuer einen Minecraft-Spieler.

**Erstelle diese Variablen:**
- `name` (String) - Dein Spielername
- `level` (int) - Dein Level
- `leben` (int) - Lebenspunkte
- `hunger` (int) - Hungerpunkte
- `erfahrung` (double) - XP als Kommazahl
- `istAmLeben` (boolean) - true

**Erwartete Ausgabe:**
```
=== SPIELER-PROFIL ===
Name: [dein Name]
Level: [dein Level]
Leben: [deine HP]
Hunger: [dein Hunger]
Erfahrung: [deine XP]
Am Leben: true
```

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/SpielerProfil.java`
3. Starten: `java -cp src SpielerProfil`

### Aufgabe 3.2: Variablen aendern

**Ziel:** Erstelle `src/SchadenTest.java`. Ein Spieler nimmt Schaden und die Werte aendern sich.

**Was passieren soll:**
1. Erstelle Variable `leben` mit Wert 20
2. Gib aus: "Leben vorher: 20"
3. Ziehe 7 ab (Zombie-Schaden): `leben = leben - 7;`
4. Gib aus: "Nach Zombie-Angriff: 13"
5. Ziehe nochmal 5 ab (Fall-Schaden): `leben = leben - 5;`
6. Gib aus: "Nach Fall: 8"

**Erwartete Ausgabe:**
```
=== SCHADENTEST ===
Leben vorher: 20
Zombie greift an! -7 Schaden
Leben jetzt: 13
Du faellst! -5 Schaden
Leben jetzt: 8
```

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/SchadenTest.java`
3. Starten: `java -cp src SchadenTest`

### Aufgabe 3.3: Text zusammenbauen

**Ziel:** Erstelle `src/ItemInfo.java`. Baue Saetze mit Variablen zusammen.

**Erstelle diese Variablen:**
- `item` (String) = "Diamant-Schwert"
- `schaden` (int) = 7
- `haltbarkeit` (int) = 1561
- `verzaubert` (boolean) = true

**Erwartete Ausgabe:**
```
Item: Diamant-Schwert
Schaden: 7 Punkte
Haltbarkeit: 1561 Benutzungen
Verzaubert: true
Das Diamant-Schwert macht 7 Schaden und hat 1561 Haltbarkeit.
```

**Hinweis:** Die letzte Zeile baust du mit `+` zusammen:
`System.out.println("Das " + item + " macht " + schaden + " Schaden...");`

**So fuehrst du es aus:**
1. Oeffne das Terminal (Strg + OE)
2. Kompilieren: `javac src/ItemInfo.java`
3. Starten: `java -cp src ItemInfo`

### Quiz Lektion 3

**Frage 1:** Welcher Typ speichert ganze Zahlen?
- A) String
- B) double
- C) int
- D) boolean

**Frage 2:** Was passiert bei `int x = 10; x = x + 5;`?
- A) x ist 10
- B) x ist 15
- C) Fehler
- D) x ist 105

**Frage 3:** Welcher Typ speichert Text?
- A) int
- B) text
- C) String
- D) char

**Frage 4:** Was gibt `System.out.println("HP: " + 20);` aus?
- A) HP: + 20
- B) HP: 20
- C) Fehler
- D) 20

**Antworten:** 1-C, 2-B, 3-C, 4-B

### Checkliste Lektion 3

- [ ] SpielerProfil.java mit 6 Variablen erstellt
- [ ] SchadenTest.java mit Wertaenderungen laeuft
- [ ] ItemInfo.java mit Text-Zusammenbau laeuft
- [ ] Typen int, double, String, boolean verstanden
- [ ] Variablen aendern mit = verstanden
- [ ] Text-Verkettung mit + verstanden

---

## Lektion 4: Rechnen mit Java

### Konzept

Java kann rechnen wie ein Taschenrechner. Du nutzt die gleichen Zeichen wie in Mathe.

**Minecraft-Bezug:**
Das Spiel rechnet staendig! Schaden berechnen, Erfahrungspunkte addieren, Crafting-Mengen pruefen.

### Rechenzeichen (Operatoren)

```java
int a = 10;
int b = 3;

System.out.println(a + b);   // 13  (Addition)
System.out.println(a - b);   // 7   (Subtraktion)
System.out.println(a * b);   // 30  (Multiplikation)
System.out.println(a / b);   // 3   (Division - ACHTUNG: ohne Komma bei int!)
System.out.println(a % b);   // 1   (Rest/Modulo - was uebrig bleibt)
```

**Wichtig bei Division:**
```java
int ergebnis = 10 / 3;        // = 3 (nicht 3.33! Weil int)
double ergebnis2 = 10.0 / 3;  // = 3.333... (mit double)
```

### Aufgabe 4.1: Schadensrechner

**Ziel:** Erstelle `src/Schadensrechner.java`. Berechne den Schaden eines Angriffs.

**Variablen:**
- `basisSchaden` (int) = 7 (Diamant-Schwert)
- `staerkeBonus` (int) = 3 (Staerke-Effekt)
- `ruestung` (int) = 5 (Gegner-Ruestung)

**Berechne:**
- `gesamtSchaden` = basisSchaden + staerkeBonus
- `effektivSchaden` = gesamtSchaden - ruestung

**Erwartete Ausgabe:**
```
=== SCHADENSRECHNER ===
Basis-Schaden: 7
Staerke-Bonus: +3
Gesamt-Schaden: 10
Gegner-Ruestung: -5
Effektiver Schaden: 5
```

**Ausfuehren:** `javac src/Schadensrechner.java` → `java -cp src Schadensrechner`

### Aufgabe 4.2: XP-Rechner

**Ziel:** Erstelle `src/XPRechner.java`. Berechne wie viel XP du fuer verschiedene Aktionen bekommst.

**Variablen:**
- `zombieXP` (int) = 5
- `skelettXP` (int) = 5
- `creeperXP` (int) = 5
- `anzahlZombies` (int) = 10
- `anzahlSkelette` (int) = 7
- `anzahlCreepers` (int) = 3

**Berechne:**
- XP von Zombies = zombieXP * anzahlZombies
- XP von Skeletten = skelettXP * anzahlSkelette
- XP von Creepers = creeperXP * anzahlCreepers
- Gesamt-XP = alle zusammen

**Erwartete Ausgabe:**
```
=== XP-RECHNER ===
Zombies getoetet: 10 (je 5 XP) = 50 XP
Skelette getoetet: 7 (je 5 XP) = 35 XP
Creeper getoetet: 3 (je 5 XP) = 15 XP
-------------------------------
Gesamt-XP: 100 XP
```

**Ausfuehren:** `javac src/XPRechner.java` → `java -cp src XPRechner`

### Aufgabe 4.3: Crafting-Rechner

**Ziel:** Erstelle `src/CraftingRechner.java`. Berechne wie viele Items du craften kannst.

**Szenario:** Du hast 23 Eisenbarren. Ein Eisenschwert braucht 2 Barren.

**Berechne:**
- `anzahlSchwerter` = eisenBarren / 2 (Division)
- `restBarren` = eisenBarren % 2 (Modulo - der Rest)

**Erwartete Ausgabe:**
```
=== CRAFTING-RECHNER ===
Eisenbarren vorhanden: 23
Barren pro Schwert: 2
---
Du kannst 11 Schwerter craften!
Uebrige Barren: 1
```

**Ausfuehren:** `javac src/CraftingRechner.java` → `java -cp src CraftingRechner`

### Quiz Lektion 4

**Frage 1:** Was ergibt `10 / 3` bei int?
- A) 3.33
- B) 3
- C) 4
- D) 0

**Frage 2:** Was macht der % Operator?
- A) Prozent berechnen
- B) Division
- C) Rest einer Division
- D) Multiplikation

**Frage 3:** Was ergibt `5 + 3 * 2`?
- A) 16
- B) 11
- C) 13
- D) 10

**Frage 4:** Wie bekommt man bei Division ein Komma-Ergebnis?
- A) int / int
- B) double / int oder int / double
- C) Geht nicht in Java
- D) Mit dem % Zeichen

**Antworten:** 1-B, 2-C, 3-B, 4-B

### Checkliste Lektion 4

- [ ] Schadensrechner.java laeuft korrekt
- [ ] XPRechner.java laeuft korrekt
- [ ] CraftingRechner.java mit Division und Modulo laeuft
- [ ] +, -, *, / verstanden
- [ ] Modulo (%) verstanden
- [ ] int-Division vs double-Division verstanden

---

## Lektion 5: if/else - Entscheidungen treffen

### Konzept

Mit `if/else` kann dein Programm **Entscheidungen** treffen. "WENN etwas wahr ist, DANN tue dies, SONST tue das."

**Minecraft-Bezug:**
- WENN Leben < 5 DANN zeige Warneffekt
- WENN Hunger = 0 DANN verliere Leben
- WENN Block = Diamanterz DANN droppe Diamant

### Syntax

```java
int leben = 8;

if (leben > 10) {
    System.out.println("Du bist gesund!");
} else if (leben > 5) {
    System.out.println("Vorsicht, Leben wird knapp!");
} else {
    System.out.println("GEFAHR! Fast tot!");
}
```

### Vergleichszeichen

```java
// == gleich (ACHTUNG: doppeltes Gleichzeichen!)
// != ungleich
// >  groesser als
// <  kleiner als
// >= groesser oder gleich
// <= kleiner oder gleich
```

### Aufgabe 5.1: Lebensanzeige

**Ziel:** Erstelle `src/Lebensanzeige.java`. Zeige verschiedene Nachrichten je nach Lebenspunkten.

**Erstelle Variable:** `int leben = 15;`

**Regeln:**
- leben > 15: "Volle Gesundheit! Du bist unaufhaltbar!"
- leben > 10: "Guter Zustand. Weitermachen!"
- leben > 5: "Vorsicht! Iss etwas oder heile dich!"
- leben > 0: "KRITISCH! Du stirbst gleich!"
- leben <= 0: "Game Over! Du bist gestorben."

**Teste mit verschiedenen Werten!** Aendere `leben` zu 20, 12, 6, 3, 0 und pruefe ob die richtige Nachricht kommt.

**Erwartete Ausgabe (bei leben = 15):**
```
=== LEBENSANZEIGE ===
Leben: 15
Status: Guter Zustand. Weitermachen!
```

**Ausfuehren:** `javac src/Lebensanzeige.java` → `java -cp src Lebensanzeige`

### Aufgabe 5.2: Mob-Erkennung

**Ziel:** Erstelle `src/MobErkennung.java`. Bestimme den Mob-Typ anhand seiner Eigenschaften.

**Variablen:**
- `int leben` = 20
- `boolean explodiert` = false
- `boolean hatBogen` = true

**Regeln:**
- Wenn `explodiert` == true: "Das ist ein Creeper!"
- Wenn `hatBogen` == true: "Das ist ein Skelett!"
- Wenn `leben` > 30: "Das ist ein Eisengolem!"
- Sonst: "Das ist ein Zombie!"

**Teste verschiedene Kombinationen!**

**Ausfuehren:** `javac src/MobErkennung.java` → `java -cp src MobErkennung`

### Aufgabe 5.3: Tageszeit-System

**Ziel:** Erstelle `src/Tageszeit.java`. Bestimme was in Minecraft passiert basierend auf der Uhrzeit (Ticks).

**Variable:** `int ticks = 6000;`

**Regeln (Minecraft-Tageszeiten):**
- 0-6000: "Morgen - Die Sonne geht auf. Mobs verschwinden."
- 6001-12000: "Mittag - Bestes Licht zum Bauen!"
- 12001-13000: "Abend - Geh nach Hause! Bald wird es dunkel."
- 13001-18000: "Nacht - Monster spawnen! Bleib im Haus!"
- 18001-24000: "Spaete Nacht - Halte durch, bald wird es hell."

**Erwartete Ausgabe (bei ticks = 6000):**
```
=== MINECRAFT TAGESZEIT ===
Ticks: 6000
Tageszeit: Morgen - Die Sonne geht auf. Mobs verschwinden.
```

**Ausfuehren:** `javac src/Tageszeit.java` → `java -cp src Tageszeit`

### Quiz Lektion 5

**Frage 1:** Was ist der Unterschied zwischen `=` und `==`?
- A) Kein Unterschied
- B) = setzt einen Wert, == vergleicht
- C) == setzt einen Wert, = vergleicht
- D) Beide vergleichen

**Frage 2:** Was gibt dieser Code aus wenn x = 7?
```java
if (x > 10) { println("A"); }
else if (x > 5) { println("B"); }
else { println("C"); }
```
- A) A
- B) B
- C) C
- D) A und B

**Frage 3:** Was bedeutet `!=`?
- A) Gleich
- B) Nicht gleich
- C) Ausrufezeichen
- D) Fehler

**Frage 4:** Kann man if ohne else benutzen?
- A) Nein, else ist Pflicht
- B) Ja, else ist optional
- C) Nur mit else if
- D) Nur in Schleifen

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 5

- [ ] Lebensanzeige.java mit mehreren Bedingungen laeuft
- [ ] MobErkennung.java mit boolean-Abfragen laeuft
- [ ] Tageszeit.java mit Zahlen-Bereichen laeuft
- [ ] if, else if, else verstanden
- [ ] Vergleichszeichen (==, !=, >, <, >=, <=) verstanden
- [ ] Mit verschiedenen Werten getestet

---

## Lektion 6: for-Schleifen - Wiederholungen

### Konzept

Eine **Schleife** wiederholt Code mehrfach. Statt 10 mal das gleiche zu schreiben, sagst du dem Computer: "Mach das 10 mal!"

**Minecraft-Bezug:**
- for-Schleife = 10 Bloecke hintereinander platzieren
- Der Computer zaehlt automatisch mit

### Syntax

```java
// zaehlt von 0 bis 4 (5 mal)
for (int i = 0; i < 5; i++) {
    System.out.println("Durchgang: " + i);
}
```

**Die 3 Teile:**
1. `int i = 0` - Start: Zaehler beginnt bei 0
2. `i < 5` - Bedingung: Solange i kleiner als 5
3. `i++` - Schritt: Nach jedem Durchgang i um 1 erhoehen

### Aufgabe 6.1: Block-Platzierer

**Ziel:** Erstelle `src/BlockPlatzierer.java`. Simuliere das Platzieren von Bloecken.

**Schreibe eine Schleife die 10 Bloecke platziert:**

**Erwartete Ausgabe:**
```
=== BLOCK-PLATZIERER ===
Block 1 platziert bei Position X:0
Block 2 platziert bei Position X:1
Block 3 platziert bei Position X:2
Block 4 platziert bei Position X:3
Block 5 platziert bei Position X:4
Block 6 platziert bei Position X:5
Block 7 platziert bei Position X:6
Block 8 platziert bei Position X:7
Block 9 platziert bei Position X:8
Block 10 platziert bei Position X:9
Fertig! 10 Bloecke platziert.
```

**Hinweis:** Die Blocknummer ist `i + 1` (weil i bei 0 startet).

**Ausfuehren:** `javac src/BlockPlatzierer.java` → `java -cp src BlockPlatzierer`

### Aufgabe 6.2: Countdown

**Ziel:** Erstelle `src/Countdown.java`. Zaehle von 10 rueckwaerts bis 0.

**Hinweis:** Du kannst auch rueckwaerts zaehlen:
```java
for (int i = 10; i >= 0; i--) {
```

**Erwartete Ausgabe:**
```
=== CREEPER COUNTDOWN ===
10...
9...
8...
7...
6...
5...
4...
3...
2...
1...
0... BOOM! Der Creeper explodiert!
```

**Tipp:** Fuer die letzte Zeile (bei i == 0) brauchst du ein `if` in der Schleife!

**Ausfuehren:** `javac src/Countdown.java` → `java -cp src Countdown`

### Aufgabe 6.3: Multiplikationstabelle

**Ziel:** Erstelle `src/MultiTabelle.java`. Zeige die Multiplikationstabelle fuer eine Zahl.

**Variable:** `int zahl = 7;`

**Erwartete Ausgabe:**
```
=== MULTIPLIKATIONSTABELLE FUER 7 ===
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

**Ausfuehren:** `javac src/MultiTabelle.java` → `java -cp src MultiTabelle`

### Quiz Lektion 6

**Frage 1:** Wie oft laeuft `for (int i = 0; i < 3; i++)`?
- A) 2 mal
- B) 3 mal
- C) 4 mal
- D) Unendlich

**Frage 2:** Was bedeutet `i++`?
- A) i wird verdoppelt
- B) i wird um 1 erhoeht
- C) i wird zurueckgesetzt
- D) i wird geloescht

**Frage 3:** Was ist der Wert von i beim ERSTEN Durchgang von `for (int i = 0; i < 5; i++)`?
- A) 1
- B) 5
- C) 0
- D) -1

**Frage 4:** Kann man in einer Schleife ein if benutzen?
- A) Nein
- B) Ja
- C) Nur bei while-Schleifen
- D) Nur beim letzten Durchgang

**Antworten:** 1-B, 2-B, 3-C, 4-B

### Checkliste Lektion 6

- [ ] BlockPlatzierer.java mit Vorwaerts-Schleife laeuft
- [ ] Countdown.java mit Rueckwaerts-Schleife laeuft
- [ ] MultiTabelle.java mit Berechnung in Schleife laeuft
- [ ] for-Schleifen-Syntax (Start; Bedingung; Schritt) verstanden
- [ ] i++ und i-- verstanden
- [ ] if innerhalb einer Schleife benutzt

---

## Lektion 7: Arrays - Listen von Daten

### Konzept

Ein **Array** ist wie eine Reihe von Kisten nebeneinander. Jede Kiste hat eine Nummer (Index) und einen Inhalt.

**Minecraft-Bezug:**
Deine Hotbar hat 9 Slots (0-8). Das ist ein Array!
- Slot 0: Schwert
- Slot 1: Bogen
- Slot 2: Schaufel
- ...

### Syntax

```java
// Array erstellen mit Werten
String[] hotbar = {"Schwert", "Bogen", "Schaufel", "Fackel", "Steak"};

// Zugriff ueber Index (ACHTUNG: beginnt bei 0!)
System.out.println(hotbar[0]);  // Schwert
System.out.println(hotbar[1]);  // Bogen

// Laenge
System.out.println(hotbar.length);  // 5

// Wert aendern
hotbar[2] = "Spitzhacke";

// Array mit Zahlen
int[] damage = {7, 5, 4, 0, 0};
```

### Array mit Schleife durchlaufen

```java
String[] items = {"Schwert", "Bogen", "Schaufel"};

for (int i = 0; i < items.length; i++) {
    System.out.println("Slot " + i + ": " + items[i]);
}
```

### Aufgabe 7.1: Hotbar-Anzeige

**Ziel:** Erstelle `src/Hotbar.java`. Zeige eine Minecraft-Hotbar an.

**Erstelle ein String-Array** mit 9 Items (wie in Minecraft):

**Erwartete Ausgabe:**
```
=== MINECRAFT HOTBAR ===
[1] Diamant-Schwert
[2] Bogen
[3] Eisenspitzhacke
[4] Steinschaufel
[5] Fackel
[6] Steak
[7] Goldapfel
[8] Schild
[9] Enderperle
Aktives Item: Diamant-Schwert
```

**Hinweis:** Nutze eine for-Schleife! Die Anzeige-Nummer ist `i + 1`.

**Ausfuehren:** `javac src/Hotbar.java` → `java -cp src Hotbar`

### Aufgabe 7.2: Mob-Spawner

**Ziel:** Erstelle `src/MobSpawner.java`. Verwalte verschiedene Mobs mit Arrays.

**Erstelle 2 Arrays:**
- `String[] mobNamen` mit 5 Mob-Namen
- `int[] mobLeben` mit den Lebenspunkten jedes Mobs

**Erwartete Ausgabe:**
```
=== MOB-SPAWNER ===
Mob 1: Zombie (HP: 20)
Mob 2: Skelett (HP: 20)
Mob 3: Creeper (HP: 20)
Mob 4: Spinne (HP: 16)
Mob 5: Enderman (HP: 40)
---
Staerkster Mob: Enderman mit 40 HP
```

**Hinweis fuer den staerksten Mob:**
```java
int maxHP = 0;
String staerkster = "";
for (int i = 0; i < mobLeben.length; i++) {
    if (mobLeben[i] > maxHP) {
        maxHP = mobLeben[i];
        staerkster = mobNamen[i];
    }
}
```

**Ausfuehren:** `javac src/MobSpawner.java` → `java -cp src MobSpawner`

### Aufgabe 7.3: Inventar-Suche

**Ziel:** Erstelle `src/InventarSuche.java`. Suche nach einem bestimmten Item im Inventar.

**Erstelle ein Array** mit 8 Items. Dann suche nach einem bestimmten Item.

**Variable:** `String gesucht = "Diamant";`

**Erwartete Ausgabe (wenn gefunden):**
```
=== INVENTAR-SUCHE ===
Suche nach: Diamant
Slot 1: Holz - nein
Slot 2: Stein - nein
Slot 3: Eisen - nein
Slot 4: Diamant - GEFUNDEN in Slot 4!
```

**Erwartete Ausgabe (wenn nicht gefunden):**
```
Suche nach: Smaragd
... (alle Slots durchsuchen)
Item nicht gefunden!
```

**Hinweis:** Vergleiche Strings mit `.equals()`:
```java
if (items[i].equals(gesucht)) {
```

**Ausfuehren:** `javac src/InventarSuche.java` → `java -cp src InventarSuche`

### Quiz Lektion 7

**Frage 1:** Welchen Index hat das ERSTE Element eines Arrays?
- A) 1
- B) 0
- C) -1
- D) Es hat keinen Index

**Frage 2:** Was passiert bei `items[10]` wenn das Array nur 5 Elemente hat?
- A) Gibt null zurueck
- B) Gibt 0 zurueck
- C) ArrayIndexOutOfBoundsException (Fehler!)
- D) Erstellt automatisch mehr Platz

**Frage 3:** Wie bekommt man die Laenge eines Arrays `items`?
- A) items.size()
- B) items.length
- C) items.count()
- D) length(items)

**Frage 4:** Wie vergleicht man Strings in Java?
- A) name == "Steve"
- B) name.equals("Steve")
- C) name = "Steve"
- D) Beides A und B funktioniert gleich

**Antworten:** 1-B, 2-C, 3-B, 4-B

### Checkliste Lektion 7

- [ ] Hotbar.java mit String-Array und Schleife laeuft
- [ ] MobSpawner.java mit 2 parallelen Arrays laeuft
- [ ] InventarSuche.java mit Suchfunktion laeuft
- [ ] Array erstellen und Zugriff ueber Index verstanden
- [ ] Array.length verstanden
- [ ] Array mit for-Schleife durchlaufen koennen
- [ ] String-Vergleich mit .equals() verstanden

---

## Lektion 8: Funktionen (Methoden) - Code organisieren

### Konzept

Eine **Funktion** (in Java "Methode" genannt) ist ein Stueck Code mit einem Namen. Du kannst sie immer wieder aufrufen, ohne den Code neu zu schreiben.

**Minecraft-Bezug:**
- Funktion `platziereBlock()` - wird jedes Mal aufgerufen wenn du klickst
- Funktion `berechneSchaden(waffe, gegner)` - berechnet den Schaden
- Du schreibst den Code einmal, nutzt ihn beliebig oft!

### Syntax

```java
public class MeinProgramm {

    // Funktion OHNE Rueckgabe
    static void begruessung(String name) {
        System.out.println("Hallo, " + name + "!");
    }

    // Funktion MIT Rueckgabe
    static int addiere(int a, int b) {
        return a + b;
    }

    // Funktion OHNE Parameter
    static void zeigeTrennlinie() {
        System.out.println("========================");
    }

    public static void main(String[] args) {
        begruessung("Steve");        // Hallo, Steve!
        begruessung("Alex");         // Hallo, Alex!

        int summe = addiere(5, 3);   // summe = 8
        System.out.println(summe);

        zeigeTrennlinie();           // ========================
    }
}
```

### Wichtige Woerter

| Wort | Bedeutung |
|------|-----------|
| `static` | Gehoert zur Klasse (brauchst du in Phase 1 immer) |
| `void` | Gibt NICHTS zurueck |
| `int` / `String` / etc | Gibt einen Wert dieses Typs zurueck |
| `return` | Gibt den Wert zurueck und beendet die Funktion |
| Parameter | Werte die du der Funktion uebergibst |

### Aufgabe 8.1: Kampf-Funktionen

**Ziel:** Erstelle `src/KampfFunktionen.java` mit mehreren Funktionen.

**Erstelle diese Funktionen:**
1. `static void zeigeTrennlinie()` - Gibt eine Linie aus
2. `static void zeigeSpieler(String name, int hp)` - Zeigt Spieler-Info
3. `static int berechneSchaden(int basisSchaden, int bonus)` - Gibt Schaden zurueck
4. `static boolean istAmLeben(int hp)` - Gibt true/false zurueck

**Rufe alle Funktionen in main() auf.**

**Erwartete Ausgabe:**
```
=============================
Spieler: Held (HP: 100)
Spieler: Zombie (HP: 50)
=============================
Angriff! Schaden: 12
Held am Leben? true
Zombie am Leben? true
```

**Ausfuehren:** `javac src/KampfFunktionen.java` → `java -cp src KampfFunktionen`

### Aufgabe 8.2: Werkzeug-Rechner

**Ziel:** Erstelle `src/WerkzeugRechner.java`. Berechne die Effizienz verschiedener Werkzeuge.

**Erstelle diese Funktionen:**
1. `static double berechneAbbauzeit(int haerte, double werkzeugSpeed)` - Gibt Abbauzeit in Sekunden zurueck
2. `static String bestesWerkzeug(double zeitHolz, double zeitStein, double zeitEisen)` - Gibt den Namen des schnellsten zurueck
3. `static void zeigeErgebnis(String block, String werkzeug, double zeit)` - Gibt das Ergebnis formatiert aus

**Erwartete Ausgabe:**
```
=== WERKZEUG-RECHNER ===
Block: Stein
  Holzspitzhacke: 1.5 Sekunden
  Steinspitzhacke: 0.75 Sekunden
  Eisenspitzhacke: 0.5 Sekunden
Bestes Werkzeug: Eisenspitzhacke
```

**Ausfuehren:** `javac src/WerkzeugRechner.java` → `java -cp src WerkzeugRechner`

### Aufgabe 8.3: Mini-Spielsimulator

**Ziel:** Erstelle `src/MiniSpiel.java`. Kombiniere alles was du gelernt hast!

**Erstelle ein kleines Kampfspiel mit Funktionen:**
1. `static void zeigeIntro()` - Zeigt das Spielintro
2. `static int wuerfeln()` - Gibt eine zufaellige Zahl 1-6 zurueck (mit `(int)(Math.random() * 6) + 1`)
3. `static void kampfRunde(String spieler1, String spieler2)` - Beide wuerfeln, hoeherer Wurf gewinnt
4. `static void zeigeGewinner(String name, int punkte)` - Zeigt den Gewinner

**In main():** Spiele 5 Runden und zeige den Gesamtgewinner.

**Erwartete Ausgabe (ungefaehr):**
```
=== MINI-KAMPFSPIEL ===
Steve vs Zombie - 5 Runden!

Runde 1: Steve wuerfelt 4, Zombie wuerfelt 2 -> Steve gewinnt!
Runde 2: Steve wuerfelt 1, Zombie wuerfelt 5 -> Zombie gewinnt!
Runde 3: Steve wuerfelt 6, Zombie wuerfelt 6 -> Unentschieden!
Runde 4: Steve wuerfelt 3, Zombie wuerfelt 1 -> Steve gewinnt!
Runde 5: Steve wuerfelt 5, Zombie wuerfelt 4 -> Steve gewinnt!

=== ERGEBNIS ===
Steve: 3 Siege
Zombie: 1 Siege
Gewinner: Steve!
```

**Ausfuehren:** `javac src/MiniSpiel.java` → `java -cp src MiniSpiel`

### Quiz Lektion 8

**Frage 1:** Was bedeutet `void` bei einer Funktion?
- A) Die Funktion ist leer
- B) Die Funktion gibt nichts zurueck
- C) Die Funktion ist kaputt
- D) Die Funktion hat keine Parameter

**Frage 2:** Was macht `return`?
- A) Beendet das ganze Programm
- B) Gibt einen Wert zurueck und beendet die Funktion
- C) Druckt etwas auf dem Bildschirm
- D) Startet die Funktion neu

**Frage 3:** Was ist ein Parameter?
- A) Der Name der Funktion
- B) Ein Wert den du der Funktion uebergibst
- C) Das Ergebnis der Funktion
- D) Eine Variable in main()

**Frage 4:** Kann eine Funktion eine andere Funktion aufrufen?
- A) Nein, nur main() kann Funktionen aufrufen
- B) Ja
- C) Nur wenn sie void ist
- D) Nur mit return

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 8

- [ ] KampfFunktionen.java mit 4 verschiedenen Funktionen laeuft
- [ ] WerkzeugRechner.java mit Rueckgabewerten laeuft
- [ ] MiniSpiel.java das alles kombiniert laeuft
- [ ] void-Funktionen verstanden (keine Rueckgabe)
- [ ] Funktionen mit Rueckgabe (return) verstanden
- [ ] Parameter verstanden
- [ ] Funktionen in main() aufrufen koennen

---

## Phase 1 abgeschlossen?

Wenn du alle 8 Lektionen durchgearbeitet hast:

1. Pruefe alle Checklisten - sind alle Punkte abgehakt?
2. Oeffne das ABSCHLUSSPROJEKT.md
3. Baue den **Minecraft Character Generator**!
4. Zeig deinem Tutor das Ergebnis fuer ein Code-Review

**Nach dem Abschlussprojekt bist du bereit fuer Phase 2: OOP!**
