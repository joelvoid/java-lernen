# Phase 3: Collections - Vollstaendiger Lernpfad
## 8 Lektionen mit Minecraft-Beispielen

**Dauer:** 3-4 Wochen (ca. 1 Stunde pro Tag, 4-5x pro Woche)
**Voraussetzungen:** Phase 1 (Basics) und Phase 2 (OOP) abgeschlossen
**Ziel:** ArrayList und HashMap verstehen und fuer Minecraft-aehnliche Systeme einsetzen koennen.

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

**Punkte pro Lektion:** 200 XP (noch schwieriger als Phase 2!)
**Abschlussprojekt:** 1000 XP

**Gesamt moeglich:** 2600 XP

---

## Lektion 1: ArrayList - Dynamische Listen (vs Array)

### Konzept

In Phase 1 hast du **Arrays** kennengelernt. Arrays haben eine feste Groesse. Aber was, wenn du nicht weisst, wie viele Items der Spieler sammeln wird?

**Minecraft-Bezug:**
Stell dir dein Inventar in Minecraft vor. Am Anfang ist es leer, dann sammelst du Holz, Stein, Eisen... Du weisst vorher nie, wie viele verschiedene Items du haben wirst! Ein Array mit fester Groesse waere wie eine Kiste mit genau 5 Faechern - was, wenn du 6 Items brauchst?

**ArrayList** ist wie eine magische Kiste, die automatisch groesser wird, wenn du mehr Items hineinlegst!

| Eigenschaft | Array | ArrayList |
|------------|-------|-----------|
| Groesse | Fest (z.B. 5) | Waechst automatisch |
| Erstellen | `String[] items = new String[5];` | `ArrayList<String> items = new ArrayList<>();` |
| Hinzufuegen | `items[0] = "Schwert";` | `items.add("Schwert");` |
| Groesse abfragen | `items.length` | `items.size()` |
| Import noetig? | Nein | Ja: `import java.util.ArrayList;` |

### Code-Beispiel zum Lesen

```java
import java.util.ArrayList;

public class MagischeKiste {
    public static void main(String[] args) {
        // Das alte Array - feste Groesse
        String[] alteKiste = new String[3];
        alteKiste[0] = "Schwert";
        alteKiste[1] = "Schild";
        alteKiste[2] = "Bogen";
        // alteKiste[3] = "Axt";  // FEHLER! Kein Platz mehr!

        System.out.println("=== Alte Kiste (Array) ===");
        System.out.println("Platz fuer: " + alteKiste.length + " Items");

        // Die neue ArrayList - waechst automatisch!
        ArrayList<String> magischeKiste = new ArrayList<>();
        magischeKiste.add("Schwert");
        magischeKiste.add("Schild");
        magischeKiste.add("Bogen");
        magischeKiste.add("Axt");       // Kein Problem!
        magischeKiste.add("Diamant");   // Immer noch Platz!

        System.out.println("\n=== Magische Kiste (ArrayList) ===");
        System.out.println("Items drin: " + magischeKiste.size());
        System.out.println("Erstes Item: " + magischeKiste.get(0));
        System.out.println("Letztes Item: " + magischeKiste.get(magischeKiste.size() - 1));
    }
}
```

**Ausgabe:**
```
=== Alte Kiste (Array) ===
Platz fuer: 3 Items

=== Magische Kiste (ArrayList) ===
Items drin: 5
Erstes Item: Schwert
Letztes Item: Diamant
```

**Wichtig:** Bei ArrayList brauchst du **immer** den Import ganz oben: `import java.util.ArrayList;`

Und beachte die spitzen Klammern: `ArrayList<String>` sagt Java, dass nur Strings in die Liste duerfen. Das nennt man **Generics**.

### Aufgabe 1.1: Erste ArrayList

**Ziel:** Erstelle `src/ErsteArrayList.java` - Dein erstes Programm mit ArrayList.

**Was du schreiben sollst:**
1. Importiere ArrayList
2. Erstelle eine `ArrayList<String>` namens `bloecke`
3. Fuege 4 Minecraft-Bloecke hinzu: "Erde", "Stein", "Sand", "Kies"
4. Gib die Anzahl und alle Bloecke einzeln mit `get()` aus

**Erwartete Ausgabe:**
```
=== Meine Bloecke ===
Anzahl: 4
Block 0: Erde
Block 1: Stein
Block 2: Sand
Block 3: Kies
```

**Kompilieren:** `javac src/ErsteArrayList.java`
**Starten:** `java -cp src ErsteArrayList`

**Hinweis:** Denke an `import java.util.ArrayList;` ganz oben!

### Aufgabe 1.2: ArrayList vs Array Vergleich

**Ziel:** Erstelle `src/ListeVsArray.java` - Zeige den Unterschied.

**Was du schreiben sollst:**
1. Erstelle ein String-Array mit Groesse 3 und fuelle es mit "Holz", "Stein", "Eisen"
2. Erstelle eine ArrayList und fuege die gleichen 3 Items hinzu
3. Fuege zur ArrayList noch "Gold" und "Diamant" hinzu (beim Array geht das NICHT!)
4. Gib beide aus

**Erwartete Ausgabe:**
```
=== Array (feste Groesse) ===
Array hat 3 Plaetze
[0] Holz
[1] Stein
[2] Eisen

=== ArrayList (dynamisch) ===
ArrayList hat 5 Items
[0] Holz
[1] Stein
[2] Eisen
[3] Gold
[4] Diamant
```

### Aufgabe 1.3: Mob-Spawner Liste

**Ziel:** Erstelle `src/MobSpawner.java` - Eine Liste von Mobs die spawnen.

**Was du schreiben sollst:**
1. Erstelle eine `ArrayList<String>` namens `spawnListe`
2. Fuege 6 Mobs hinzu: "Zombie", "Skelett", "Spinne", "Creeper", "Enderman", "Hexe"
3. Gib die Liste mit Nummern aus (starte bei 1, nicht 0!)
4. Gib am Ende die Gesamtzahl aus

**Erwartete Ausgabe:**
```
=== Mob Spawner ===
1. Zombie
2. Skelett
3. Spinne
4. Creeper
5. Enderman
6. Hexe
Gesamt: 6 Mobs koennen spawnen
```

**Hinweis:** Benutze eine for-Schleife: `for (int i = 0; i < spawnListe.size(); i++)` und gib `(i + 1) + ". " + spawnListe.get(i)` aus.

### Quiz Lektion 1

**Frage 1:** Was ist der groesste Vorteil von ArrayList gegenueber Array?
- A) ArrayList ist schneller
- B) ArrayList kann automatisch wachsen und schrumpfen
- C) ArrayList braucht keinen Import
- D) ArrayList speichert nur Zahlen

**Frage 2:** Wie erstellst du eine ArrayList fuer Strings?
- A) `ArrayList items = new ArrayList();`
- B) `ArrayList<String> items = new ArrayList<>();`
- C) `String[] items = new ArrayList();`
- D) `new ArrayList<String> items;`

**Frage 3:** Welchen Import brauchst du fuer ArrayList?
- A) `import java.ArrayList;`
- B) `import java.util.ArrayList;`
- C) `import ArrayList;`
- D) Keinen Import noetig

**Frage 4:** Wie fragst du die Anzahl der Elemente in einer ArrayList ab?
- A) `liste.length`
- B) `liste.count()`
- C) `liste.size()`
- D) `liste.anzahl()`

**Antworten:** 1-B, 2-B, 3-B, 4-C

### Checkliste Lektion 1

- [ ] Verstanden warum ArrayList besser ist als Array fuer dynamische Daten
- [ ] ErsteArrayList.java erstellt und laeuft
- [ ] ListeVsArray.java zeigt den Unterschied
- [ ] MobSpawner.java gibt nummerierte Liste aus
- [ ] Import `java.util.ArrayList` verstanden
- [ ] `<String>` Generics-Schreibweise verstanden

**Lektion 1 abgeschlossen? +200 XP! Weiter zu Lektion 2!**

---

## Lektion 2: ArrayList Methoden vertiefen

### Konzept

Du kennst jetzt `add()`, `get()` und `size()`. Aber ArrayList hat noch viel mehr nuetzliche Methoden! Stell dir vor, du verwaltest eine Truhe in Minecraft:

**Minecraft-Bezug:**
- `add("Schwert")` - Item in die Truhe legen
- `remove("Schwert")` - Item aus der Truhe nehmen
- `get(0)` - Schauen was im ersten Fach liegt
- `set(0, "Diamantschwert")` - Item im ersten Fach austauschen
- `contains("Gold")` - Pruefen ob Gold in der Truhe ist
- `size()` - Wie viele Items in der Truhe sind
- `indexOf("Bogen")` - In welchem Fach liegt der Bogen?

| Methode | Was sie tut | Beispiel |
|---------|------------|---------|
| `add(item)` | Fuegt am Ende hinzu | `liste.add("Schwert");` |
| `add(index, item)` | Fuegt an Position ein | `liste.add(0, "Schwert");` |
| `remove(index)` | Entfernt an Position | `liste.remove(2);` |
| `remove(item)` | Entfernt erstes Vorkommen | `liste.remove("Schwert");` |
| `get(index)` | Gibt Element an Position | `liste.get(0)` |
| `set(index, item)` | Ersetzt an Position | `liste.set(0, "Axt");` |
| `contains(item)` | Prueft ob enthalten | `liste.contains("Gold")` |
| `size()` | Anzahl Elemente | `liste.size()` |
| `indexOf(item)` | Position des Elements | `liste.indexOf("Bogen")` |
| `isEmpty()` | Ist die Liste leer? | `liste.isEmpty()` |

### Code-Beispiel zum Lesen

```java
import java.util.ArrayList;

public class TruheVerwalten {
    public static void main(String[] args) {
        ArrayList<String> truhe = new ArrayList<>();

        // Items hinzufuegen
        truhe.add("Holzschwert");
        truhe.add("Brot");
        truhe.add("Fackel");
        truhe.add("Kohle");
        System.out.println("Truhe: " + truhe);

        // Item ersetzen: Holzschwert wird zu Eisenschwert!
        truhe.set(0, "Eisenschwert");
        System.out.println("Nach Upgrade: " + truhe);

        // Ist Brot in der Truhe?
        System.out.println("Brot vorhanden? " + truhe.contains("Brot"));
        System.out.println("Diamant vorhanden? " + truhe.contains("Diamant"));

        // Wo liegt die Fackel?
        int pos = truhe.indexOf("Fackel");
        System.out.println("Fackel ist an Position: " + pos);

        // Kohle entfernen
        truhe.remove("Kohle");
        System.out.println("Nach Entfernen von Kohle: " + truhe);
        System.out.println("Items in Truhe: " + truhe.size());
    }
}
```

**Ausgabe:**
```
Truhe: [Holzschwert, Brot, Fackel, Kohle]
Nach Upgrade: [Eisenschwert, Brot, Fackel, Kohle]
Brot vorhanden? true
Diamant vorhanden? false
Fackel ist an Position: 2
Nach Entfernen von Kohle: [Eisenschwert, Brot, Fackel]
Items in Truhe: 3
```

**Tipp:** Wenn du eine ArrayList direkt mit `System.out.println(liste)` ausgibst, zeigt Java sie in eckigen Klammern an: `[Item1, Item2, Item3]`. Sehr praktisch zum Testen!

### Aufgabe 2.1: Inventar Manager

**Ziel:** Erstelle `src/InventarManager.java` - Verwalte ein Spieler-Inventar.

**Was du schreiben sollst:**
1. Erstelle eine ArrayList und fuege hinzu: "Holzschwert", "Brot", "Fackel", "Stein", "Kohle"
2. Gib das Inventar aus
3. Ersetze "Holzschwert" (Position 0) durch "Diamantschwert" mit `set()`
4. Entferne "Kohle" mit `remove()`
5. Fuege "Goldapfel" an Position 1 ein mit `add(1, ...)`
6. Gib das neue Inventar aus

**Erwartete Ausgabe:**
```
=== Inventar vorher ===
[Holzschwert, Brot, Fackel, Stein, Kohle]
Anzahl Items: 5

=== Aenderungen ===
Holzschwert -> Diamantschwert (Upgrade!)
Kohle entfernt
Goldapfel an Position 1 eingefuegt

=== Inventar nachher ===
[Diamantschwert, Goldapfel, Brot, Fackel, Stein]
Anzahl Items: 5
```

### Aufgabe 2.2: Item Sucher

**Ziel:** Erstelle `src/ItemSucher.java` - Suche Items in einer Liste.

**Was du schreiben sollst:**
1. Erstelle eine ArrayList mit 6 Items: "Schwert", "Bogen", "Schild", "Trank", "Brot", "Fackel"
2. Pruefe mit `contains()` ob "Trank", "Diamant" und "Bogen" vorhanden sind
3. Finde die Position von "Schild" und "Brot" mit `indexOf()`
4. Pruefe was `indexOf()` zurueckgibt wenn ein Item NICHT existiert

**Erwartete Ausgabe:**
```
=== Item Sucher ===
Inventar: [Schwert, Bogen, Schild, Trank, Brot, Fackel]

Trank vorhanden? true
Diamant vorhanden? false
Bogen vorhanden? true

Position von Schild: 2
Position von Brot: 4
Position von Diamant: -1 (nicht gefunden!)
```

**Hinweis:** `indexOf()` gibt `-1` zurueck, wenn das Element nicht in der Liste ist!

### Aufgabe 2.3: Werkbank Upgrade

**Ziel:** Erstelle `src/WerkbankUpgrade.java` - Ersetze Items durch bessere Versionen.

**Was du schreiben sollst:**
1. Erstelle eine ArrayList mit: "Holzschwert", "Holzspitzhacke", "Holzaxt", "Holzschaufel"
2. Gib die Liste aus
3. Ersetze jedes Item: Benutze eine for-Schleife und `set()`, um "Holz" durch "Stein" zu ersetzen
4. Gib die aktualisierte Liste aus
5. Ersetze erneut: diesmal "Stein" durch "Eisen"
6. Gib die finale Liste aus

**Erwartete Ausgabe:**
```
=== Werkbank Upgrade ===
Holz-Werkzeuge: [Holzschwert, Holzspitzhacke, Holzaxt, Holzschaufel]

Upgrade auf Stein...
Stein-Werkzeuge: [Steinschwert, Steinspitzhacke, Steinaxt, Steinschaufel]

Upgrade auf Eisen...
Eisen-Werkzeuge: [Eisenschwert, Eisenspitzhacke, Eisenaxt, Eisenschaufel]
```

**Hinweis:** Benutze `String.replace("Holz", "Stein")` um Teile eines Strings zu ersetzen! Also: `liste.set(i, liste.get(i).replace("Holz", "Stein"));`

### Quiz Lektion 2

**Frage 1:** Was macht `liste.set(2, "Diamant")`?
- A) Fuegt "Diamant" am Ende hinzu
- B) Ersetzt das Element an Position 2 durch "Diamant"
- C) Loescht das Element an Position 2
- D) Prueft ob "Diamant" an Position 2 ist

**Frage 2:** Was gibt `liste.indexOf("Gold")` zurueck, wenn "Gold" NICHT in der Liste ist?
- A) 0
- B) null
- C) -1
- D) Eine Fehlermeldung

**Frage 3:** Was ist der Unterschied zwischen `remove(0)` und `remove("Schwert")`?
- A) Kein Unterschied
- B) `remove(0)` entfernt an Position 0, `remove("Schwert")` entfernt das erste "Schwert"
- C) `remove(0)` ist schneller
- D) `remove("Schwert")` entfernt alle "Schwert" Eintraege

**Frage 4:** Was macht `liste.contains("Brot")`?
- A) Fuegt "Brot" hinzu
- B) Entfernt "Brot"
- C) Gibt true oder false zurueck, ob "Brot" in der Liste ist
- D) Zaehlt wie oft "Brot" vorkommt

**Antworten:** 1-B, 2-C, 3-B, 4-C

### Checkliste Lektion 2

- [ ] Alle ArrayList-Methoden aus der Tabelle kennengelernt
- [ ] InventarManager.java erstellt und laeuft
- [ ] ItemSucher.java mit contains() und indexOf() laeuft
- [ ] WerkbankUpgrade.java mit set() und replace() laeuft
- [ ] Verstanden was indexOf() bei fehlendem Element zurueckgibt
- [ ] Unterschied zwischen remove(index) und remove(objekt) verstanden

**Lektion 2 abgeschlossen? +200 XP! Weiter zu Lektion 3!**

---

## Lektion 3: for-each Schleife mit ArrayList

### Konzept

Bisher hast du mit einer normalen for-Schleife durch ArrayLists iteriert:
```java
for (int i = 0; i < liste.size(); i++) {
    System.out.println(liste.get(i));
}
```

Das funktioniert, aber Java hat etwas Einfacheres: die **for-each Schleife**!

```java
for (String item : liste) {
    System.out.println(item);
}
```

**Minecraft-Bezug:**
Stell dir vor, du gehst durch jede Truhe in deiner Basis und schaust was drin ist. Die for-each Schleife ist wie: "Fuer JEDE Truhe in meiner Basis: oeffne sie und zeige den Inhalt." Du musst nicht zaehlen, wie viele Truhen es sind - Java macht das automatisch!

**Lese es so:** `for (String item : liste)` = "Fuer jeden String namens item IN der liste"

| Normale for-Schleife | for-each Schleife |
|----------------------|-------------------|
| `for (int i = 0; i < liste.size(); i++)` | `for (String item : liste)` |
| Braucht Index-Variable | Kein Index noetig |
| Zugriff mit `liste.get(i)` | Direkter Zugriff mit `item` |
| Gut wenn du den Index brauchst | Gut wenn du nur die Werte brauchst |

### Code-Beispiel zum Lesen

```java
import java.util.ArrayList;

public class ForEachDemo {
    public static void main(String[] args) {
        ArrayList<String> inventar = new ArrayList<>();
        inventar.add("Diamantschwert");
        inventar.add("Goldapfel");
        inventar.add("Enderperle");
        inventar.add("Bogen");
        inventar.add("Pfeile");

        // Normale for-Schleife (mit Index)
        System.out.println("=== Mit normaler for-Schleife ===");
        for (int i = 0; i < inventar.size(); i++) {
            System.out.println("Slot " + i + ": " + inventar.get(i));
        }

        // for-each Schleife (einfacher!)
        System.out.println("\n=== Mit for-each Schleife ===");
        for (String item : inventar) {
            System.out.println("- " + item);
        }

        // for-each mit Zaehler (wenn du DOCH nummerieren willst)
        System.out.println("\n=== for-each mit Zaehler ===");
        int nummer = 1;
        for (String item : inventar) {
            System.out.println(nummer + ". " + item);
            nummer++;
        }
    }
}
```

**Ausgabe:**
```
=== Mit normaler for-Schleife ===
Slot 0: Diamantschwert
Slot 1: Goldapfel
Slot 2: Enderperle
Slot 3: Bogen
Slot 4: Pfeile

=== Mit for-each Schleife ===
- Diamantschwert
- Goldapfel
- Enderperle
- Bogen
- Pfeile

=== for-each mit Zaehler ===
1. Diamantschwert
2. Goldapfel
3. Enderperle
4. Bogen
5. Pfeile
```

### Aufgabe 3.1: Kampfbericht

**Ziel:** Erstelle `src/Kampfbericht.java` - Zeige einen Kampfbericht mit for-each.

**Was du schreiben sollst:**
1. Erstelle eine `ArrayList<String>` namens `besiegteGegner`
2. Fuege hinzu: "Zombie", "Skelett", "Spinne", "Creeper", "Zombie", "Hexe", "Zombie"
3. Benutze for-each um jeden Gegner auszugeben
4. Zaehle mit einer Variablen, wie viele Zombies besiegt wurden

**Erwartete Ausgabe:**
```
=== Kampfbericht ===
Besiegt: Zombie
Besiegt: Skelett
Besiegt: Spinne
Besiegt: Creeper
Besiegt: Zombie
Besiegt: Hexe
Besiegt: Zombie

Gesamt besiegt: 7
Davon Zombies: 3
```

**Hinweis:** Benutze ein `if` in der for-each Schleife: `if (gegner.equals("Zombie")) { zombieZaehler++; }`

### Aufgabe 3.2: Inventar Bewertung

**Ziel:** Erstelle `src/InventarBewertung.java` - Bewerte Items mit for-each.

**Was du schreiben sollst:**
1. Erstelle eine `ArrayList<String>` mit: "Diamantschwert", "Brot", "Holzspitzhacke", "Goldapfel", "Fackel", "Diamantruestung"
2. Benutze for-each und pruefe fuer jedes Item:
   - Wenn es mit "Diamant" anfaengt: "LEGENDAER"
   - Wenn es mit "Gold" anfaengt: "SELTEN"
   - Sonst: "NORMAL"

**Erwartete Ausgabe:**
```
=== Inventar Bewertung ===
Diamantschwert -> LEGENDAER
Brot -> NORMAL
Holzspitzhacke -> NORMAL
Goldapfel -> SELTEN
Fackel -> NORMAL
Diamantruestung -> LEGENDAER

Legendaere Items: 2
Seltene Items: 1
Normale Items: 3
```

**Hinweis:** Benutze `item.startsWith("Diamant")` um zu pruefen ob ein String mit "Diamant" anfaengt!

### Aufgabe 3.3: Erz-Zaehler

**Ziel:** Erstelle `src/ErzZaehler.java` - Zaehle verschiedene Erze.

**Was du schreiben sollst:**
1. Erstelle eine ArrayList die eine Mine simuliert: "Stein", "Kohle", "Stein", "Eisen", "Stein", "Gold", "Stein", "Diamant", "Kohle", "Stein", "Eisen", "Kohle"
2. Benutze for-each und zaehle: wie oft kommt Stein, Kohle, Eisen, Gold und Diamant vor?
3. Gib die Ergebnisse aus

**Erwartete Ausgabe:**
```
=== Mine Ergebnis ===
Abgebaute Bloecke: 12

Stein: 5
Kohle: 3
Eisen: 2
Gold: 1
Diamant: 1

Wertvolle Erze gefunden: 7
```

**Hinweis:** Erstelle fuer jedes Erz eine eigene Zaehlvariable (z.B. `int steinCount = 0;`). "Wertvolle Erze" = alles ausser Stein.

### Quiz Lektion 3

**Frage 1:** Wie liest man `for (String item : liste)`?
- A) Fuer String item gleich liste
- B) Fuer jeden String namens item IN der liste
- C) String item ist groesser als liste
- D) Erstelle einen String aus der liste

**Frage 2:** Wann solltest du die NORMALE for-Schleife statt for-each benutzen?
- A) Immer
- B) Nie
- C) Wenn du den Index brauchst
- D) Wenn die Liste leer ist

**Frage 3:** Was passiert bei for-each wenn die ArrayList leer ist?
- A) Fehler / Absturz
- B) Die Schleife wird einfach uebersprungen
- C) Java fuegt automatisch Elemente hinzu
- D) Eine Endlosschleife

**Frage 4:** Was macht `item.startsWith("Gold")`?
- A) Fuegt "Gold" am Anfang des Strings hinzu
- B) Entfernt "Gold" vom Anfang
- C) Prueft ob der String mit "Gold" anfaengt (true/false)
- D) Zaehlt wie oft "Gold" vorkommt

**Antworten:** 1-B, 2-C, 3-B, 4-C

### Checkliste Lektion 3

- [ ] for-each Syntax verstanden: `for (Typ name : liste)`
- [ ] Kampfbericht.java mit for-each und Zaehlen laeuft
- [ ] InventarBewertung.java mit startsWith() Pruefung laeuft
- [ ] ErzZaehler.java mit mehreren Zaehlern laeuft
- [ ] Unterschied for-each vs normale for-Schleife verstanden
- [ ] Weiss wann welche Schleife besser passt

**Lektion 3 abgeschlossen? +200 XP! Weiter zu Lektion 4!**

---

## Lektion 4: ArrayList mit eigenen Objekten

### Konzept

Bisher waren in deinen ArrayLists nur Strings. Aber in Phase 2 hast du eigene Klassen erstellt (Spieler, Mob, Item...). Die kannst du auch in eine ArrayList packen!

**Minecraft-Bezug:**
In Minecraft hat jedes Item nicht nur einen Namen, sondern auch Schaden, Haltbarkeit, Verzauberung usw. Statt einer `ArrayList<String>` mit nur Namen, benutzen wir `ArrayList<Item>` mit ganzen Item-Objekten!

```java
// Nur Namen (langweilig)
ArrayList<String> items = new ArrayList<>();

// Ganze Objekte (viel besser!)
ArrayList<Item> items = new ArrayList<>();
```

### Code-Beispiel zum Lesen

```java
// Datei: Item.java
public class Item {
    String name;
    int wert;
    String seltenheit;

    Item(String name, int wert, String seltenheit) {
        this.name = name;
        this.wert = wert;
        this.seltenheit = seltenheit;
    }

    void zeigeInfo() {
        System.out.println(name + " (Wert: " + wert + ", " + seltenheit + ")");
    }
}
```

```java
// Datei: ItemListe.java
import java.util.ArrayList;

public class ItemListe {
    public static void main(String[] args) {
        ArrayList<Item> inventar = new ArrayList<>();

        inventar.add(new Item("Diamantschwert", 500, "Legendaer"));
        inventar.add(new Item("Brot", 5, "Normal"));
        inventar.add(new Item("Goldapfel", 100, "Selten"));
        inventar.add(new Item("Fackel", 2, "Normal"));

        System.out.println("=== Inventar ===");
        for (Item item : inventar) {
            item.zeigeInfo();
        }

        // Gesamtwert berechnen
        int gesamtwert = 0;
        for (Item item : inventar) {
            gesamtwert = gesamtwert + item.wert;
        }
        System.out.println("\nGesamtwert: " + gesamtwert + " Gold");
    }
}
```

**Ausgabe:**
```
=== Inventar ===
Diamantschwert (Wert: 500, Legendaer)
Brot (Wert: 5, Normal)
Goldapfel (Wert: 100, Selten)
Fackel (Wert: 2, Normal)

Gesamtwert: 607 Gold
```

### Aufgabe 4.1: Mob-Armee

**Ziel:** Erstelle `src/Mob.java` und `src/MobArmee.java` - Verwalte eine Armee von Mobs.

**Datei 1 - `src/Mob.java`:**
- Eigenschaften: `name` (String), `hp` (int), `schaden` (int)
- Konstruktor mit allen 3 Werten
- Methode `void zeigeInfo()`: Gibt "Name - HP: X, Schaden: Y" aus

**Datei 2 - `src/MobArmee.java`:**
1. Erstelle eine `ArrayList<Mob>`
2. Fuege 5 Mobs hinzu: Zombie(20,5), Skelett(20,4), Spinne(16,3), Creeper(20,25), Enderman(40,7)
3. Gib alle Mobs mit for-each aus
4. Berechne die gesamten HP und den gesamten Schaden aller Mobs

**Erwartete Ausgabe:**
```
=== Mob Armee ===
Zombie - HP: 20, Schaden: 5
Skelett - HP: 20, Schaden: 4
Spinne - HP: 16, Schaden: 3
Creeper - HP: 20, Schaden: 25
Enderman - HP: 40, Schaden: 7

Anzahl Mobs: 5
Gesamt HP: 116
Gesamt Schaden: 44
```

**Kompilieren:** `javac src/Mob.java src/MobArmee.java`
**Starten:** `java -cp src MobArmee`

### Aufgabe 4.2: Bester Mob finden

**Ziel:** Erstelle `src/BesterMob.java` - Finde den staerksten und den zaehesten Mob.

**Was du schreiben sollst:**
1. Benutze die gleiche Mob.java Klasse von Aufgabe 4.1
2. Erstelle die gleiche Mob-Liste
3. Finde mit for-each den Mob mit den meisten HP
4. Finde den Mob mit dem hoechsten Schaden

**Erwartete Ausgabe:**
```
=== Mob Analyse ===
Alle Mobs:
- Zombie (HP: 20, Schaden: 5)
- Skelett (HP: 20, Schaden: 4)
- Spinne (HP: 16, Schaden: 3)
- Creeper (HP: 20, Schaden: 25)
- Enderman (HP: 40, Schaden: 7)

Zaehester Mob: Enderman mit 40 HP
Staerkster Mob: Creeper mit 25 Schaden
```

**Hinweis:** Erstelle Variablen `String zaehesterName = ""; int maxHP = 0;` und vergleiche in der Schleife: `if (mob.hp > maxHP) { maxHP = mob.hp; zaehesterName = mob.name; }`

### Aufgabe 4.3: Kampf-Simulation

**Ziel:** Erstelle `src/KampfSimulation.java` - Simuliere Kaempfe gegen Mobs.

**Was du schreiben sollst:**
1. Benutze die Mob.java Klasse
2. Erstelle eine ArrayList mit 3 Mobs: Zombie(20,5), Skelett(20,4), Spinne(16,3)
3. Der Spieler hat 100 HP und macht 10 Schaden
4. Gehe mit for-each durch die Mobs. Fuer jeden Mob:
   - Gib aus: "Kampf gegen [Mob]!"
   - Berechne wie viele Runden der Spieler braucht (Mob HP / Spieler Schaden, aufrunden)
   - Der Mob macht pro Runde Schaden am Spieler
   - Gib die verbleibenden Spieler-HP aus

**Erwartete Ausgabe:**
```
=== Kampf Simulation ===
Spieler HP: 100

Kampf gegen Zombie!
Runden: 2 | Zombie besiegt!
Spieler verliert 10 HP
Spieler HP: 90

Kampf gegen Skelett!
Runden: 2 | Skelett besiegt!
Spieler verliert 8 HP
Spieler HP: 82

Kampf gegen Spinne!
Runden: 2 | Spinne besiegt!
Spieler verliert 6 HP
Spieler HP: 76

=== Ergebnis ===
Alle Mobs besiegt!
Spieler ueberlebt mit 76 HP
```

**Hinweis:** Runden berechnen: `int runden = (mob.hp + spielerSchaden - 1) / spielerSchaden;` (das rundet auf). Schaden am Spieler pro Mob: `runden * mob.schaden`.

### Quiz Lektion 4

**Frage 1:** Wie erstellt man eine ArrayList die Mob-Objekte speichert?
- A) `ArrayList<Mob> mobs = new ArrayList<>();`
- B) `ArrayList mobs = new Mob();`
- C) `Mob[] mobs = new ArrayList<>();`
- D) `ArrayList<String> mobs = new Mob<>();`

**Frage 2:** Wie fuegt man ein Mob-Objekt zur Liste hinzu?
- A) `mobs.add("Zombie");`
- B) `mobs.add(new Mob("Zombie", 20, 5));`
- C) `mobs.new Mob("Zombie");`
- D) `mobs.put(new Mob("Zombie", 20, 5));`

**Frage 3:** Wie greift man in for-each auf die HP eines Mobs zu?
- A) `for (Mob m : mobs) { m.hp; }`
- B) `for (String m : mobs) { m.hp; }`
- C) `for (Mob m : mobs) { mobs.hp; }`
- D) `for (int m : mobs) { m.hp; }`

**Frage 4:** Muessen beide Dateien (Mob.java und MobArmee.java) zusammen kompiliert werden?
- A) Nein, jede einzeln
- B) Ja, mit `javac src/Mob.java src/MobArmee.java`
- C) Nur MobArmee.java reicht
- D) Man braucht einen speziellen Befehl

**Antworten:** 1-A, 2-B, 3-A, 4-B

### Checkliste Lektion 4

- [ ] Mob.java Klasse mit Konstruktor erstellt
- [ ] MobArmee.java mit ArrayList von Mob-Objekten laeuft
- [ ] BesterMob.java findet Maximum in der Liste
- [ ] KampfSimulation.java simuliert Kaempfe mit Berechnungen
- [ ] Verstanden wie man eigene Objekte in ArrayList speichert
- [ ] for-each mit eigenen Objekten angewendet

**Lektion 4 abgeschlossen? +200 XP! Weiter zu Lektion 5!**

---

## Lektion 5: HashMap - Schluessel-Wert-Paare

### Konzept

Eine **HashMap** speichert Daten als **Schluessel-Wert-Paare**. Jeder Schluessel zeigt auf einen Wert - wie ein Woerterbuch, wo jedes Wort eine Erklaerung hat.

**Minecraft-Bezug:**
Stell dir ein **Rezeptbuch** in Minecraft vor:
- Schluessel: "Schwert" -> Wert: "2 Diamanten + 1 Stock"
- Schluessel: "Fackel" -> Wert: "1 Kohle + 1 Stock"

Oder ein **Lager** wo du weisst, wie viele von jedem Item du hast:
- "Holz" -> 64
- "Stein" -> 128
- "Diamant" -> 3

Bei einer ArrayList musst du die Position (Index) wissen: `inventar.get(3)`. Bei einer HashMap suchst du mit dem **Namen**: `lager.get("Diamant")`. Viel einfacher!

| Eigenschaft | ArrayList | HashMap |
|------------|-----------|---------|
| Zugriff | Per Index (0, 1, 2...) | Per Schluessel ("Diamant") |
| Sortiert? | Ja (Reihenfolge bleibt) | Nein (keine feste Reihenfolge) |
| Erstellen | `ArrayList<String>` | `HashMap<String, Integer>` |
| Hinzufuegen | `add("Item")` | `put("Item", 5)` |
| Import | `java.util.ArrayList` | `java.util.HashMap` |

### Code-Beispiel zum Lesen

```java
import java.util.HashMap;

public class MinecraftLager {
    public static void main(String[] args) {
        HashMap<String, Integer> lager = new HashMap<>();

        // Items ins Lager legen (Schluessel -> Wert)
        lager.put("Holz", 64);
        lager.put("Stein", 128);
        lager.put("Eisen", 24);
        lager.put("Gold", 8);
        lager.put("Diamant", 3);

        // Ein bestimmtes Item abfragen
        System.out.println("=== Lager Abfrage ===");
        System.out.println("Holz: " + lager.get("Holz"));
        System.out.println("Diamant: " + lager.get("Diamant"));
        System.out.println("Smaragd: " + lager.get("Smaragd")); // null - nicht vorhanden!

        // Pruefen ob ein Item existiert
        System.out.println("\nHaben wir Gold? " + lager.containsKey("Gold"));
        System.out.println("Haben wir Smaragd? " + lager.containsKey("Smaragd"));

        // Anzahl verschiedener Items
        System.out.println("\nVerschiedene Items: " + lager.size());
    }
}
```

**Ausgabe:**
```
=== Lager Abfrage ===
Holz: 64
Diamant: 3
Smaragd: null

Haben wir Gold? true
Haben wir Smaragd? false

Verschiedene Items: 5
```

**Wichtig:** Bei HashMap brauchst du ZWEI Typen in den spitzen Klammern: `HashMap<SchluesselTyp, WertTyp>`. Fuer Zahlen benutzt du `Integer` statt `int` (Java-Besonderheit bei Generics).

### Aufgabe 5.1: Minecraft Rezeptbuch

**Ziel:** Erstelle `src/Rezeptbuch.java` - Ein Crafting-Rezeptbuch als HashMap.

**Was du schreiben sollst:**
1. Erstelle eine `HashMap<String, String>` namens `rezepte`
2. Fuege 5 Rezepte hinzu (Schluessel = Item, Wert = Zutaten):
   - "Schwert" -> "2x Diamant + 1x Stock"
   - "Fackel" -> "1x Kohle + 1x Stock"
   - "Ofen" -> "8x Stein"
   - "Truhe" -> "8x Holz"
   - "Werkbank" -> "4x Holz"
3. Frage 3 Rezepte ab und gib sie aus
4. Pruefe ob ein Rezept fuer "Amboss" existiert

**Erwartete Ausgabe:**
```
=== Minecraft Rezeptbuch ===
Rezepte gespeichert: 5

Wie craftet man ein Schwert?
-> 2x Diamant + 1x Stock

Wie craftet man eine Fackel?
-> 1x Kohle + 1x Stock

Wie craftet man einen Ofen?
-> 8x Stein

Rezept fuer Amboss vorhanden? false
```

**Kompilieren:** `javac src/Rezeptbuch.java`
**Starten:** `java -cp src Rezeptbuch`

### Aufgabe 5.2: Spieler Statistik

**Ziel:** Erstelle `src/SpielerStatistik.java` - Speichere Spieler-Statistiken.

**Was du schreiben sollst:**
1. Erstelle eine `HashMap<String, Integer>` namens `stats`
2. Fuege hinzu: "Mobs besiegt" -> 142, "Bloecke abgebaut" -> 5830, "Tode" -> 7, "Spielzeit Minuten" -> 4200, "Level" -> 28
3. Gib alle Statistiken aus
4. Berechne Mobs pro Tod (Mobs besiegt / Tode)

**Erwartete Ausgabe:**
```
=== Spieler Statistik ===
Mobs besiegt: 142
Bloecke abgebaut: 5830
Tode: 7
Spielzeit Minuten: 4200
Level: 28

=== Analyse ===
Mobs pro Tod: 20
Spielzeit in Stunden: 70
```

### Aufgabe 5.3: Erz-Preisliste

**Ziel:** Erstelle `src/ErzPreisliste.java` - Ein Handelssystem mit Preisen.

**Was du schreiben sollst:**
1. Erstelle eine `HashMap<String, Integer>` fuer Preise pro Einheit
2. Fuege hinzu: "Kohle" -> 1, "Eisen" -> 5, "Gold" -> 15, "Diamant" -> 50, "Smaragd" -> 30
3. Der Spieler hat: 10 Kohle, 5 Eisen, 3 Gold, 1 Diamant
4. Berechne den Gesamtwert des Spieler-Inventars

**Erwartete Ausgabe:**
```
=== Erz Preisliste ===
Kohle: 1 Gold pro Stueck
Eisen: 5 Gold pro Stueck
Gold: 15 Gold pro Stueck
Diamant: 50 Gold pro Stueck
Smaragd: 30 Gold pro Stueck

=== Spieler Inventar Wert ===
10x Kohle = 10 Gold
5x Eisen = 25 Gold
3x Gold = 45 Gold
1x Diamant = 50 Gold

Gesamtwert: 130 Gold
```

### Quiz Lektion 5

**Frage 1:** Was speichert eine HashMap?
- A) Nur Strings
- B) Nur Zahlen
- C) Schluessel-Wert-Paare
- D) Nur eine Liste von Items

**Frage 2:** Was gibt `map.get("Gold")` zurueck wenn "Gold" NICHT in der HashMap ist?
- A) 0
- B) ""
- C) null
- D) Eine Fehlermeldung

**Frage 3:** Wie erstellst du eine HashMap mit String-Schluesseln und Integer-Werten?
- A) `HashMap<String, int> map = new HashMap<>();`
- B) `HashMap<String, Integer> map = new HashMap<>();`
- C) `HashMap map = new HashMap();`
- D) `Map<String> map = new HashMap<>();`

**Frage 4:** Was passiert wenn du `map.put("Holz", 64)` aufrufst und "Holz" schon existiert?
- A) Fehler
- B) Es wird ein zweiter Eintrag erstellt
- C) Der alte Wert wird durch 64 ersetzt
- D) Nichts passiert

**Antworten:** 1-C, 2-C, 3-B, 4-C

### Checkliste Lektion 5

- [ ] HashMap Konzept verstanden: Schluessel-Wert-Paare
- [ ] Rezeptbuch.java mit String-String HashMap laeuft
- [ ] SpielerStatistik.java mit String-Integer HashMap laeuft
- [ ] ErzPreisliste.java mit Berechnung aus HashMap-Werten laeuft
- [ ] Import `java.util.HashMap` verstanden
- [ ] Unterschied ArrayList vs HashMap verstanden

**Lektion 5 abgeschlossen? +200 XP! Weiter zu Lektion 6!**

---

## Lektion 6: HashMap Methoden vertiefen

### Konzept

Genau wie ArrayList hat auch HashMap viele nuetzliche Methoden. Die wichtigsten lernst du jetzt!

**Minecraft-Bezug:**
Stell dir vor, du verwaltest einen grossen Lagerraum mit vielen Truhen. Du willst:
- Alle Truhen-Namen sehen (`keySet()`)
- Alle Inhalte sehen (`values()`)
- Eine bestimmte Truhe leeren (`remove()`)
- Pruefen ob eine Truhe existiert (`containsKey()`)
- Durch alle Truhen gehen (`for-each` mit `keySet()`)

| Methode | Was sie tut | Beispiel |
|---------|------------|---------|
| `put(key, value)` | Fuegt Paar hinzu / ersetzt Wert | `map.put("Gold", 10);` |
| `get(key)` | Gibt Wert zum Schluessel | `map.get("Gold")` |
| `remove(key)` | Entfernt Paar | `map.remove("Gold");` |
| `containsKey(key)` | Prueft ob Schluessel existiert | `map.containsKey("Gold")` |
| `containsValue(value)` | Prueft ob Wert existiert | `map.containsValue(10)` |
| `keySet()` | Alle Schluessel | `map.keySet()` |
| `values()` | Alle Werte | `map.values()` |
| `size()` | Anzahl Paare | `map.size()` |
| `isEmpty()` | Ist leer? | `map.isEmpty()` |

### Code-Beispiel zum Lesen

```java
import java.util.HashMap;

public class LagerVerwaltung {
    public static void main(String[] args) {
        HashMap<String, Integer> lager = new HashMap<>();

        lager.put("Holz", 64);
        lager.put("Stein", 128);
        lager.put("Eisen", 24);
        lager.put("Gold", 8);
        lager.put("Diamant", 3);

        // Alle Schluessel anzeigen
        System.out.println("=== Alle Items im Lager ===");
        System.out.println("Items: " + lager.keySet());

        // Alle Werte anzeigen
        System.out.println("Mengen: " + lager.values());

        // Durch alle Eintraege gehen mit for-each
        System.out.println("\n=== Lager Bestand ===");
        for (String item : lager.keySet()) {
            System.out.println(item + ": " + lager.get(item) + " Stueck");
        }

        // Item entfernen
        lager.remove("Stein");
        System.out.println("\nStein entfernt!");
        System.out.println("Noch " + lager.size() + " verschiedene Items");

        // Wert aendern (Eisen dazulegen)
        int altesMengeEisen = lager.get("Eisen");
        lager.put("Eisen", altesMengeEisen + 16);
        System.out.println("Eisen aufgestockt: " + lager.get("Eisen"));
    }
}
```

**Ausgabe:**
```
=== Alle Items im Lager ===
Items: [Holz, Gold, Diamant, Stein, Eisen]
Mengen: [64, 8, 3, 128, 24]

=== Lager Bestand ===
Holz: 64 Stueck
Gold: 8 Stueck
Diamant: 3 Stueck
Stein: 128 Stueck
Eisen: 24 Stueck

Stein entfernt!
Noch 4 verschiedene Items
Eisen aufgestockt: 40
```

**Hinweis:** Die Reihenfolge bei HashMap ist NICHT garantiert! Die Items koennen in beliebiger Reihenfolge ausgegeben werden. Das ist normal!

### Aufgabe 6.1: Haendler System

**Ziel:** Erstelle `src/HaendlerSystem.java` - Ein Dorf-Haendler mit HashMap.

**Was du schreiben sollst:**
1. Erstelle eine `HashMap<String, Integer>` namens `haendlerPreise`
2. Fuege Preise hinzu: "Brot"->3, "Schwert"->25, "Schild"->20, "Trank"->15, "Pfeil"->1, "Bogen"->18
3. Zeige alle Waren mit keySet() und for-each
4. Der Spieler hat 50 Gold. Kaufe "Schwert" und "Trank" (ziehe Preise ab)
5. Entferne ein Item ("Pfeil") aus dem Sortiment mit remove()
6. Zeige das aktualisierte Sortiment

**Erwartete Ausgabe:**
```
=== Dorf Haendler ===
Sortiment (6 Waren):
- Brot: 3 Gold
- Schwert: 25 Gold
- Schild: 20 Gold
- Trank: 15 Gold
- Pfeil: 1 Gold
- Bogen: 18 Gold

=== Einkauf ===
Spieler Gold: 50
Schwert gekauft fuer 25 Gold. Restgold: 25
Trank gekauft fuer 15 Gold. Restgold: 10

Pfeil aus dem Sortiment entfernt.

=== Aktuelles Sortiment (5 Waren) ===
- Brot: 3 Gold
- Schwert: 25 Gold
- Schild: 20 Gold
- Trank: 15 Gold
- Bogen: 18 Gold
```

**Hinweis:** Die Reihenfolge der Items kann bei dir anders sein - das ist bei HashMap normal!

### Aufgabe 6.2: Mob Drops Zaehler

**Ziel:** Erstelle `src/MobDrops.java` - Zaehle Mob-Drops mit HashMap.

**Was du schreiben sollst:**
1. Erstelle eine `HashMap<String, Integer>` namens `drops`
2. Simuliere 10 Mob-Kills: "Knochen", "Feder", "Knochen", "Fleisch", "Feder", "Knochen", "Ender Perle", "Feder", "Fleisch", "Knochen"
3. Fuer jedes Drop: Wenn der Schluessel schon existiert, erhoehe den Wert um 1. Wenn nicht, setze ihn auf 1.
4. Zeige alle Drops und ihre Anzahl

**Erwartete Ausgabe:**
```
=== Mob Drops Zaehler ===
Drops gesammelt:
Knochen: 4x
Feder: 3x
Fleisch: 2x
Ender Perle: 1x

Verschiedene Drop-Arten: 4
Gesamt Drops: 10
```

**Hinweis:** Pruefe mit `containsKey()`:
```java
if (drops.containsKey(drop)) {
    drops.put(drop, drops.get(drop) + 1);
} else {
    drops.put(drop, 1);
}
```

### Aufgabe 6.3: Verzauberungs-Werkstatt

**Ziel:** Erstelle `src/Verzauberung.java` - Verwalte Verzauberungen und ihre Level.

**Was du schreiben sollst:**
1. Erstelle eine `HashMap<String, Integer>` namens `verzauberungen`
2. Fuege hinzu: "Schaerfe"->3, "Schutz"->2, "Haltbarkeit"->1, "Effizienz"->2
3. Zeige alle Verzauberungen
4. Upgrade "Schaerfe" um 1 Level (3 -> 4)
5. Upgrade "Haltbarkeit" um 2 Level (1 -> 3)
6. Fuege neue Verzauberung hinzu: "Glueck"->1
7. Entferne "Effizienz"
8. Zeige das finale Ergebnis

**Erwartete Ausgabe:**
```
=== Verzauberungs-Werkstatt ===

Aktuelle Verzauberungen:
Schaerfe Level 3
Schutz Level 2
Haltbarkeit Level 1
Effizienz Level 2

=== Upgrades ===
Schaerfe: Level 3 -> Level 4
Haltbarkeit: Level 1 -> Level 3
Neue Verzauberung: Glueck Level 1
Effizienz entfernt

=== Finale Verzauberungen ===
Schaerfe Level 4
Schutz Level 2
Haltbarkeit Level 3
Glueck Level 1

Gesamt Verzauberungen: 4
```

### Quiz Lektion 6

**Frage 1:** Was gibt `map.keySet()` zurueck?
- A) Alle Werte
- B) Alle Schluessel
- C) Alle Schluessel-Wert-Paare
- D) Die Groesse der Map

**Frage 2:** Wie erhoehst du den Wert von "Gold" um 10?
- A) `map.add("Gold", 10);`
- B) `map.put("Gold", map.get("Gold") + 10);`
- C) `map.get("Gold") + 10;`
- D) `map.increase("Gold", 10);`

**Frage 3:** Was passiert bei `map.remove("Stein")` wenn "Stein" nicht existiert?
- A) Fehler / Absturz
- B) Nichts - es wird einfach ignoriert
- C) Die ganze Map wird geloescht
- D) null wird zur Map hinzugefuegt

**Frage 4:** Wie iterierst du durch alle Eintraege einer HashMap?
- A) `for (int i = 0; i < map.size(); i++)`
- B) `for (String key : map.keySet())`
- C) `for (String key : map)`
- D) `map.forEach()`

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 6

- [ ] keySet(), values() und remove() verstanden
- [ ] HaendlerSystem.java mit Kauf-Logik laeuft
- [ ] MobDrops.java mit dynamischem Zaehlen laeuft
- [ ] Verzauberung.java mit Upgrade-Logik laeuft
- [ ] for-each ueber keySet() zum Iterieren durch HashMap gelernt
- [ ] Werte in HashMap erhoehen/aendern geuebt

**Lektion 6 abgeschlossen? +200 XP! Weiter zu Lektion 7!**

---

## Lektion 7: HashMap mit Objekten als Werte

### Konzept

Bisher waren die Werte in deinen HashMaps immer einfache Typen (String, Integer). Aber du kannst auch **eigene Objekte** als Werte speichern!

**Minecraft-Bezug:**
Stell dir vor, du hast ein Register aller Spieler auf deinem Server. Der Schluessel ist der Spielername (String), und der Wert ist ein ganzes Spieler-Objekt mit allen Infos (HP, Level, Inventar...):

```
"Steve" -> Spieler(hp=20, level=15, xp=3000)
"Alex"  -> Spieler(hp=18, level=22, xp=7500)
```

Das ist VIEL besser als fuer jede Info eine separate HashMap zu haben!

### Code-Beispiel zum Lesen

```java
// Datei: Spieler.java
public class Spieler {
    String name;
    int hp;
    int level;
    int xp;

    Spieler(String name, int hp, int level, int xp) {
        this.name = name;
        this.hp = hp;
        this.level = level;
        this.xp = xp;
    }

    void zeigeInfo() {
        System.out.println(name + " - HP: " + hp + ", Level: " + level + ", XP: " + xp);
    }
}
```

```java
// Datei: SpielerRegister.java
import java.util.HashMap;

public class SpielerRegister {
    public static void main(String[] args) {
        HashMap<String, Spieler> register = new HashMap<>();

        register.put("Steve", new Spieler("Steve", 20, 15, 3000));
        register.put("Alex", new Spieler("Alex", 18, 22, 7500));
        register.put("Notch", new Spieler("Notch", 20, 99, 50000));

        // Einen bestimmten Spieler abfragen
        Spieler s = register.get("Alex");
        System.out.println("=== Spieler Suche ===");
        s.zeigeInfo();

        // Alle Spieler anzeigen
        System.out.println("\n=== Alle Spieler ===");
        for (String name : register.keySet()) {
            register.get(name).zeigeInfo();
        }

        // Spieler-Level direkt aendern
        register.get("Steve").level = 16;
        register.get("Steve").xp = 3500;
        System.out.println("\n=== Nach Update ===");
        register.get("Steve").zeigeInfo();
    }
}
```

**Ausgabe:**
```
=== Spieler Suche ===
Alex - HP: 18, Level: 22, XP: 7500

=== Alle Spieler ===
Alex - HP: 18, Level: 22, XP: 7500
Steve - HP: 20, Level: 15, XP: 3000
Notch - HP: 20, Level: 99, XP: 50000

=== Nach Update ===
Steve - HP: 20, Level: 16, XP: 3500
```

### Aufgabe 7.1: Mob Enzyklopaedie

**Ziel:** Erstelle `src/MobInfo.java` und `src/MobEnzyklopaedie.java` - Ein Nachschlagewerk fuer Mobs.

**Datei 1 - `src/MobInfo.java`:**
- Eigenschaften: `name` (String), `hp` (int), `schaden` (int), `dropItem` (String)
- Konstruktor mit allen 4 Werten
- Methode `void zeigeInfo()`: Gibt alle Infos formatiert aus

**Datei 2 - `src/MobEnzyklopaedie.java`:**
1. Erstelle `HashMap<String, MobInfo>` namens `enzyklopaedie`
2. Fuege 5 Mobs hinzu:
   - "Zombie" -> MobInfo("Zombie", 20, 5, "Verrottetes Fleisch")
   - "Skelett" -> MobInfo("Skelett", 20, 4, "Knochen")
   - "Creeper" -> MobInfo("Creeper", 20, 25, "Schwarzpulver")
   - "Enderman" -> MobInfo("Enderman", 40, 7, "Enderperle")
   - "Hexe" -> MobInfo("Hexe", 26, 6, "Trank")
3. Schlage 2 Mobs nach und zeige ihre Infos
4. Zeige alle Mobs in der Enzyklopaedie

**Erwartete Ausgabe:**
```
=== Mob Enzyklopaedie ===
5 Mobs registriert

--- Mob nachschlagen: Creeper ---
Name: Creeper
HP: 20
Schaden: 25
Drop: Schwarzpulver

--- Mob nachschlagen: Enderman ---
Name: Enderman
HP: 40
Schaden: 7
Drop: Enderperle

=== Alle Mobs ===
Zombie - HP: 20, Schaden: 5, Drop: Verrottetes Fleisch
Skelett - HP: 20, Schaden: 4, Drop: Knochen
Creeper - HP: 20, Schaden: 25, Drop: Schwarzpulver
Enderman - HP: 40, Schaden: 7, Drop: Enderperle
Hexe - HP: 26, Schaden: 6, Drop: Trank
```

**Kompilieren:** `javac src/MobInfo.java src/MobEnzyklopaedie.java`
**Starten:** `java -cp src MobEnzyklopaedie`

### Aufgabe 7.2: Block Register

**Ziel:** Erstelle `src/BlockDaten.java` und `src/BlockRegister.java` - Ein Register fuer Minecraft-Bloecke.

**Datei 1 - `src/BlockDaten.java`:**
- Eigenschaften: `name` (String), `haerte` (int, 1-10), `werkzeug` (String), `drop` (String)
- Konstruktor mit allen 4 Werten
- Methode `void zeigeInfo()`

**Datei 2 - `src/BlockRegister.java`:**
1. Erstelle `HashMap<String, BlockDaten>` namens `bloecke`
2. Fuege hinzu:
   - "Stein" -> BlockDaten("Stein", 5, "Spitzhacke", "Pflasterstein")
   - "Holz" -> BlockDaten("Holz", 2, "Axt", "Holz")
   - "Diamanterz" -> BlockDaten("Diamanterz", 8, "Eisenspitzhacke", "Diamant")
   - "Obsidian" -> BlockDaten("Obsidian", 10, "Diamantspitzhacke", "Obsidian")
3. Gib alle Bloecke aus
4. Finde den haertesten Block (mit for-each und Vergleich)

**Erwartete Ausgabe:**
```
=== Block Register ===
4 Bloecke registriert

Alle Bloecke:
Stein - Haerte: 5, Werkzeug: Spitzhacke, Drop: Pflasterstein
Holz - Haerte: 2, Werkzeug: Axt, Drop: Holz
Diamanterz - Haerte: 8, Werkzeug: Eisenspitzhacke, Drop: Diamant
Obsidian - Haerte: 10, Werkzeug: Diamantspitzhacke, Drop: Obsidian

Haertester Block: Obsidian (Haerte: 10)
```

### Aufgabe 7.3: Server Rangliste

**Ziel:** Erstelle `src/ServerRangliste.java` - Benutze die Spieler.java aus dem Code-Beispiel.

**Was du schreiben sollst:**
1. Erstelle `HashMap<String, Spieler>` mit 4 Spielern:
   - "Steve" -> Spieler("Steve", 20, 15, 3000)
   - "Alex" -> Spieler("Alex", 18, 22, 7500)
   - "Herobrine" -> Spieler("Herobrine", 20, 50, 25000)
   - "Dream" -> Spieler("Dream", 14, 35, 18000)
2. Zeige alle Spieler
3. Finde den Spieler mit dem hoechsten Level
4. Finde den Spieler mit den meisten XP
5. Berechne den Durchschnittslevel aller Spieler

**Erwartete Ausgabe:**
```
=== Server Rangliste ===
Spieler auf dem Server: 4

Alle Spieler:
Steve - HP: 20, Level: 15, XP: 3000
Alex - HP: 18, Level: 22, XP: 7500
Herobrine - HP: 20, Level: 50, XP: 25000
Dream - HP: 14, Level: 35, XP: 18000

=== Rangliste ===
Hoechstes Level: Herobrine (Level 50)
Meiste XP: Herobrine (25000 XP)
Durchschnittslevel: 30
```

**Hinweis:** Durchschnitt berechnen: Addiere alle Level zusammen und teile durch die Anzahl Spieler (`register.size()`).

### Quiz Lektion 7

**Frage 1:** Was ist der Vorteil von `HashMap<String, Spieler>` gegenueber `HashMap<String, Integer>`?
- A) Es ist schneller
- B) Man kann mehrere zusammengehoerige Informationen in einem Objekt speichern
- C) Man braucht weniger Speicher
- D) Kein Vorteil

**Frage 2:** Wie greifst du auf die HP eines Spielers in der HashMap zu?
- A) `register.hp`
- B) `register.get("Steve").hp`
- C) `register.get(hp)`
- D) `register["Steve"].hp`

**Frage 3:** Kann man den Wert eines Objekts in der HashMap direkt aendern?
- A) Nein, man muss das Objekt entfernen und neu hinzufuegen
- B) Ja, mit `register.get("Steve").level = 20;`
- C) Nur mit einer speziellen Methode
- D) Nur wenn das Objekt public ist

**Frage 4:** Was passiert bei `register.get("unbekannt")` wenn "unbekannt" nicht existiert?
- A) Leeres Spieler-Objekt
- B) Fehler / Absturz
- C) null
- D) 0

**Antworten:** 1-B, 2-B, 3-B, 4-C

### Checkliste Lektion 7

- [ ] MobInfo.java und MobEnzyklopaedie.java erstellt und laeuft
- [ ] BlockDaten.java und BlockRegister.java mit Maximum-Suche laeuft
- [ ] ServerRangliste.java mit Rangliste und Durchschnitt laeuft
- [ ] Verstanden wie man Objekte als HashMap-Werte benutzt
- [ ] Kann auf Objekt-Eigenschaften in der HashMap zugreifen
- [ ] Kann durch HashMap mit Objekten iterieren und vergleichen

**Lektion 7 abgeschlossen? +200 XP! Weiter zu Lektion 8 - dem Finale!**

---

## Lektion 8: Collections kombinieren - ArrayList + HashMap Projekt

### Konzept

Jetzt kommt alles zusammen! In echten Programmen (und in Minecraft-Mods) benutzt man oft ArrayList und HashMap ZUSAMMEN.

**Minecraft-Bezug:**
Stell dir ein komplettes Minecraft-Inventarsystem vor:
- Eine **HashMap** speichert verschiedene Truhen: `HashMap<String, ArrayList<String>>` - Jede Truhe (Schluessel) hat eine Liste von Items (Wert)!
- Oder: Eine **ArrayList von HashMaps** - Eine Liste von Spielern, wobei jeder Spieler mehrere Statistiken hat.

**Kombinationen:**
```java
// HashMap mit ArrayList als Wert
HashMap<String, ArrayList<String>> truhen = new HashMap<>();

// ArrayList mit HashMap als Element
ArrayList<HashMap<String, Integer>> spielerListe = new ArrayList<>();
```

### Code-Beispiel zum Lesen

```java
import java.util.ArrayList;
import java.util.HashMap;

public class TruhenSystem {
    public static void main(String[] args) {
        // Jede Truhe hat einen Namen und eine Liste von Items
        HashMap<String, ArrayList<String>> truhen = new HashMap<>();

        // Waffen-Truhe erstellen und fuellen
        ArrayList<String> waffenTruhe = new ArrayList<>();
        waffenTruhe.add("Diamantschwert");
        waffenTruhe.add("Bogen");
        waffenTruhe.add("Dreizack");
        truhen.put("Waffen", waffenTruhe);

        // Essen-Truhe erstellen und fuellen
        ArrayList<String> essenTruhe = new ArrayList<>();
        essenTruhe.add("Steak");
        essenTruhe.add("Goldapfel");
        essenTruhe.add("Brot");
        essenTruhe.add("Kuchen");
        truhen.put("Essen", essenTruhe);

        // Erz-Truhe erstellen und fuellen
        ArrayList<String> erzTruhe = new ArrayList<>();
        erzTruhe.add("Diamant");
        erzTruhe.add("Gold");
        erzTruhe.add("Eisen");
        truhen.put("Erze", erzTruhe);

        // Alle Truhen anzeigen
        System.out.println("=== Truhen System ===");
        System.out.println("Anzahl Truhen: " + truhen.size());

        for (String truhenName : truhen.keySet()) {
            ArrayList<String> inhalt = truhen.get(truhenName);
            System.out.println("\n[" + truhenName + "] (" + inhalt.size() + " Items)");
            for (String item : inhalt) {
                System.out.println("  - " + item);
            }
        }

        // Item suchen: In welcher Truhe ist der Goldapfel?
        System.out.println("\n=== Suche: Goldapfel ===");
        for (String truhenName : truhen.keySet()) {
            if (truhen.get(truhenName).contains("Goldapfel")) {
                System.out.println("Gefunden in Truhe: " + truhenName);
            }
        }
    }
}
```

**Ausgabe:**
```
=== Truhen System ===
Anzahl Truhen: 3

[Waffen] (3 Items)
  - Diamantschwert
  - Bogen
  - Dreizack

[Essen] (4 Items)
  - Steak
  - Goldapfel
  - Brot
  - Kuchen

[Erze] (3 Items)
  - Diamant
  - Gold
  - Eisen

=== Suche: Goldapfel ===
Gefunden in Truhe: Essen
```

### Aufgabe 8.1: Biom-Mobs Datenbank

**Ziel:** Erstelle `src/BiomMobs.java` - Welche Mobs spawnen in welchem Biom?

**Was du schreiben sollst:**
1. Erstelle `HashMap<String, ArrayList<String>>` namens `biomMobs`
2. Fuege 4 Biome mit ihren Mobs hinzu:
   - "Wald" -> [Zombie, Skelett, Spinne, Creeper]
   - "Wueste" -> [Husk, Skelett, Spinne]
   - "Nether" -> [Ghast, Piglin, Magmawuerfel, Lohe]
   - "End" -> [Enderman, Shulker, Enderdrache]
3. Zeige alle Biome und ihre Mobs an
4. Finde das Biom mit den meisten Mobs
5. Zaehle die Gesamtzahl aller Mobs ueber alle Biome

**Erwartete Ausgabe:**
```
=== Biom-Mobs Datenbank ===

[Wald] - 4 Mobs:
  1. Zombie
  2. Skelett
  3. Spinne
  4. Creeper

[Wueste] - 3 Mobs:
  1. Husk
  2. Skelett
  3. Spinne

[Nether] - 4 Mobs:
  1. Ghast
  2. Piglin
  3. Magmawuerfel
  4. Lohe

[End] - 3 Mobs:
  1. Enderman
  2. Shulker
  3. Enderdrache

=== Statistik ===
Biome gesamt: 4
Mobs gesamt: 14
Biom mit den meisten Mobs: Wald (4 Mobs)
```

**Hinweis:** Benutze eine verschachtelte for-each Schleife: Zuerst durch die Biome (keySet), dann durch die Mob-Liste jedes Bioms.

### Aufgabe 8.2: Crafting-System

**Ziel:** Erstelle `src/CraftingSystem.java` - Ein Crafting-System das HashMap und ArrayList kombiniert.

**Was du schreiben sollst:**
1. Erstelle `HashMap<String, ArrayList<String>>` namens `rezepte` (Item -> Liste der Zutaten)
2. Erstelle `HashMap<String, Integer>` namens `inventar` (Material -> Anzahl)
3. Fuege Rezepte hinzu:
   - "Schwert" -> ["Diamant", "Diamant", "Stock"]
   - "Fackel" -> ["Kohle", "Stock"]
   - "Ofen" -> ["Stein", "Stein", "Stein", "Stein", "Stein", "Stein", "Stein", "Stein"]
4. Fuege Inventar hinzu: "Diamant"->5, "Stock"->10, "Kohle"->3, "Stein"->6
5. Zeige alle Rezepte an
6. Pruefe fuer jedes Rezept ob genug Materialien vorhanden sind

**Erwartete Ausgabe:**
```
=== Crafting System ===

Rezepte:
Schwert: [Diamant, Diamant, Stock]
Fackel: [Kohle, Stock]
Ofen: [Stein, Stein, Stein, Stein, Stein, Stein, Stein, Stein]

Inventar:
Diamant: 5
Stock: 10
Kohle: 3
Stein: 6

=== Crafting Check ===
Schwert crafbar? JA (2x Diamant, 1x Stock vorhanden)
Fackel crafbar? JA (1x Kohle, 1x Stock vorhanden)
Ofen crafbar? NEIN (braucht 8x Stein, habe nur 6)
```

**Hinweis:** Um zu pruefen ob ein Rezept crafbar ist, zaehle fuer jede Zutat wie oft sie im Rezept vorkommt und vergleiche mit dem Inventar. Das ist die groesste Herausforderung bisher! Tipp: Erstelle eine Hilfs-HashMap die zaehlt, wie oft jede Zutat im Rezept vorkommt.

### Aufgabe 8.3: Mini Dungeon Loot Tabelle

**Ziel:** Erstelle `src/DungeonLoot.java` - Ein Loot-System fuer ein Dungeon.

**Was du schreiben sollst:**
1. Erstelle `HashMap<String, ArrayList<String>>` namens `dungeonRaeume` fuer Raeume und ihren Loot
2. Fuege 3 Raeume hinzu:
   - "Eingangshalle" -> ["Fackel", "Brot", "Kohle"]
   - "Schatzkammer" -> ["Diamant", "Goldapfel", "Verzaubertes Buch", "Smaragd"]
   - "Boss Raum" -> ["Drachenatem", "Elytra", "Diamantschwert"]
3. Erstelle eine `ArrayList<String>` namens `gesammelterLoot` (anfangs leer)
4. "Durchlaufe" jeden Raum: Gib den Raumnamen aus und fuege alle Items zum gesammelten Loot hinzu
5. Zeige am Ende den gesamten gesammelten Loot an

**Erwartete Ausgabe:**
```
=== Dungeon Abenteuer ===

Betrete: Eingangshalle
  Gefunden: Fackel
  Gefunden: Brot
  Gefunden: Kohle

Betrete: Schatzkammer
  Gefunden: Diamant
  Gefunden: Goldapfel
  Gefunden: Verzaubertes Buch
  Gefunden: Smaragd

Betrete: Boss Raum
  Gefunden: Drachenatem
  Gefunden: Elytra
  Gefunden: Diamantschwert

=== Gesammelter Loot ===
Items gesamt: 10
1. Fackel
2. Brot
3. Kohle
4. Diamant
5. Goldapfel
6. Verzaubertes Buch
7. Smaragd
8. Drachenatem
9. Elytra
10. Diamantschwert

Dungeon abgeschlossen!
```

**Hinweis:** Benutze `gesammelterLoot.add(item)` in der inneren for-each Schleife, um jedes gefundene Item zur Gesamtliste hinzuzufuegen. Damit die Raeume in der richtigen Reihenfolge durchlaufen werden, erstelle eine extra `ArrayList<String>` mit den Raumnamen in der gewuenschten Reihenfolge.

### Quiz Lektion 8

**Frage 1:** Was ist der Typ von `HashMap<String, ArrayList<String>>`?
- A) Eine Liste von Strings
- B) Eine Map von Strings zu Strings
- C) Eine Map von Strings zu Listen von Strings
- D) Eine Liste von Maps

**Frage 2:** Wie fuegst du ein Item zur ArrayList INNERHALB einer HashMap hinzu?
- A) `map.add("Truhe", "Schwert");`
- B) `map.get("Truhe").add("Schwert");`
- C) `map.put("Truhe", "Schwert");`
- D) `map.get("Truhe").put("Schwert");`

**Frage 3:** Warum ist die Reihenfolge bei HashMap nicht garantiert?
- A) Weil HashMap kaputt ist
- B) Weil HashMap nach Hash-Codes sortiert, nicht nach Einfuege-Reihenfolge
- C) Weil Java einen Bug hat
- D) Weil HashMap nur fuer kleine Datenmengen gedacht ist

**Frage 4:** Was hast du in Phase 3 NICHT gelernt?
- A) ArrayList
- B) HashMap
- C) for-each Schleife
- D) Datenbanken

**Antworten:** 1-C, 2-B, 3-B, 4-D

### Checkliste Lektion 8

- [ ] BiomMobs.java mit HashMap von ArrayLists laeuft
- [ ] CraftingSystem.java mit zwei HashMaps kombiniert laeuft
- [ ] DungeonLoot.java sammelt Loot aus mehreren Raeumen
- [ ] Verstanden wie man ArrayList und HashMap kombiniert
- [ ] Verschachtelte for-each Schleifen angewendet
- [ ] Bereit fuer das Abschlussprojekt!

**Lektion 8 abgeschlossen? +200 XP! Du hast alle Lektionen geschafft!**

---

## Zusammenfassung Phase 3

### Was du gelernt hast

| Lektion | Thema | Wichtigste Konzepte |
|---------|-------|-------------------|
| 1 | ArrayList Basics | Dynamische Listen, import, Generics |
| 2 | ArrayList Methoden | add, remove, get, set, contains, indexOf |
| 3 | for-each Schleife | Einfaches Iterieren ueber Collections |
| 4 | ArrayList mit Objekten | Eigene Klassen in ArrayList speichern |
| 5 | HashMap Basics | Schluessel-Wert-Paare, put, get |
| 6 | HashMap Methoden | keySet, values, remove, containsKey |
| 7 | HashMap mit Objekten | Eigene Klassen als HashMap-Werte |
| 8 | Collections kombinieren | HashMap + ArrayList zusammen nutzen |

### Deine XP Uebersicht

| Quelle | XP |
|--------|-----|
| Lektion 1 | 200 XP |
| Lektion 2 | 200 XP |
| Lektion 3 | 200 XP |
| Lektion 4 | 200 XP |
| Lektion 5 | 200 XP |
| Lektion 6 | 200 XP |
| Lektion 7 | 200 XP |
| Lektion 8 | 200 XP |
| **Abschlussprojekt** | **1000 XP** |
| **Gesamt Phase 3** | **2600 XP** |

---

## Naechster Schritt: Abschlussprojekt!

Du hast alle 8 Lektionen abgeschlossen - fantastisch!

Oeffne jetzt **`ABSCHLUSSPROJEKT.md`** in diesem Ordner und baue dein eigenes **Minecraft Inventar- und Lagersystem** mit allem was du gelernt hast!

Das Abschlussprojekt kombiniert ArrayList, HashMap, eigene Klassen, for-each und alles andere aus Phase 3. Es bringt satte **1000 XP**!

Nach dem Abschlussprojekt bist du bereit fuer **Phase 4: File I/O** - dort lernst du, Daten in Dateien zu speichern und zu laden!

---

**Viel Erfolg bei Phase 3! Du schaffst das!**
