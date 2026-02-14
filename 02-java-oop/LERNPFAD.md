# Phase 2: OOP (Objekt-Orientierte Programmierung) - Vollstaendiger Lernpfad
## 8 Lektionen mit Minecraft-Beispielen

**Dauer:** 4-6 Wochen (ca. 1 Stunde pro Tag, 4-5x pro Woche)
**Voraussetzungen:** Phase 1 abgeschlossen (Variablen, if/else, Schleifen, Arrays, Funktionen)
**Ziel:** Klassen, Objekte und Vererbung verstehen - DAS Fundament fuer Minecraft-Mods!

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

**Punkte pro Lektion:** 150 XP (schwieriger als Phase 1!)
**Abschlussprojekt:** 750 XP

---

## Lektion 1: Klassen und Objekte verstehen

### Konzept

Eine **Klasse** ist wie eine Blaupause/Bauplan. Ein **Objekt** ist ein konkretes Ding, das nach diesem Bauplan gebaut wurde.

**Minecraft-Bezug:**
- Klasse `Zombie` = Der Bauplan: "Jeder Zombie hat 20 HP, kann angreifen, laesst Items fallen"
- Objekt `zombie1` = Ein konkreter Zombie in deiner Welt bei Position X:100 Y:64 Z:200
- Objekt `zombie2` = Ein anderer Zombie an einer anderen Stelle

In Phase 1 hast du alles in EINER Datei mit Variablen gemacht:
```java
// Phase 1 - OHNE Klassen (umstaendlich bei vielen Zombies!)
int zombie1HP = 20;
int zombie1Damage = 5;
int zombie2HP = 20;
int zombie2Damage = 5;
// ... das wird schnell nervig!
```

Ab jetzt mit Klassen:
```java
// Phase 2 - MIT Klassen (sauber und flexibel!)
class Zombie {
    int hp = 20;
    int damage = 5;
}
Zombie z1 = new Zombie();
Zombie z2 = new Zombie();
```

### Code-Struktur einer Klasse

```java
public class Spieler {
    // Eigenschaften (was hat der Spieler?)
    String name;
    int leben;
    int level;

    // Methoden (was kann der Spieler tun?)
    void zeigeInfo() {
        System.out.println("Name: " + name);
        System.out.println("Leben: " + leben);
        System.out.println("Level: " + level);
    }
}
```

### Objekte erstellen

```java
// In einer separaten Datei oder in main():
Spieler s1 = new Spieler();  // Neues Objekt erstellen
s1.name = "Steve";           // Eigenschaft setzen
s1.leben = 20;
s1.level = 1;
s1.zeigeInfo();              // Methode aufrufen
```

### Aufgabe 1.1: Deine erste Klasse

**Ziel:** Erstelle zwei Dateien: `src/Spieler.java` und `src/SpielerTest.java`.

**Datei 1 - `Spieler.java`:**
Erstelle eine Klasse `Spieler` mit:
- Eigenschaften: `name` (String), `level` (int), `erfahrung` (int)
- Methode: `void zeigeInfo()` - gibt alle Infos aus

**Datei 2 - `SpielerTest.java`:**
Erstelle `main()` und:
1. Erstelle ein Spieler-Objekt mit `new`
2. Setze die Werte (name, level, erfahrung)
3. Rufe `zeigeInfo()` auf

**Erwartete Ausgabe:**
```
=== Spieler-Info ===
Name: Steve
Level: 5
Erfahrung: 1200
```

**Kompilieren:** `javac src/Spieler.java src/SpielerTest.java`
**Starten:** `java -cp src SpielerTest`

### Aufgabe 1.2: Mehrere Objekte

**Ziel:** Erweitere `SpielerTest.java` - erstelle 3 verschiedene Spieler-Objekte.

**Erstelle:**
- Spieler 1: "Steve", Level 5, 1200 XP
- Spieler 2: "Alex", Level 12, 5000 XP
- Spieler 3: Dein eigener Name und Werte

**Erwartete Ausgabe:**
```
=== Spieler-Info ===
Name: Steve
Level: 5
Erfahrung: 1200

=== Spieler-Info ===
Name: Alex
Level: 12
Erfahrung: 5000

=== Spieler-Info ===
Name: [Dein Name]
Level: [Dein Level]
Erfahrung: [Deine XP]
```

### Aufgabe 1.3: Mob-Klasse

**Ziel:** Erstelle `src/Mob.java` und `src/MobTest.java`.

**Klasse Mob:**
- Eigenschaften: `name` (String), `hp` (int), `damage` (int)
- Methode: `void zeigeInfo()` - gibt Mob-Infos aus
- Methode: `void angreifen()` - gibt "[name] greift an und macht [damage] Schaden!" aus

**In MobTest.java:** Erstelle 3 verschiedene Mobs (Zombie, Skelett, Creeper) und lass sie angreifen.

**Erwartete Ausgabe:**
```
=== Mobs ===
Zombie (HP: 20, Schaden: 5)
Skelett (HP: 20, Schaden: 4)
Creeper (HP: 20, Schaden: 25)

Zombie greift an und macht 5 Schaden!
Skelett greift an und macht 4 Schaden!
Creeper greift an und macht 25 Schaden!
```

### Quiz Lektion 1

**Frage 1:** Was ist der Unterschied zwischen Klasse und Objekt?
- A) Kein Unterschied
- B) Klasse = Bauplan, Objekt = konkretes Ding
- C) Objekt = Bauplan, Klasse = konkretes Ding
- D) Klasse ist schneller als Objekt

**Frage 2:** Wie erstellt man ein neues Objekt?
- A) Spieler s = Spieler();
- B) Spieler s = new Spieler();
- C) new Spieler s;
- D) create Spieler s;

**Frage 3:** Wie greift man auf eine Eigenschaft zu?
- A) Spieler->name
- B) Spieler.name
- C) s.name (wobei s ein Objekt ist)
- D) name.s

**Frage 4:** Kann man mehrere Objekte von einer Klasse erstellen?
- A) Nein, nur eins
- B) Maximal 10
- C) Ja, beliebig viele
- D) Nur in main()

**Antworten:** 1-B, 2-B, 3-C, 4-C

### Checkliste Lektion 1

- [ ] Spieler.java Klasse erstellt mit Eigenschaften und Methode
- [ ] SpielerTest.java mit Objekterstellung laeuft
- [ ] 3 verschiedene Spieler-Objekte erstellt
- [ ] Mob.java mit Eigenschaften und 2 Methoden erstellt
- [ ] Unterschied Klasse vs Objekt verstanden
- [ ] `new` Keyword verstanden

---

## Lektion 2: Konstruktoren

### Konzept

Ein **Konstruktor** ist eine spezielle Methode, die automatisch aufgerufen wird, wenn du ein Objekt mit `new` erstellst. Damit kannst du Werte direkt beim Erstellen setzen.

**Minecraft-Bezug:**
Wenn ein Zombie in Minecraft spawnt, bekommt er sofort 20 HP, eine Laufgeschwindigkeit, und einen Spawn-Punkt. Das macht der Konstruktor!

### Ohne vs Mit Konstruktor

```java
// OHNE Konstruktor (Phase 1 Stil - umstaendlich)
Spieler s = new Spieler();
s.name = "Steve";
s.leben = 20;
s.level = 1;

// MIT Konstruktor (Phase 2 - elegant!)
Spieler s = new Spieler("Steve", 20, 1);
```

### Syntax

```java
public class Spieler {
    String name;
    int leben;
    int level;

    // DAS ist der Konstruktor (gleicher Name wie die Klasse!)
    public Spieler(String name, int leben, int level) {
        this.name = name;    // this.name = die Eigenschaft
        this.leben = leben;  // name = der Parameter
        this.level = level;
    }
}
```

### Aufgabe 2.1: Spieler mit Konstruktor

**Ziel:** Ueberarbeite `src/Spieler.java` - fuege einen Konstruktor hinzu.

**Aendere die Klasse:**
- Fuege Konstruktor hinzu: `Spieler(String name, int leben, int level)`
- Nutze `this.name = name;` etc.

**Aendere SpielerTest.java:**
```java
Spieler s1 = new Spieler("Steve", 20, 5);
Spieler s2 = new Spieler("Alex", 20, 12);
s1.zeigeInfo();
s2.zeigeInfo();
```

**Erwartete Ausgabe:**
```
=== Spieler-Info ===
Name: Steve
Leben: 20
Level: 5

=== Spieler-Info ===
Name: Alex
Leben: 20
Level: 12
```

### Aufgabe 2.2: Mob mit Konstruktor

**Ziel:** Ueberarbeite `src/Mob.java` mit Konstruktor.

**Konstruktor:** `Mob(String name, int hp, int damage)`

**Erstelle in MobTest.java ein Array:**
```java
Mob[] mobs = new Mob[3];
mobs[0] = new Mob("Zombie", 20, 5);
mobs[1] = new Mob("Skelett", 20, 4);
mobs[2] = new Mob("Creeper", 20, 25);
```

**Zeige alle Mobs mit einer Schleife.**

**Erwartete Ausgabe:**
```
=== Mob-Arena ===
[1] Zombie (HP: 20, Schaden: 5)
[2] Skelett (HP: 20, Schaden: 4)
[3] Creeper (HP: 20, Schaden: 25)
```

### Aufgabe 2.3: Werkzeug-Klasse

**Ziel:** Erstelle `src/Werkzeug.java` und `src/WerkzeugTest.java`.

**Klasse Werkzeug:**
- Eigenschaften: `name` (String), `haltbarkeit` (int), `schaden` (int), `material` (String)
- Konstruktor mit allen 4 Werten
- Methode: `void zeigeInfo()`
- Methode: `void benutzen()` - reduziert haltbarkeit um 1 und zeigt neuen Wert

**Erstelle 3 Werkzeuge und benutze jedes 3 mal.**

**Erwartete Ausgabe (Ausschnitt):**
```
=== Werkzeuge ===
Holzschwert (Holz) - Schaden: 4, Haltbarkeit: 60
Steinschwert (Stein) - Schaden: 5, Haltbarkeit: 132
Eisenschwert (Eisen) - Schaden: 6, Haltbarkeit: 251

Holzschwert benutzt! Haltbarkeit: 59
Holzschwert benutzt! Haltbarkeit: 58
Holzschwert benutzt! Haltbarkeit: 57
```

### Quiz Lektion 2

**Frage 1:** Was ist ein Konstruktor?
- A) Eine normale Methode
- B) Eine spezielle Methode die beim Erstellen eines Objekts aufgerufen wird
- C) Ein Befehl zum Loeschen
- D) Eine Variable

**Frage 2:** Wie heisst der Konstruktor einer Klasse `Auto`?
- A) void Auto()
- B) new Auto()
- C) Auto()
- D) constructor()

**Frage 3:** Was bedeutet `this.name = name;`?
- A) name wird geloescht
- B) Die Eigenschaft (this.name) bekommt den Wert des Parameters (name)
- C) Beides ist gleich
- D) Fehler

**Frage 4:** Wann wird der Konstruktor aufgerufen?
- A) Manuell mit konstruktor()
- B) Automatisch bei `new Klasse()`
- C) Am Ende des Programms
- D) Nie automatisch

**Antworten:** 1-B, 2-C, 3-B, 4-B

### Checkliste Lektion 2

- [ ] Spieler.java mit Konstruktor ueberarbeitet
- [ ] Mob.java mit Konstruktor ueberarbeitet
- [ ] Werkzeug.java mit Konstruktor und 2 Methoden erstellt
- [ ] this-Keyword im Konstruktor verstanden
- [ ] Objekte mit Werten direkt erstellen koennen
- [ ] Mehrere Objekte in Array mit Schleife ausgeben

---

## Lektion 3: this-Keyword verstehen

### Konzept

`this` bedeutet "ich selbst" oder "mein eigenes Objekt". Es wird benutzt wenn der Parametername gleich heisst wie die Eigenschaft.

**Minecraft-Bezug:**
Wenn ein Zombie sagt "meine HP" meint er SEINE HP, nicht die vom Spieler. `this` ist das "meine/mein" in Java.

### Wann brauchst du this?

```java
public class Mob {
    String name;      // Eigenschaft
    int hp;           // Eigenschaft

    // Parameter "name" und Eigenschaft "name" heissen gleich!
    public Mob(String name, int hp) {
        this.name = name;  // this.name = Eigenschaft, name = Parameter
        this.hp = hp;
    }

    // In Methoden: this zeigt auf das aktuelle Objekt
    void zeigeInfo() {
        System.out.println(this.name + " hat " + this.hp + " HP");
        // this. kann hier auch weggelassen werden wenn eindeutig:
        // System.out.println(name + " hat " + hp + " HP");
    }
}
```

### Aufgabe 3.1: this im Konstruktor

**Ziel:** Erstelle `src/Block.java` und `src/BlockTest.java`.

**Klasse Block:**
- Eigenschaften: `name` (String), `haerte` (int), `werkzeug` (String), `abbaubar` (boolean)
- Konstruktor mit `this` fuer ALLE Eigenschaften
- Methode: `void zeigeInfo()`

**Erstelle Bloecke:** Stein (haerte:5, Spitzhacke, true), Bedrock (haerte:999, keins, false), Holz (haerte:2, Axt, true)

**Erwartete Ausgabe:**
```
=== Block-Infos ===
Block: Stein
  Haerte: 5
  Werkzeug: Spitzhacke
  Abbaubar: true

Block: Bedrock
  Haerte: 999
  Werkzeug: keins
  Abbaubar: false

Block: Holz
  Haerte: 2
  Werkzeug: Axt
  Abbaubar: true
```

### Aufgabe 3.2: this in Methoden

**Ziel:** Erstelle `src/Truhe.java` und `src/TruheTest.java`.

**Klasse Truhe:**
- Eigenschaften: `name` (String), `inhalt` (String), `istOffen` (boolean)
- Konstruktor
- Methode: `void oeffnen()` - setzt istOffen auf true, gibt Nachricht aus
- Methode: `void schliessen()` - setzt istOffen auf false
- Methode: `void zeigeStatus()` - zeigt ob offen/geschlossen und Inhalt

**In TruheTest.java:** Erstelle 2 Truhen, oeffne eine, schliesse die andere.

**Erwartete Ausgabe:**
```
Truhe "Schatzkiste" geoeffnet!
Truhe "Vorratskiste" geschlossen.

=== Truhen-Status ===
Schatzkiste: OFFEN - Inhalt: Diamanten
Vorratskiste: GESCHLOSSEN
```

### Aufgabe 3.3: Methoden die das eigene Objekt veraendern

**Ziel:** Erstelle `src/Ruestung.java` und `src/RuestungTest.java`.

**Klasse Ruestung:**
- Eigenschaften: `name` (String), `schutz` (int), `haltbarkeit` (int), `maxHaltbarkeit` (int)
- Konstruktor (maxHaltbarkeit = haltbarkeit am Anfang)
- Methode: `void nimmSchaden(int schaden)` - reduziert haltbarkeit
- Methode: `void reparieren()` - setzt haltbarkeit auf maxHaltbarkeit
- Methode: `boolean istKaputt()` - true wenn haltbarkeit <= 0
- Methode: `void zeigeInfo()` - zeigt alles

**In RuestungTest.java:** Erstelle Diamant-Brustplatte, nimm mehrmals Schaden, repariere.

**Erwartete Ausgabe:**
```
=== Ruestungstest ===
Diamant-Brustplatte (Schutz: 8, Haltbarkeit: 528/528)
Treffer! -50 Haltbarkeit
Diamant-Brustplatte (Schutz: 8, Haltbarkeit: 478/528)
Treffer! -100 Haltbarkeit
Diamant-Brustplatte (Schutz: 8, Haltbarkeit: 378/528)
Repariert!
Diamant-Brustplatte (Schutz: 8, Haltbarkeit: 528/528)
```

### Quiz Lektion 3

**Frage 1:** Was bedeutet `this` in einer Klasse?
- A) Die Klasse selbst
- B) Das aktuelle Objekt
- C) Der Konstruktor
- D) Die main-Methode

**Frage 2:** Wann ist `this` NOTWENDIG?
- A) Immer
- B) Wenn Parameter und Eigenschaft gleich heissen
- C) Nur in Konstruktoren
- D) Nie

**Frage 3:** Was passiert bei `name = name;` (ohne this)?
- A) Funktioniert perfekt
- B) Der Parameter weist sich selbst zu, die Eigenschaft bleibt leer/null
- C) Fehler
- D) Gleich wie this.name = name

**Frage 4:** Kann man this in Methoden benutzen?
- A) Nur im Konstruktor
- B) Ja, in allen Methoden der Klasse
- C) Nur in void-Methoden
- D) Nur mit static

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 3

- [ ] Block.java mit this im Konstruktor erstellt
- [ ] Truhe.java mit Methoden die Zustand aendern erstellt
- [ ] Ruestung.java mit komplexerem Objektverhalten erstellt
- [ ] this im Konstruktor verstanden
- [ ] this in Methoden verstanden
- [ ] Objekte koennen ihren eigenen Zustand veraendern

---

## Lektion 4: Getter und Setter

### Konzept

**Getter** lesen einen Wert, **Setter** setzen einen Wert. Damit kontrollierst du WER die Eigenschaften aendern darf und WIE.

**Minecraft-Bezug:**
Du kannst deine HP nicht einfach auf 1000 setzen - das Spiel kontrolliert das. Getter/Setter sind wie diese Kontrolle.

### private vs public

```java
public class Spieler {
    private int leben;  // private = nur INNERHALB der Klasse zugreifbar
    private String name;

    public Spieler(String name, int leben) {
        this.name = name;
        this.leben = leben;
    }

    // GETTER - Wert lesen
    public int getLeben() {
        return this.leben;
    }

    public String getName() {
        return this.name;
    }

    // SETTER - Wert setzen MIT Kontrolle
    public void setLeben(int leben) {
        if (leben >= 0 && leben <= 20) {  // Kontrolle!
            this.leben = leben;
        } else {
            System.out.println("Ungueltiger Wert!");
        }
    }
}
```

### Aufgabe 4.1: Spieler mit Getter/Setter

**Ziel:** Ueberarbeite `src/Spieler.java` mit private Eigenschaften und Getter/Setter.

**Mache ALLE Eigenschaften private:**
- `private String name`
- `private int leben`
- `private int level`

**Erstelle Getter und Setter fuer alle.**
**Setter fuer leben:** Nur Werte zwischen 0 und 20 erlauben!
**Setter fuer level:** Nur Werte >= 1 erlauben!

**Teste in SpielerTest.java:**

**Erwartete Ausgabe:**
```
=== Getter Test ===
Name: Steve
Leben: 20
Level: 5

=== Setter Test ===
Leben auf 15 gesetzt: 15
Leben auf -5 gesetzt: Ungueltiger Wert! Leben bleibt: 15
Level auf 0 gesetzt: Ungueltiger Wert! Level bleibt: 5
```

### Aufgabe 4.2: Item-Klasse mit Kontrolle

**Ziel:** Erstelle `src/Item.java` und `src/ItemTest.java`.

**Klasse Item:**
- `private String name`
- `private int anzahl`
- `private int maxStack` (z.B. 64 fuer die meisten Items)
- Konstruktor
- Getter fuer alle
- `setAnzahl(int n)` - nur wenn n >= 0 UND n <= maxStack
- `void hinzufuegen(int n)` - fuegt hinzu, aber nie ueber maxStack
- `void entfernen(int n)` - entfernt, aber nie unter 0
- `void zeigeInfo()`

**Erwartete Ausgabe:**
```
=== Item Test ===
Diamanten x10 (max: 64)
5 hinzugefuegt: Diamanten x15
100 hinzugefuegt: Kann nicht! Maximum ist 64. Diamanten x15
10 entfernt: Diamanten x5
20 entfernt: Kann nicht! Minimum ist 0. Diamanten x5
```

### Aufgabe 4.3: Erfahrungssystem

**Ziel:** Erstelle `src/Erfahrung.java` und `src/ErfahrungTest.java`.

**Klasse Erfahrung:**
- `private int xp`
- `private int level`
- `private int xpProLevel` = 100
- Konstruktor (startet bei Level 1, XP 0)
- `void addXP(int punkte)` - fuegt XP hinzu, prueft Level-Up
- `int getLevel()`, `int getXP()`
- `void zeigeStatus()`

**Level-Up Logik:** Wenn xp >= xpProLevel, dann level++, xp -= xpProLevel

**Erwartete Ausgabe:**
```
=== Erfahrungssystem ===
Level: 1, XP: 0/100
+50 XP gesammelt!
Level: 1, XP: 50/100
+60 XP gesammelt!
LEVEL UP! Du bist jetzt Level 2!
Level: 2, XP: 10/100
+200 XP gesammelt!
LEVEL UP! Du bist jetzt Level 3!
LEVEL UP! Du bist jetzt Level 4!
Level: 4, XP: 10/100
```

### Quiz Lektion 4

**Frage 1:** Was bedeutet `private`?
- A) Die Variable existiert nicht
- B) Nur innerhalb der Klasse zugreifbar
- C) Ueberall zugreifbar
- D) Nur in main()

**Frage 2:** Wozu braucht man Getter?
- A) Um private Werte von aussen zu LESEN
- B) Um Objekte zu erstellen
- C) Um Klassen zu loeschen
- D) Fuer Schleifen

**Frage 3:** Was ist der Vorteil von Settern?
- A) Sie sind schneller
- B) Man kann Werte kontrollieren/validieren
- C) Sie brauchen weniger Speicher
- D) Kein Vorteil

**Frage 4:** Was passiert bei `spieler.leben = 50;` wenn leben private ist?
- A) Funktioniert normal
- B) Kompilier-Fehler
- C) leben wird auf 50 gesetzt
- D) Das Programm stuerzt ab

**Antworten:** 1-B, 2-A, 3-B, 4-B

### Checkliste Lektion 4

- [ ] Spieler.java mit private und Getter/Setter ueberarbeitet
- [ ] Item.java mit Werte-Kontrolle in Settern erstellt
- [ ] Erfahrung.java mit Level-Up-System erstellt
- [ ] private/public Unterschied verstanden
- [ ] Getter und Setter schreiben koennen
- [ ] Werte-Validierung in Settern verstanden

---

## Lektion 5: Methoden vertiefen

### Konzept

Methoden sind Aktionen die ein Objekt ausfuehren kann. In dieser Lektion lernst du:
- Methoden mit Rueckgabewerten
- Methoden die andere Objekte als Parameter bekommen
- Methoden die mit dem eigenen Objekt arbeiten

**Minecraft-Bezug:**
- `spieler.angreifen(zombie)` - Der Spieler greift den Zombie an
- `zombie.nimmSchaden(spieler.getSchaden())` - Der Zombie nimmt Schaden
- Objekte interagieren miteinander!

### Objekte als Parameter

```java
public class Kaempfer {
    private String name;
    private int hp;
    private int schaden;

    // Ein Kaempfer greift einen ANDEREN Kaempfer an
    public void angreifen(Kaempfer gegner) {
        System.out.println(this.name + " greift " + gegner.getName() + " an!");
        gegner.nimmSchaden(this.schaden);
    }

    public void nimmSchaden(int dmg) {
        this.hp -= dmg;
        System.out.println(this.name + " hat noch " + this.hp + " HP");
    }
}
```

### Aufgabe 5.1: Kampfsystem

**Ziel:** Erstelle `src/Kaempfer.java` und `src/KampfTest.java`.

**Klasse Kaempfer:**
- Private Eigenschaften: `name`, `hp`, `maxHP`, `schaden`
- Konstruktor
- Getter fuer alle
- `void angreifen(Kaempfer gegner)` - greift den Gegner an
- `void nimmSchaden(int dmg)` - reduziert HP (nicht unter 0)
- `void heilen(int betrag)` - heilt (nicht ueber maxHP)
- `boolean istAmLeben()` - true wenn hp > 0
- `void zeigeStatus()`

**In KampfTest.java:** Spieler vs Zombie, 3 Runden Kampf.

**Erwartete Ausgabe:**
```
=== KAMPF ===
Held (HP: 100/100, Schaden: 15)
Zombie (HP: 50/50, Schaden: 8)

Runde 1:
Held greift Zombie an!
Zombie nimmt 15 Schaden! HP: 35/50
Zombie greift Held an!
Held nimmt 8 Schaden! HP: 92/100

Runde 2:
Held greift Zombie an!
Zombie nimmt 15 Schaden! HP: 20/50
Zombie greift Held an!
Held nimmt 8 Schaden! HP: 84/100

Runde 3:
Held greift Zombie an!
Zombie nimmt 15 Schaden! HP: 5/50
Zombie greift Held an!
Held nimmt 8 Schaden! HP: 76/100
```

### Aufgabe 5.2: Tauschsystem

**Ziel:** Erstelle ein System wo Spieler Items tauschen koennen.

**Erstelle `src/Haendler.java` und `src/HandelTest.java`:**

**Klasse Haendler:**
- Private: `name` (String), `item` (String), `gold` (int)
- Konstruktor, Getter
- `void kaufen(Haendler verkaeufer, int preis)` - kauft das Item des Verkaeufers

**Erwartete Ausgabe:**
```
=== VOR dem Handel ===
Steve: Gold: 100, Item: Schwert
Haendler Bob: Gold: 50, Item: Diamant

Steve kauft Diamant von Bob fuer 30 Gold!

=== NACH dem Handel ===
Steve: Gold: 70, Item: Diamant
Haendler Bob: Gold: 80, Item: Schwert
```

### Aufgabe 5.3: Rezept-System

**Ziel:** Erstelle `src/Rezept.java` und `src/RezeptTest.java`.

**Klasse Rezept:**
- `String ergebnis`, `String zutat1`, `int menge1`, `String zutat2`, `int menge2`
- Konstruktor
- `boolean kannCraften(int vorrat1, int vorrat2)` - prueft ob genug Zutaten da sind
- `void craften(int vorrat1, int vorrat2)` - gibt Ergebnis oder Fehlermeldung
- `void zeigeRezept()`

**Erstelle Rezepte fuer:** Fackel (1 Kohle + 1 Stock), Ofen (8 Steine + 0)

**Erwartete Ausgabe:**
```
=== Rezept: Fackel ===
Zutaten: 1x Kohle + 1x Stock
Ergebnis: Fackel

Vorrat: 5x Kohle, 3x Stock
Kann craften? true
Fackel gecraftet!

Vorrat: 5x Kohle, 0x Stock
Kann craften? false
Nicht genug Zutaten!
```

### Quiz Lektion 5

**Frage 1:** Kann eine Methode ein anderes Objekt als Parameter haben?
- A) Nein
- B) Ja
- C) Nur in main()
- D) Nur mit static

**Frage 2:** Was bedeutet `gegner.nimmSchaden(this.schaden)`?
- A) Der Gegner schadet sich selbst
- B) Das aktuelle Objekt (this) fuegt dem Gegner Schaden zu
- C) Fehler
- D) this wird geloescht

**Frage 3:** Kann eine Methode `boolean` zurueckgeben?
- A) Nein, nur int und String
- B) Ja
- C) Nur als Parameter
- D) Nur in if-Bedingungen

**Frage 4:** Was ist der Rueckgabetyp von `void nimmSchaden(int dmg)`?
- A) int
- B) nichts (void)
- C) boolean
- D) String

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 5

- [ ] Kaempfer.java mit Objekt-Interaktion erstellt
- [ ] KampfTest.java mit mehrrundiger Kampfsimulation laeuft
- [ ] Haendler.java mit Tauschsystem erstellt
- [ ] Rezept.java mit Crafting-Logik erstellt
- [ ] Methoden mit Objekten als Parameter verstanden
- [ ] Objekte die miteinander interagieren koennen erstellt

---

## Lektion 6: Vererbung (Grundlagen)

### Konzept

**Vererbung** bedeutet: Eine Klasse kann Eigenschaften und Methoden von einer anderen Klasse uebernehmen. Die "Eltern-Klasse" gibt weiter, die "Kind-Klasse" erbt.

**Minecraft-Bezug:**
- Eltern-Klasse: `Mob` (hat: name, hp, damage, kann: angreifen, sterben)
- Kind: `Zombie` erbt alles von Mob + hat eigene Extras
- Kind: `Creeper` erbt alles von Mob + kann explodieren
- Kind: `Skelett` erbt alles von Mob + schiesst Pfeile

### Syntax

```java
// Eltern-Klasse
public class Mob {
    protected String name;   // protected = Kinder koennen zugreifen
    protected int hp;

    public Mob(String name, int hp) {
        this.name = name;
        this.hp = hp;
    }

    public void zeigeInfo() {
        System.out.println(name + " (HP: " + hp + ")");
    }
}

// Kind-Klasse
public class Zombie extends Mob {    // "extends" = erbt von
    boolean istBaby;

    public Zombie(String name, int hp, boolean istBaby) {
        super(name, hp);             // super() ruft Eltern-Konstruktor auf
        this.istBaby = istBaby;
    }
}
```

### Aufgabe 6.1: Mob-Hierarchie

**Ziel:** Erstelle eine Mob-Vererbungshierarchie.

**Dateien:**
- `src/Mob.java` (Eltern-Klasse)
- `src/Zombie.java` (erbt von Mob)
- `src/Skelett.java` (erbt von Mob)
- `src/Creeper.java` (erbt von Mob)
- `src/MobArena.java` (main)

**Klasse Mob:** name, hp, damage + Konstruktor + zeigeInfo()
**Klasse Zombie:** Zusatz: `boolean istBaby` + eigener Konstruktor
**Klasse Skelett:** Zusatz: `boolean hatBogen` + eigener Konstruktor
**Klasse Creeper:** Zusatz: `int explosionsRadius` + eigener Konstruktor

**Erwartete Ausgabe:**
```
=== MOB-ARENA ===
Zombie (HP: 20, Schaden: 5) - Baby: false
Skelett (HP: 20, Schaden: 4) - Bogen: true
Creeper (HP: 20, Schaden: 25) - Explosionsradius: 3
```

### Aufgabe 6.2: Werkzeug-Vererbung

**Ziel:** Erstelle eine Werkzeug-Hierarchie.

**Dateien:**
- `src/Werkzeug.java` (Eltern)
- `src/Schwert.java` (erbt)
- `src/Spitzhacke.java` (erbt)
- `src/WerkzeugTest.java` (main)

**Werkzeug:** name, haltbarkeit, material
**Schwert:** Zusatz: schaden
**Spitzhacke:** Zusatz: abbauGeschwindigkeit

**Erwartete Ausgabe:**
```
=== Werkzeuge ===
Diamant-Schwert (Diamant) - Haltbarkeit: 1561, Schaden: 7
Eisen-Spitzhacke (Eisen) - Haltbarkeit: 251, Geschwindigkeit: 6
```

### Aufgabe 6.3: protected verstehen

**Ziel:** Experimentiere mit private, protected und public in der Vererbung.

**Aendere in Mob.java:**
- Mache `name` zu `private`
- Versuche in Zombie.java auf `this.name` zuzugreifen
- Beobachte den Fehler!
- Aendere zu `protected` und es funktioniert wieder

**Schreibe auf:** Was ist der Unterschied zwischen private, protected und public?

### Quiz Lektion 6

**Frage 1:** Was bedeutet `extends`?
- A) Die Klasse wird geloescht
- B) Die Klasse erbt von einer anderen
- C) Die Klasse wird groesser
- D) Die Klasse bekommt mehr Speicher

**Frage 2:** Was macht `super(name, hp)` im Kind-Konstruktor?
- A) Erstellt ein neues Objekt
- B) Ruft den Konstruktor der Eltern-Klasse auf
- C) Loescht die Eltern-Klasse
- D) Kopiert alles

**Frage 3:** Was bedeutet `protected`?
- A) Wie private
- B) Zugreifbar in der Klasse UND in Kind-Klassen
- C) Wie public
- D) Nur im Konstruktor

**Frage 4:** Kann eine Kind-Klasse eigene neue Eigenschaften haben?
- A) Nein, nur geerbte
- B) Ja
- C) Nur Methoden
- D) Nur mit super

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 6

- [ ] Mob-Hierarchie mit 3 Kind-Klassen erstellt
- [ ] Werkzeug-Hierarchie erstellt
- [ ] extends und super() verstanden
- [ ] protected vs private vs public verstanden
- [ ] Kind-Klassen mit eigenen Zusatz-Eigenschaften erstellt

---

## Lektion 7: Methoden ueberschreiben (@Override)

### Konzept

Eine Kind-Klasse kann Methoden der Eltern-Klasse **ueberschreiben**. Das heisst: Die Kind-Klasse hat eine eigene Version der Methode.

**Minecraft-Bezug:**
- Alle Mobs koennen `angreifen()`, aber:
  - Zombie schlaegt
  - Skelett schiesst Pfeile
  - Creeper explodiert
- Gleicher Methodenname, verschiedenes Verhalten!

### Syntax

```java
public class Mob {
    public void angreifen() {
        System.out.println(name + " greift an!");
    }
}

public class Creeper extends Mob {
    @Override  // Markierung: Diese Methode ueberschreibt die Eltern-Version
    public void angreifen() {
        System.out.println(name + " EXPLODIERT! BOOM!");
    }
}
```

### Aufgabe 7.1: Verschiedene Angriffsarten

**Ziel:** Ueberschreibe `angreifen()` in allen Mob-Klassen.

**Mob.java:** `angreifen()` gibt generische Nachricht aus
**Zombie.java:** `@Override angreifen()` - "schlaegt zu"
**Skelett.java:** `@Override angreifen()` - "schiesst einen Pfeil"
**Creeper.java:** `@Override angreifen()` - "explodiert"

**Erwartete Ausgabe:**
```
=== Angriffe ===
Zombie schlaegt zu! 5 Schaden!
Skelett schiesst einen Pfeil! 4 Schaden!
Creeper explodiert! BOOM! 25 Schaden!
```

### Aufgabe 7.2: Verschiedene zeigeInfo()

**Ziel:** Jede Mob-Klasse zeigt ihre Info anders an.

**Mob:** Standard-Info (Name, HP)
**Zombie:** + Baby-Status
**Skelett:** + Munition (Pfeile)
**Creeper:** + Explosionsstaerke + "GEFAHR"-Warnung

**Nutze `@Override` fuer jede Klasse.**

**Erwartete Ausgabe:**
```
[Zombie] HP: 20 | Schaden: 5 | Baby: false
[Skelett] HP: 20 | Schaden: 4 | Pfeile: 64
[Creeper] HP: 20 | Schaden: 25 | Radius: 3 | !! GEFAHR !!
```

### Aufgabe 7.3: Mob-Array mit verschiedenen Typen

**Ziel:** Erstelle ein Array vom Typ `Mob[]` und fuege verschiedene Mob-Typen ein.

**Das ist Polymorphie in Aktion:**
```java
Mob[] mobs = new Mob[4];
mobs[0] = new Zombie("Zombie", 20, 5, false);
mobs[1] = new Skelett("Skelett", 20, 4, 64);
mobs[2] = new Creeper("Creeper", 20, 25, 3);
mobs[3] = new Zombie("Baby-Zombie", 12, 4, true);
```

**Iteriere mit Schleife und rufe `angreifen()` auf - jeder Mob kaempft anders!**

**Erwartete Ausgabe:**
```
=== Alle Mobs greifen an! ===
Zombie schlaegt zu! 5 Schaden!
Skelett schiesst einen Pfeil! 4 Schaden!
Creeper explodiert! BOOM! 25 Schaden!
Baby-Zombie schlaegt zu! 4 Schaden!
```

### Quiz Lektion 7

**Frage 1:** Was macht `@Override`?
- A) Erstellt eine neue Methode
- B) Markiert dass die Methode die Eltern-Version ueberschreibt
- C) Loescht die Eltern-Methode
- D) Ist nur ein Kommentar

**Frage 2:** Muessen ueberschriebene Methoden den gleichen Namen haben?
- A) Nein
- B) Ja, gleicher Name UND gleiche Parameter
- C) Nur gleicher Name
- D) Egal

**Frage 3:** Was passiert bei `Mob[] mobs; mobs[0] = new Zombie(...);`?
- A) Fehler
- B) Funktioniert! Zombie IST ein Mob (durch Vererbung)
- C) Nur Mob-Objekte erlaubt
- D) Array wird zu Zombie-Array

**Frage 4:** Was wird aufgerufen bei `mobs[0].angreifen()` wenn mobs[0] ein Zombie ist?
- A) Die Mob-Version
- B) Die Zombie-Version (Override)
- C) Beide
- D) Keine

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 7

- [ ] angreifen() in allen Mob-Klassen ueberschrieben
- [ ] zeigeInfo() in allen Mob-Klassen ueberschrieben
- [ ] Mob-Array mit verschiedenen Typen erstellt
- [ ] @Override Annotation verstanden
- [ ] Polymorphie-Grundidee verstanden (verschiedene Typen im gleichen Array)

---

## Lektion 8: Alles zusammen - OOP-Projekt

### Konzept

In dieser Lektion kombinierst du ALLES aus Phase 2:
- Klassen und Objekte
- Konstruktoren
- this und super
- Getter/Setter (private/protected)
- Vererbung
- @Override

### Aufgabe 8.1: Mini-RPG Design

**Ziel:** Plane (auf Papier oder in einer Textdatei) folgendes System:

**Welche Klassen brauchst du?**
- Eltern-Klasse: `Charakter` (name, hp, schaden)
- Kind 1: `Spieler` (+ level, xp)
- Kind 2: `Monster` (+ dropItem)

**Welche Methoden?**
- angreifen(Charakter gegner)
- nimmSchaden(int dmg)
- istAmLeben()
- zeigeInfo()

**Schreibe dein Design auf bevor du codest!**

### Aufgabe 8.2: RPG implementieren

**Ziel:** Setze dein Design in Code um.

**Dateien:**
- `src/Charakter.java` (Eltern)
- `src/Spieler.java` (Kind)
- `src/Monster.java` (Kind)
- `src/RPGTest.java` (main)

**Der Spieler kaempft gegen 3 Monster hintereinander:**

**Erwartete Ausgabe (Beispiel):**
```
=== MINI-RPG ===
Held (Level 1, HP: 100, Schaden: 15)

--- Gegner 1: Slime ---
Held greift Slime an! -15 HP
Slime greift Held an! -3 HP
Held greift Slime an! -15 HP
Slime ist besiegt! Drop: Schleim
Held: 97/100 HP

--- Gegner 2: Zombie ---
Held greift Zombie an! -15 HP
Zombie greift Held an! -5 HP
...
Zombie ist besiegt! Drop: Fauliges Fleisch
Held: 87/100 HP

--- Gegner 3: Skelett ---
...
Skelett ist besiegt! Drop: Knochen
Held: 75/100 HP

=== SIEG! Alle Gegner besiegt! ===
```

### Aufgabe 8.3: Features hinzufuegen

**Ziel:** Erweitere dein RPG mit einem dieser Features:

**Option A:** Spieler heilt sich nach jedem Kampf um 10 HP
**Option B:** Monster werden staerker (jedes naechste +5 HP, +2 Schaden)
**Option C:** Spieler bekommt XP nach jedem Kill und levelt auf

**Waehle EINE Option und implementiere sie!**

### Quiz Lektion 8

**Frage 1:** Welches OOP-Konzept nutzt man fuer "Zombie ist eine Art Mob"?
- A) Kapselung
- B) Vererbung
- C) Getter/Setter
- D) Konstruktor

**Frage 2:** Was ist Kapselung (Encapsulation)?
- A) Code in Dateien aufteilen
- B) Daten mit private schuetzen und Zugriff ueber Getter/Setter
- C) Klassen erstellen
- D) Schleifen benutzen

**Frage 3:** Welche Reihenfolge beim Entwerfen ist am besten?
- A) Sofort Code schreiben
- B) Zuerst planen (Klassen, Eigenschaften, Methoden), dann Code
- C) Copy-Paste aus dem Internet
- D) Reihenfolge egal

**Frage 4:** Kann ein Spieler-Objekt in einem Mob-Array gespeichert werden, wenn Spieler NICHT von Mob erbt?
- A) Ja
- B) Nein
- C) Nur mit Casting
- D) Nur in main()

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 8

- [ ] RPG-System auf Papier geplant
- [ ] Charakter.java als Eltern-Klasse erstellt
- [ ] Spieler.java und Monster.java als Kind-Klassen erstellt
- [ ] Kampfsystem mit Schleife implementiert
- [ ] Mindestens ein zusaetzliches Feature eingebaut
- [ ] Alles kompiliert und laeuft fehlerfrei

---

## Phase 2 abgeschlossen?

Wenn du alle 8 Lektionen durchgearbeitet hast:

1. Pruefe alle Checklisten
2. Oeffne das ABSCHLUSSPROJEKT.md
3. Baue den **Zombie Kampfsimulator**!
4. Zeig deinem Tutor das Ergebnis fuer ein Code-Review

**Nach dem Abschlussprojekt bist du bereit fuer Phase 3: Collections!**
