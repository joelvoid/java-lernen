# Phase 4: I/O & Exceptions - Vollstaendiger Lernpfad
## 8 Lektionen mit Minecraft-Beispielen

**Dauer:** 4-6 Wochen (ca. 1 Stunde pro Tag, 4-5x pro Woche)
**Voraussetzungen:** Phase 1-3 abgeschlossen (Basics, OOP, Collections)
**Ziel:** Dateien lesen und schreiben, Benutzereingaben verarbeiten, Fehler richtig behandeln - wie ein echter Minecraft-Mod-Entwickler!

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

**Punkte pro Lektion:** 200 XP (die schwerste Phase bisher!)
**Abschlussprojekt:** 1000 XP

---

## Programm ausfuehren

Wie in Phase 2 und 3: Klicke ▶ oben in der Datei mit `main()` (ueber `public static void main`), oder nutze das Terminal.

---

## Lektion 1: Scanner - Benutzereingabe von der Konsole

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Phase 1-3 abgeschlossen
**Ziel:** Mit dem Scanner Eingaben vom Benutzer lesen und verarbeiten
**Belohnung:** 200 XP

### Konzept

Bisher haben deine Programme nur Text AUSGEGEBEN. Aber echte Programme koennen auch EINGABEN vom Benutzer lesen! Dafuer gibt es die Klasse `Scanner`.

**Minecraft-Bezug:**
Stell dir vor, du oeffnest den Chat in Minecraft und tippst einen Befehl wie `/gamemode creative`. Minecraft LIEST deine Eingabe und fuehrt den Befehl aus. Genau das macht der Scanner in Java: Er liest was der Benutzer in der Konsole tippt.

### Wichtige Methoden vom Scanner

```java
import java.util.Scanner;

public class EingabeBeispiel {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);  // Scanner fuer Tastatur-Eingabe

        System.out.print("Dein Name: ");
        String name = scanner.nextLine();          // Liest eine ganze Zeile Text

        System.out.print("Dein Alter: ");
        int alter = scanner.nextInt();             // Liest eine ganze Zahl

        System.out.print("Deine XP: ");
        double xp = scanner.nextDouble();          // Liest eine Kommazahl

        System.out.println("Hallo " + name + ", du bist " + alter + " und hast " + xp + " XP!");

        scanner.close();  // Scanner immer schliessen!
    }
}
```

**Wichtig:** Nach `nextInt()` oder `nextDouble()` bleibt ein unsichtbarer Zeilenumbruch im Speicher. Wenn du danach `nextLine()` benutzen willst, musst du vorher ein extra `scanner.nextLine()` aufrufen, um den Zeilenumbruch zu entfernen!

### Aufgabe 1.1: Spieler-Registrierung

**Ziel:** Erstelle `src/SpielerRegistrierung.java`. Der Benutzer gibt seine Spieler-Daten ein.

**Das Programm soll fragen nach:**
1. Spielername (String)
2. Alter (int)
3. Lieblings-Mob (String)

**Erwartete Ausgabe:**
```
=== SPIELER-REGISTRIERUNG ===
Wie heisst du? Steve
Wie alt bist du? 12
Was ist dein Lieblings-Mob? Creeper

=== DEIN PROFIL ===
Name: Steve
Alter: 12
Lieblings-Mob: Creeper
Willkommen in der Welt, Steve!
```

**Hinweis:** Benutze `System.out.print()` (ohne `ln`) fuer die Fragen, damit der Benutzer in der gleichen Zeile antworten kann. Vergiss nicht: Nach `nextInt()` ein extra `scanner.nextLine()` aufrufen, bevor du wieder `nextLine()` benutzt!

**Ausfuehren:** Klicke ▶ oben in `SpielerRegistrierung.java`.

### Aufgabe 1.2: Schadensrechner mit Eingabe

**Ziel:** Erstelle `src/SchadensrechnerInput.java`. Der Benutzer gibt Werte ein und das Programm berechnet den Schaden.

**Erwartete Ausgabe:**
```
=== SCHADENSRECHNER ===
Basis-Schaden eingeben: 7
Staerke-Bonus eingeben: 3
Gegner-Ruestung eingeben: 4

=== ERGEBNIS ===
Basis-Schaden: 7
Staerke-Bonus: +3
Gesamt-Schaden: 10
Gegner-Ruestung: -4
Effektiver Schaden: 6
```

**Ausfuehren:** Klicke ▶ oben in `SchadensrechnerInput.java`.

### Aufgabe 1.3: Ja/Nein-Abfrage

**Ziel:** Erstelle `src/JaNeinAbfrage.java`. Frage den Benutzer etwas und reagiere auf die Antwort.

**Erwartete Ausgabe:**
```
=== MINECRAFT ABENTEUER ===
Du stehst vor einer Hoehle. Willst du reingehen? (ja/nein): ja
Du gehst mutig in die Hoehle hinein!
Du findest 5 Diamanten!

Willst du tiefer gehen? (ja/nein): nein
Du gehst zurueck zum Eingang. Sicherheit geht vor!
```

**Hinweis:** Benutze `scanner.nextLine()` und vergleiche mit `.equals("ja")`:
```java
String antwort = scanner.nextLine();
if (antwort.equals("ja")) {
    // ...
}
```

**Ausfuehren:** Klicke ▶ oben in `JaNeinAbfrage.java`.

### Quiz Lektion 1

**Frage 1:** Welche Klasse benutzt man fuer Benutzer-Eingaben von der Konsole?
- A) Reader
- B) Scanner
- C) Input
- D) Keyboard

**Frage 2:** Was macht `scanner.nextLine()`?
- A) Liest eine ganze Zahl
- B) Liest eine ganze Zeile Text
- C) Springt zur naechsten Zeile
- D) Schliesst den Scanner

**Frage 3:** Was passiert wenn man `scanner.close()` vergisst?
- A) Das Programm stuerzt sofort ab
- B) Die Ressource bleibt offen (schlecht, aber kein sofortiger Absturz)
- C) Der Text wird nicht ausgegeben
- D) Nichts, close() ist optional

**Frage 4:** Was muss man nach `nextInt()` tun, bevor man `nextLine()` aufruft?
- A) Den Scanner neu erstellen
- B) Ein extra `scanner.nextLine()` aufrufen, um den Zeilenumbruch zu entfernen
- C) `scanner.reset()` aufrufen
- D) Nichts, es funktioniert automatisch

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 1

- [ ] SpielerRegistrierung.java mit 3 Eingaben erstellt und laeuft
- [ ] SchadensrechnerInput.java mit Berechnungen laeuft
- [ ] JaNeinAbfrage.java mit if/else-Reaktion laeuft
- [ ] Scanner erstellen mit `new Scanner(System.in)` verstanden
- [ ] nextLine(), nextInt(), nextDouble() verstanden
- [ ] scanner.close() am Ende aufrufen verstanden

---

## Lektion 2: Textdateien lesen mit Scanner und File

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Lektion 1 abgeschlossen
**Ziel:** Textdateien von der Festplatte lesen und den Inhalt verarbeiten
**Belohnung:** 200 XP

### Konzept

Der Scanner kann nicht nur Tastatur-Eingaben lesen, sondern auch Dateien! Dafuer brauchst du die Klasse `File`, die eine Datei auf deiner Festplatte darstellt.

**Minecraft-Bezug:**
Wenn Minecraft startet, liest es deine `options.txt` Datei, um deine Einstellungen zu laden (Lautstaerke, Tastenbelegung, Grafikeinstellungen). Genau das lernst du jetzt: Daten aus einer Datei lesen!

### Code-Beispiel

```java
import java.util.Scanner;
import java.io.File;

public class DateiLeser {
    public static void main(String[] args) throws Exception {
        File datei = new File("spieler.txt");       // Datei-Objekt erstellen
        Scanner scanner = new Scanner(datei);        // Scanner fuer die Datei

        while (scanner.hasNextLine()) {              // Solange es noch Zeilen gibt
            String zeile = scanner.nextLine();       // Zeile lesen
            System.out.println(zeile);               // Zeile ausgeben
        }

        scanner.close();                             // Scanner schliessen!
    }
}
```

**Wichtig:** Das `throws Exception` hinter `main(...)` ist erstmal noetig, weil beim Datei-Lesen Fehler passieren koennen (z.B. Datei existiert nicht). In Lektion 4 lernst du die bessere Loesung mit try/catch!

### Aufgabe 2.1: Inventar aus Datei lesen

**Ziel:** Erstelle zuerst die Datei `data/inventar.txt` und dann `src/InventarLeser.java`.

**Schritt 1:** Erstelle den Ordner `data/` und darin die Datei `inventar.txt` mit folgendem Inhalt:
```
Diamant-Schwert
Eisenspitzhacke
Bogen
Fackel
Steak
Goldapfel
Schild
Enderperle
```

**Schritt 2:** Erstelle `src/InventarLeser.java` das die Datei liest und nummeriert ausgibt.

**Erwartete Ausgabe:**
```
=== INVENTAR AUS DATEI ===
1. Diamant-Schwert
2. Eisenspitzhacke
3. Bogen
4. Fackel
5. Steak
6. Goldapfel
7. Schild
8. Enderperle
---
Gesamt: 8 Items geladen!
```

**Hinweis:** Benutze einen Zaehler `int nummer = 1;` und erhoehe ihn in der Schleife.

**Ausfuehren:** Klicke ▶ oben in `InventarLeser.java`.

### Aufgabe 2.2: Spieler-Daten aus Datei lesen

**Ziel:** Erstelle `data/spieler.txt` und `src/SpielerLaden.java`.

**Datei `data/spieler.txt`:**
```
Steve
20
1500
true
```

**Das Programm soll die 4 Zeilen lesen und korrekt zuweisen:**
- Zeile 1: Name (String)
- Zeile 2: Leben (int)
- Zeile 3: XP (int)
- Zeile 4: Ist am Leben (boolean)

**Erwartete Ausgabe:**
```
=== SPIELER GELADEN ===
Name: Steve
Leben: 20
XP: 1500
Am Leben: true
Spieler erfolgreich geladen!
```

**Hinweis:** Benutze `Integer.parseInt()` und `Boolean.parseBoolean()` um Strings in Zahlen/Boolean umzuwandeln:
```java
String zeile = scanner.nextLine();
int leben = Integer.parseInt(zeile);
```

**Ausfuehren:** Klicke ▶ oben in `SpielerLaden.java`.

### Aufgabe 2.3: Highscore-Liste lesen

**Ziel:** Erstelle `data/highscores.txt` und `src/HighscoreLeser.java`.

**Datei `data/highscores.txt`:**
```
Alex - 5000
Steve - 3200
Notch - 9999
Jeb - 4100
Dinnerbone - 7500
```

**Das Programm soll die Datei lesen und den hoechsten Score finden.**

**Erwartete Ausgabe:**
```
=== HIGHSCORE-LISTE ===
1. Alex - 5000
2. Steve - 3200
3. Notch - 9999
4. Jeb - 4100
5. Dinnerbone - 7500
---
Hoechster Score: Notch - 9999
Anzahl Spieler: 5
```

**Hinweis:** Du kannst `zeile.split(" - ")` benutzen, um den Namen und den Score zu trennen. Dann mit `Integer.parseInt()` den Score in eine Zahl umwandeln. Merke dir den hoechsten Wert in einer Variablen!

**Ausfuehren:** Klicke ▶ oben in `HighscoreLeser.java`.

### Quiz Lektion 2

**Frage 1:** Welche Klasse repraesentiert eine Datei auf der Festplatte?
- A) Scanner
- B) File
- C) Document
- D) Reader

**Frage 2:** Was macht `scanner.hasNextLine()`?
- A) Liest die naechste Zeile
- B) Prueft ob es noch eine weitere Zeile gibt
- C) Zaehlt die Zeilen
- D) Springt zur naechsten Zeile

**Frage 3:** Was passiert wenn die Datei nicht existiert?
- A) Eine leere Datei wird erstellt
- B) Das Programm gibt null aus
- C) Es gibt einen Fehler (FileNotFoundException)
- D) Nichts passiert

**Frage 4:** Wie wandelt man den String "42" in eine Zahl um?
- A) int zahl = "42";
- B) int zahl = Integer.parseInt("42");
- C) int zahl = (int) "42";
- D) int zahl = String.toInt("42");

**Antworten:** 1-B, 2-B, 3-C, 4-B

### Checkliste Lektion 2

- [ ] inventar.txt erstellt und InventarLeser.java liest sie korrekt
- [ ] spieler.txt erstellt und SpielerLaden.java parst alle Datentypen
- [ ] highscores.txt erstellt und HighscoreLeser.java findet den hoechsten Score
- [ ] File-Objekt erstellen verstanden
- [ ] Scanner mit File benutzen verstanden
- [ ] while-Schleife mit hasNextLine() verstanden
- [ ] Integer.parseInt() und Boolean.parseBoolean() verstanden

---

## Lektion 3: Textdateien schreiben mit FileWriter

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Lektion 2 abgeschlossen
**Ziel:** Daten in Textdateien speichern
**Belohnung:** 200 XP

### Konzept

Bisher konntest du Dateien nur LESEN. Jetzt lernst du, wie du Daten in Dateien SCHREIBST. Dafuer gibt es die Klasse `FileWriter`.

**Minecraft-Bezug:**
Wenn du in Minecraft deine Welt speicherst (Strg+S oder beim Beenden), schreibt das Spiel deine Spieler-Daten, Inventar und Weltdaten in Dateien. Genau das lernst du jetzt!

### Code-Beispiel

```java
import java.io.FileWriter;

public class DateiSchreiber {
    public static void main(String[] args) throws Exception {
        FileWriter writer = new FileWriter("ausgabe.txt");  // Datei erstellen/ueberschreiben

        writer.write("Hallo Welt!\n");          // Text schreiben (\n = neue Zeile)
        writer.write("Zweite Zeile\n");
        writer.write("Dritte Zeile\n");

        writer.close();                          // WICHTIG: Immer schliessen!
        System.out.println("Datei gespeichert!");
    }
}
```

**Wichtig:**
- `new FileWriter("datei.txt")` erstellt eine NEUE Datei oder UEBERSCHREIBT eine vorhandene!
- `new FileWriter("datei.txt", true)` haengt Text an eine vorhandene Datei AN (append).
- `writer.close()` ist PFLICHT! Ohne close() werden die Daten moeglicherweise nicht geschrieben.
- `\n` erzeugt eine neue Zeile in der Datei.

### Aufgabe 3.1: Inventar speichern

**Ziel:** Erstelle `src/InventarSpeichern.java`. Speichere ein Inventar in eine Datei.

**Das Programm soll:**
1. Ein String-Array mit 5 Items erstellen
2. Die Items in die Datei `data/mein_inventar.txt` schreiben (eins pro Zeile)
3. Bestaetigung auf der Konsole ausgeben

**Erwartete Konsolen-Ausgabe:**
```
=== INVENTAR SPEICHERN ===
Schreibe: Diamant-Schwert
Schreibe: Eisenspitzhacke
Schreibe: Bogen
Schreibe: Fackel
Schreibe: Steak
---
5 Items in data/mein_inventar.txt gespeichert!
```

**Erwarteter Datei-Inhalt von `data/mein_inventar.txt`:**
```
Diamant-Schwert
Eisenspitzhacke
Bogen
Fackel
Steak
```

**Hinweis:** Benutze eine for-Schleife ueber das Array und schreibe jedes Item mit `writer.write(item + "\n")`.

**Ausfuehren:** Klicke ▶ oben in `InventarSpeichern.java`.

### Aufgabe 3.2: Spieler-Profil speichern

**Ziel:** Erstelle `src/ProfilSpeichern.java`. Der Benutzer gibt seine Daten ein und sie werden in eine Datei gespeichert.

**Das Programm soll:**
1. Mit Scanner den Namen, das Level und die XP abfragen
2. Die Daten in `data/profil.txt` speichern
3. Bestaetigung ausgeben

**Erwartete Konsolen-Ausgabe:**
```
=== PROFIL SPEICHERN ===
Dein Name: Steve
Dein Level: 5
Deine XP: 1500

Speichere Profil...
Profil gespeichert in data/profil.txt!
```

**Erwarteter Datei-Inhalt von `data/profil.txt`:**
```
Name: Steve
Level: 5
XP: 1500
```

**Ausfuehren:** Klicke ▶ oben in `ProfilSpeichern.java`.

### Aufgabe 3.3: Logbuch schreiben (Anhang-Modus)

**Ziel:** Erstelle `src/Logbuch.java`. Schreibe mehrere Eintraege in ein Logbuch, OHNE die vorherigen zu ueberschreiben.

**Das Programm soll:**
1. Den Benutzer nach einem Logbuch-Eintrag fragen
2. Den Eintrag mit einer Nummer an `data/logbuch.txt` ANHAENGEN
3. Danach fragen ob noch ein Eintrag geschrieben werden soll
4. Am Ende alle Eintraege aus der Datei lesen und anzeigen

**Erwartete Konsolen-Ausgabe (beim ZWEITEN Ausfuehren):**
```
=== LOGBUCH ===
Neuer Eintrag: Diamanten in Hoehle gefunden
Eintrag gespeichert!
Noch ein Eintrag? (ja/nein): ja
Neuer Eintrag: Creeper hat mein Haus zerstoert
Eintrag gespeichert!
Noch ein Eintrag? (ja/nein): nein

=== ALLE EINTRAEGE ===
1. Gold in der Mine gefunden
2. Diamanten in Hoehle gefunden
3. Creeper hat mein Haus zerstoert
Gesamt: 3 Eintraege
```

**Hinweis:** Benutze `new FileWriter("data/logbuch.txt", true)` fuer den Anhang-Modus! Benutze eine while-Schleife fuer die Eingabe:
```java
String weiter = "ja";
while (weiter.equals("ja")) {
    // Eintrag abfragen und schreiben
    System.out.print("Noch ein Eintrag? (ja/nein): ");
    weiter = scanner.nextLine();
}
```

**Ausfuehren:** Klicke ▶ oben in `Logbuch.java`.

### Quiz Lektion 3

**Frage 1:** Welche Klasse benutzt man zum Schreiben in Dateien?
- A) FileReader
- B) FileWriter
- C) Scanner
- D) Printer

**Frage 2:** Was passiert bei `new FileWriter("test.txt")` wenn test.txt schon existiert?
- A) Fehler
- B) Die Datei wird ueberschrieben (alter Inhalt weg!)
- C) Text wird angehaengt
- D) Nichts passiert

**Frage 3:** Wie haengt man Text an eine vorhandene Datei an?
- A) FileWriter("datei.txt", false)
- B) FileWriter("datei.txt", true)
- C) FileWriter("datei.txt").append()
- D) FileAppender("datei.txt")

**Frage 4:** Warum ist `writer.close()` so wichtig?
- A) Nur fuer die Ordnung
- B) Ohne close() werden Daten moeglicherweise nicht in die Datei geschrieben
- C) close() loescht die Datei
- D) Ist nicht wichtig, kann man weglassen

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 3

- [ ] InventarSpeichern.java schreibt ein Array in eine Datei
- [ ] ProfilSpeichern.java kombiniert Scanner-Eingabe mit FileWriter
- [ ] Logbuch.java benutzt den Anhang-Modus (append = true)
- [ ] FileWriter erstellen und benutzen verstanden
- [ ] writer.write() und writer.close() verstanden
- [ ] Unterschied zwischen Ueberschreiben und Anhaengen verstanden

---

## Lektion 4: Try/Catch - Fehlerbehandlung verstehen

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Lektion 3 abgeschlossen
**Ziel:** Verstehen was Exceptions sind und wie man sie mit try/catch behandelt
**Belohnung:** 200 XP

### Konzept

Bisher hast du `throws Exception` hinter main() geschrieben. Das ist wie zu sagen: "Wenn etwas schiefgeht, kuemmere ich mich NICHT darum." Jetzt lernst du die RICHTIGE Art, mit Fehlern umzugehen: **try/catch**.

**Minecraft-Bezug:**
Stell dir vor, du willst einen Block abbauen, aber deine Spitzhacke ist kaputt. Minecraft stuerzt nicht ab! Es zeigt dir einfach an, dass es nicht geht. Das ist Fehlerbehandlung! Das Programm sagt:
- **try:** "Versuche, diesen Block abzubauen..."
- **catch:** "Wenn es nicht klappt (Spitzhacke kaputt), dann zeige eine Nachricht."

### Code-Beispiel

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;

public class TryCatchBeispiel {
    public static void main(String[] args) {
        // OHNE try/catch: Programm stuerzt ab wenn Datei fehlt!
        // MIT try/catch: Programm faengt den Fehler ab.

        try {
            File datei = new File("gibt_es_nicht.txt");
            Scanner scanner = new Scanner(datei);   // HIER koennte der Fehler passieren!
            System.out.println("Datei gefunden!");
            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("Datei nicht gefunden!");
            System.out.println("Fehlermeldung: " + e.getMessage());
        }

        System.out.println("Programm laeuft weiter!");  // Wird trotzdem ausgefuehrt!
    }
}
```

**Wichtig:**
- Der Code im `try`-Block wird VERSUCHT auszufuehren.
- Wenn ein Fehler passiert, springt Java sofort zum `catch`-Block.
- Der Code NACH try/catch laeuft in jedem Fall weiter!
- `e.getMessage()` gibt die genaue Fehlerbeschreibung zurueck.

### Aufgabe 4.1: Sicherer Datei-Leser

**Ziel:** Erstelle `src/SichererLeser.java`. Lese eine Datei mit richtiger Fehlerbehandlung.

**Das Programm soll:**
1. Versuchen, `data/inventar.txt` zu lesen
2. Wenn die Datei existiert: Inhalt ausgeben
3. Wenn die Datei NICHT existiert: Freundliche Fehlermeldung

**Erwartete Ausgabe (wenn Datei existiert):**
```
=== SICHERER DATEI-LESER ===
Versuche data/inventar.txt zu lesen...
1. Diamant-Schwert
2. Eisenspitzhacke
3. Bogen
4. Fackel
5. Steak
Datei erfolgreich gelesen!
```

**Erwartete Ausgabe (wenn Datei NICHT existiert):**
```
=== SICHERER DATEI-LESER ===
Versuche data/gibt_es_nicht.txt zu lesen...
FEHLER: Datei wurde nicht gefunden!
Tipp: Pruefe ob die Datei im richtigen Ordner liegt.
```

**Teste beide Faelle!** Aendere den Dateinamen zu einer Datei die nicht existiert.

**Ausfuehren:** Klicke ▶ oben in `SichererLeser.java`.

### Aufgabe 4.2: Sichere Zahleneingabe

**Ziel:** Erstelle `src/SichereEingabe.java`. Fange Fehler bei falschen Eingaben ab.

**Das Programm soll:**
1. Den Benutzer nach einer Zahl fragen
2. Wenn der Benutzer Text statt einer Zahl eingibt: Fehler abfangen und nochmal fragen
3. Wiederholen bis eine gueltige Zahl eingegeben wird

**Erwartete Ausgabe:**
```
=== SICHERE EINGABE ===
Gib dein Level ein: abc
Das war keine gueltige Zahl! Versuch es nochmal.
Gib dein Level ein: xyz
Das war keine gueltige Zahl! Versuch es nochmal.
Gib dein Level ein: 5
Dein Level: 5
```

**Hinweis:** Benutze eine while-Schleife und fange `NumberFormatException` ab:
```java
boolean gueltig = false;
int level = 0;
while (!gueltig) {
    try {
        System.out.print("Gib dein Level ein: ");
        String eingabe = scanner.nextLine();
        level = Integer.parseInt(eingabe);
        gueltig = true;  // Kein Fehler = gueltig!
    } catch (NumberFormatException e) {
        System.out.println("Das war keine gueltige Zahl! Versuch es nochmal.");
    }
}
```

**Ausfuehren:** Klicke ▶ oben in `SichereEingabe.java`.

### Aufgabe 4.3: Datei lesen ODER erstellen

**Ziel:** Erstelle `src/DateiOderNeu.java`. Wenn eine Datei nicht existiert, erstelle sie mit Standardwerten.

**Das Programm soll:**
1. Versuchen, `data/config.txt` zu lesen
2. Wenn die Datei existiert: Inhalt anzeigen
3. Wenn die Datei NICHT existiert: Die Datei mit Standardwerten erstellen

**Erwartete Ausgabe (erster Start, Datei existiert noch nicht):**
```
=== CONFIG LADEN ===
Versuche data/config.txt zu laden...
Datei nicht gefunden! Erstelle Standardkonfiguration...
Standardkonfiguration gespeichert!

=== AKTUELLE CONFIG ===
spielername=Spieler1
level=1
leben=20
```

**Erwartete Ausgabe (zweiter Start, Datei existiert jetzt):**
```
=== CONFIG LADEN ===
Versuche data/config.txt zu laden...
Config geladen!

=== AKTUELLE CONFIG ===
spielername=Spieler1
level=1
leben=20
```

**Hinweis:** Im catch-Block benutzt du einen FileWriter, um die Datei zu erstellen. Der FileWriter braucht auch ein eigenes try/catch!

**Ausfuehren:** Klicke ▶ oben in `DateiOderNeu.java`.

### Quiz Lektion 4

**Frage 1:** Was passiert wenn im try-Block ein Fehler auftritt?
- A) Das Programm stuerzt ab
- B) Java springt sofort zum catch-Block
- C) Der try-Block wird nochmal ausgefuehrt
- D) Nichts passiert

**Frage 2:** Was gibt `e.getMessage()` zurueck?
- A) Den gesamten Code
- B) Eine Beschreibung des Fehlers
- C) Die Zeilennummer
- D) Den Dateinamen

**Frage 3:** Laeuft Code nach dem try/catch-Block noch?
- A) Nein, das Programm endet
- B) Nur wenn kein Fehler passiert ist
- C) Ja, in jedem Fall
- D) Nur im catch-Block

**Frage 4:** Was ist besser: `throws Exception` oder `try/catch`?
- A) throws Exception ist immer besser
- B) try/catch ist besser, weil du den Fehler selbst behandeln kannst
- C) Beides ist gleich gut
- D) Keines von beiden

**Antworten:** 1-B, 2-B, 3-C, 4-B

### Checkliste Lektion 4

- [ ] SichererLeser.java mit try/catch fuer FileNotFoundException laeuft
- [ ] SichereEingabe.java faengt falsche Eingaben ab und fragt nochmal
- [ ] DateiOderNeu.java erstellt fehlende Datei mit Standardwerten
- [ ] try/catch Grundsyntax verstanden
- [ ] Unterschied zu throws Exception verstanden
- [ ] e.getMessage() benutzt
- [ ] Code laeuft nach try/catch weiter (verstanden)

---

## Lektion 5: Verschiedene Exceptions

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Lektion 4 abgeschlossen
**Ziel:** Die wichtigsten Exception-Typen kennenlernen und gezielt abfangen
**Belohnung:** 200 XP

### Konzept

Es gibt verschiedene Arten von Fehlern in Java. Jeder Fehler hat einen eigenen Namen (Exception-Typ). Je genauer du den Fehler beschreibst, desto besser kannst du darauf reagieren!

**Minecraft-Bezug:**
Minecraft hat verschiedene Arten von "Fehlern" (Gefahren):
- **FileNotFoundException:** Wie wenn du eine Truhe oeffnen willst, die nicht existiert
- **IOException:** Wie wenn du aus einer Truhe lesen willst, aber sie ist gesperrt
- **NumberFormatException:** Wie wenn du "abc" Goldbarren in einen Ofen legen willst - das ist keine gueltige Zahl!
- **ArrayIndexOutOfBoundsException:** Wie wenn du in Hotbar-Slot 10 greifen willst, aber es gibt nur 9

### Die wichtigsten Exceptions

```java
// 1. FileNotFoundException - Datei nicht gefunden
try {
    Scanner scan = new Scanner(new File("gibt_es_nicht.txt"));
} catch (FileNotFoundException e) {
    System.out.println("Datei nicht gefunden!");
}

// 2. IOException - Allgemeiner Ein-/Ausgabe-Fehler
try {
    FileWriter writer = new FileWriter("/unmoeglich/pfad/datei.txt");
} catch (IOException e) {
    System.out.println("Fehler beim Schreiben: " + e.getMessage());
}

// 3. NumberFormatException - Text ist keine gueltige Zahl
try {
    int zahl = Integer.parseInt("abc");
} catch (NumberFormatException e) {
    System.out.println("Das ist keine Zahl!");
}

// 4. ArrayIndexOutOfBoundsException - Index ausserhalb des Arrays
try {
    int[] zahlen = {1, 2, 3};
    System.out.println(zahlen[10]);
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Index existiert nicht!");
}
```

### Mehrere catch-Bloecke

Du kannst mehrere catch-Bloecke haben, um verschiedene Fehler unterschiedlich zu behandeln:

```java
try {
    // Code der verschiedene Fehler verursachen kann
} catch (FileNotFoundException e) {
    System.out.println("Datei nicht gefunden!");
} catch (NumberFormatException e) {
    System.out.println("Ungueltige Zahl!");
} catch (Exception e) {
    System.out.println("Unbekannter Fehler: " + e.getMessage());
}
```

**Wichtig:** Fange SPEZIFISCHE Exceptions zuerst ab! `Exception` (allgemein) kommt immer ZULETZT.

### Aufgabe 5.1: Exception-Tester

**Ziel:** Erstelle `src/ExceptionTester.java`. Erzeuge absichtlich verschiedene Exceptions und fange sie ab.

**Das Programm soll 4 Tests durchfuehren:**

**Erwartete Ausgabe:**
```
=== EXCEPTION TESTER ===

Test 1: FileNotFoundException
Ergebnis: Datei 'phantom.txt' nicht gefunden!

Test 2: NumberFormatException
Ergebnis: 'Hallo' ist keine gueltige Zahl!

Test 3: ArrayIndexOutOfBoundsException
Ergebnis: Index 99 existiert nicht! Array hat nur 3 Elemente.

Test 4: ArithmeticException (Division durch Null)
Ergebnis: Man kann nicht durch Null teilen!

Alle 4 Tests bestanden! Kein Absturz!
```

**Hinweis:** Jeder Test bekommt sein eigenes try/catch:
```java
// Test 1
try {
    Scanner s = new Scanner(new File("phantom.txt"));
} catch (FileNotFoundException e) {
    System.out.println("Ergebnis: Datei 'phantom.txt' nicht gefunden!");
}
```

**Ausfuehren:** Klicke ▶ oben in `ExceptionTester.java`.

### Aufgabe 5.2: Sichere Spieler-Daten laden

**Ziel:** Erstelle `src/SicherLaden.java`. Lade Spieler-Daten aus einer Datei mit umfassender Fehlerbehandlung.

**Erstelle die Datei `data/spieler_daten.txt`:**
```
Steve
20
1500
```

**Das Programm soll:**
1. Die Datei lesen
2. Die Werte parsen (Name, Leben, XP)
3. Verschiedene Fehler einzeln abfangen

**Erwartete Ausgabe (alles korrekt):**
```
=== SPIELER LADEN ===
Lade Daten aus data/spieler_daten.txt...
Name: Steve
Leben: 20
XP: 1500
Spieler erfolgreich geladen!
```

**Erwartete Ausgabe (wenn die Datei fehlt):**
```
=== SPIELER LADEN ===
Lade Daten aus data/spieler_daten.txt...
FEHLER: Speicherdatei nicht gefunden!
Erstelle neuen Spieler mit Standardwerten...
Name: Neuling
Leben: 20
XP: 0
```

**Erwartete Ausgabe (wenn die Datei kaputte Daten hat, z.B. "abc" statt einer Zahl):**
```
=== SPIELER LADEN ===
Lade Daten aus data/spieler_daten.txt...
FEHLER: Speicherdatei enthaelt ungueltige Daten!
Fehlermeldung: For input string: "abc"
Lade Standardwerte...
```

**Teste alle 3 Faelle!** Loesche die Datei, aendere eine Zahl zu Text, etc.

**Ausfuehren:** Klicke ▶ oben in `SicherLaden.java`.

### Aufgabe 5.3: Fehler-Protokoll

**Ziel:** Erstelle `src/FehlerProtokoll.java`. Schreibe aufgetretene Fehler in eine Log-Datei.

**Das Programm soll:**
1. Mehrere riskante Operationen durchfuehren (Dateien lesen, Zahlen parsen)
2. Jeden aufgetretenen Fehler in `data/fehler.log` schreiben
3. Am Ende die Zusammenfassung anzeigen

**Erwartete Konsolen-Ausgabe:**
```
=== FEHLER-PROTOKOLL ===
Teste Operation 1: Datei lesen... FEHLER!
Teste Operation 2: Zahl parsen... FEHLER!
Teste Operation 3: Array-Zugriff... FEHLER!
Teste Operation 4: Division... OK!
---
3 Fehler aufgetreten. Siehe data/fehler.log fuer Details.
1 Operation erfolgreich.
```

**Erwarteter Inhalt von `data/fehler.log`:**
```
FEHLER 1: FileNotFoundException - phantom.txt (Das System kann die angegebene Datei nicht finden)
FEHLER 2: NumberFormatException - For input string: "keine_zahl"
FEHLER 3: ArrayIndexOutOfBoundsException - Index 50 out of bounds for length 3
```

**Ausfuehren:** Klicke ▶ oben in `FehlerProtokoll.java`.

### Quiz Lektion 5

**Frage 1:** Welche Exception tritt auf wenn eine Datei nicht existiert?
- A) IOException
- B) FileNotFoundException
- C) NullPointerException
- D) RuntimeException

**Frage 2:** Welche Exception tritt auf bei `Integer.parseInt("Hallo")`?
- A) IOException
- B) ParseException
- C) NumberFormatException
- D) StringException

**Frage 3:** In welcher Reihenfolge muessen catch-Bloecke stehen?
- A) Egal, Reihenfolge spielt keine Rolle
- B) Spezifische zuerst, allgemeine (Exception) zuletzt
- C) Allgemeine zuerst, spezifische zuletzt
- D) Alphabetisch

**Frage 4:** Was passiert wenn du `catch (Exception e)` als EINZIGEN catch verwendest?
- A) Fehler
- B) Es faengt ALLE Exceptions ab (funktioniert, aber weniger praezise)
- C) Es faengt keine Exception ab
- D) Nur IOExceptions werden gefangen

**Antworten:** 1-B, 2-C, 3-B, 4-B

### Checkliste Lektion 5

- [ ] ExceptionTester.java erzeugt und faengt 4 verschiedene Exceptions ab
- [ ] SicherLaden.java behandelt FileNotFoundException und NumberFormatException
- [ ] FehlerProtokoll.java schreibt Fehler in eine Log-Datei
- [ ] FileNotFoundException, IOException, NumberFormatException kennen
- [ ] ArrayIndexOutOfBoundsException, ArithmeticException kennen
- [ ] Mehrere catch-Bloecke in richtiger Reihenfolge verwenden koennen

---

## Lektion 6: CSV-Dateien lesen und parsen (String.split)

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Lektion 5 abgeschlossen
**Ziel:** Strukturierte Daten aus CSV-Dateien lesen und verarbeiten
**Belohnung:** 200 XP

### Konzept

**CSV** steht fuer "Comma-Separated Values" (durch Komma getrennte Werte). Das ist ein einfaches Format, um Daten wie eine Tabelle zu speichern. Jede Zeile ist ein Eintrag, und die Werte werden durch Kommas getrennt.

**Minecraft-Bezug:**
Stell dir vor, du hast eine Liste aller deiner Verzauberungen gespeichert:
```
Schwert,Schaerfe,5
Bogen,Unendlichkeit,1
Ruestung,Schutz,4
```
Jede Zeile hat: Item, Verzauberung, Stufe. Das ist CSV! Minecraft-Mods speichern Daten oft in aehnlichen Formaten.

### String.split() erklaert

```java
String zeile = "Steve,20,1500,true";
String[] teile = zeile.split(",");     // Teilt den String an jedem Komma

// teile[0] = "Steve"
// teile[1] = "20"
// teile[2] = "1500"
// teile[3] = "true"

String name = teile[0];
int leben = Integer.parseInt(teile[1]);
int xp = Integer.parseInt(teile[2]);
boolean lebt = Boolean.parseBoolean(teile[3]);
```

### Vollstaendiges Beispiel

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;

public class CSVLeser {
    public static void main(String[] args) {
        try {
            Scanner scanner = new Scanner(new File("spieler.csv"));

            while (scanner.hasNextLine()) {
                String zeile = scanner.nextLine();
                String[] teile = zeile.split(",");

                String name = teile[0];
                int level = Integer.parseInt(teile[1]);
                int xp = Integer.parseInt(teile[2]);

                System.out.println(name + " ist Level " + level + " mit " + xp + " XP");
            }

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("CSV-Datei nicht gefunden!");
        }
    }
}
```

### Aufgabe 6.1: Mob-Datenbank lesen

**Ziel:** Erstelle `data/mobs.csv` und `src/MobDatenbank.java`.

**Datei `data/mobs.csv`:**
```
Zombie,20,5,false
Skelett,20,4,true
Creeper,20,25,false
Spinne,16,3,false
Enderman,40,7,true
Wither-Skelett,20,8,true
Hexe,26,6,true
```

**Das Format ist:** Name,HP,Schaden,IstSelten

**Das Programm soll die Datei lesen und uebersichtlich anzeigen.**

**Erwartete Ausgabe:**
```
=== MOB-DATENBANK ===
+-------------------+----+--------+--------+
| Name              | HP | Schaden| Selten |
+-------------------+----+--------+--------+
| Zombie            | 20 |      5 | Nein   |
| Skelett           | 20 |      4 | Ja     |
| Creeper           | 20 |     25 | Nein   |
| Spinne            | 16 |      3 | Nein   |
| Enderman          | 40 |      7 | Ja     |
| Wither-Skelett    | 20 |      8 | Ja     |
| Hexe              | 26 |      6 | Ja     |
+-------------------+----+--------+--------+
Gesamt: 7 Mobs geladen
Durchschnittliche HP: 23
Staerkster Angriff: Creeper mit 25 Schaden
```

**Hinweis:** Fuer die Tabelle reicht einfacher Text mit Leerzeichen. Berechne die Statistiken mit Variablen die du in der Schleife aktualisierst!

**Ausfuehren:** Klicke ▶ oben in `MobDatenbank.java`.

### Aufgabe 6.2: Item-Shop aus CSV

**Ziel:** Erstelle `data/shop.csv` und `src/ItemShop.java`.

**Datei `data/shop.csv`:**
```
Diamant-Schwert,500,7
Eisenspitzhacke,250,4
Bogen,350,5
Goldapfel,100,0
Schild,200,0
Fackel,10,0
```

**Das Format ist:** Name,Preis,Schaden

**Das Programm soll:**
1. Die CSV-Datei laden
2. Den Shop anzeigen
3. Den Benutzer fragen welches Item er kaufen will (nach Nummer)
4. Pruefen ob er genug Gold hat (Startgold: 600)

**Erwartete Ausgabe:**
```
=== ITEM SHOP ===
Dein Gold: 600

Nr. | Item              | Preis | Schaden
----|-------------------|-------|--------
1   | Diamant-Schwert   | 500   | 7
2   | Eisenspitzhacke   | 250   | 4
3   | Bogen             | 350   | 5
4   | Goldapfel         | 100   | 0
5   | Schild            | 200   | 0
6   | Fackel            | 10    | 0

Welches Item kaufen? (1-6): 1
Du kaufst: Diamant-Schwert fuer 500 Gold!
Restgold: 100

Welches Item kaufen? (1-6): 2
Nicht genug Gold! Du brauchst 250, hast aber nur 100.
```

**Hinweis:** Speichere die geladenen Daten in Arrays (oder ArrayList wenn du dich an Phase 3 erinnerst) und benutze die Nummer als Index!

**Ausfuehren:** Klicke ▶ oben in `ItemShop.java`.

### Aufgabe 6.3: Highscore-Analyse

**Ziel:** Erstelle `data/highscores.csv` und `src/HighscoreAnalyse.java`.

**Datei `data/highscores.csv`:**
```
Alex,5000,15,Krieger
Steve,3200,10,Abenteurer
Notch,9999,50,Legende
Jeb,4100,20,Baumeister
Dinnerbone,7500,35,Erforscher
```

**Das Format ist:** Name,Score,Level,Klasse

**Das Programm soll eine vollstaendige Analyse durchfuehren.**

**Erwartete Ausgabe:**
```
=== HIGHSCORE-ANALYSE ===
1. Notch       | 9999 Punkte | Level 50 | Legende
2. Dinnerbone  | 7500 Punkte | Level 35 | Erforscher
3. Alex        | 5000 Punkte | Level 15 | Krieger
4. Jeb         | 4100 Punkte | Level 20 | Baumeister
5. Steve       | 3200 Punkte | Level 10 | Abenteurer

=== STATISTIKEN ===
Hoechster Score: Notch mit 9999
Niedrigster Score: Steve mit 3200
Durchschnitt: 5960 Punkte
Hoechstes Level: Notch (Level 50)
Anzahl Spieler: 5
```

**Hinweis:** Sortieren ist hier optional. Wenn du es versuchen willst, sammle erst alle Daten in Arrays, dann sortiere. Sonst gib die Daten unsortiert aus und finde trotzdem die Statistiken!

**Ausfuehren:** Klicke ▶ oben in `HighscoreAnalyse.java`.

### Quiz Lektion 6

**Frage 1:** Wofuer steht CSV?
- A) Computer System Values
- B) Comma-Separated Values
- C) Code Syntax Variables
- D) Common Storage Version

**Frage 2:** Was macht `"Hallo,Welt,42".split(",")`?
- A) Loescht die Kommas
- B) Erstellt ein Array: {"Hallo", "Welt", "42"}
- C) Gibt "Hallo Welt 42" zurueck
- D) Fehler

**Frage 3:** Wie greift man auf das DRITTE Element nach einem split() zu?
- A) teile[3]
- B) teile[2]
- C) teile.get(3)
- D) teile(2)

**Frage 4:** Was passiert wenn eine CSV-Zeile weniger Werte hat als erwartet?
- A) Die fehlenden Werte werden automatisch aufgefuellt
- B) ArrayIndexOutOfBoundsException wenn man auf den fehlenden Index zugreift
- C) Nichts passiert
- D) Die Zeile wird uebersprungen

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 6

- [ ] MobDatenbank.java liest mobs.csv und zeigt eine formatierte Tabelle
- [ ] ItemShop.java laedt Shop-Daten aus CSV und erlaubt Kauf-Auswahl
- [ ] HighscoreAnalyse.java berechnet Statistiken aus CSV-Daten
- [ ] String.split(",") verstanden und benutzt
- [ ] Daten nach dem Split in richtige Typen umwandeln verstanden
- [ ] CSV-Format (Komma-getrennte Werte) verstanden

---

## Lektion 7: CSV-Dateien schreiben (Daten speichern)

**Dauer:** ca. 60-90 Minuten
**Voraussetzungen:** Lektion 6 abgeschlossen
**Ziel:** Strukturierte Daten im CSV-Format in Dateien speichern
**Belohnung:** 200 XP

### Konzept

In Lektion 6 hast du CSV-Dateien GELESEN. Jetzt lernst du, Daten im CSV-Format zu SCHREIBEN. So kannst du Spielstaende, Inventare und andere Daten dauerhaft speichern.

**Minecraft-Bezug:**
Wenn du in Minecraft "Speichern und Beenden" klickst, schreibt das Spiel alles in Dateien: deine Position, dein Inventar, welche Bloecke platziert wurden. Beim naechsten Start wird alles wieder geladen. Genau das baust du jetzt!

### Code-Beispiel

```java
import java.io.FileWriter;
import java.io.IOException;

public class CSVSchreiber {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("spieler.csv");

            // Kopfzeile (optional, aber hilfreich)
            writer.write("Name,Level,XP\n");

            // Daten schreiben
            writer.write("Steve,5,1500\n");
            writer.write("Alex,12,5000\n");
            writer.write("Notch,99,99999\n");

            writer.close();
            System.out.println("CSV-Datei gespeichert!");

        } catch (IOException e) {
            System.out.println("Fehler beim Speichern: " + e.getMessage());
        }
    }
}
```

### Aufgabe 7.1: Inventar als CSV speichern

**Ziel:** Erstelle `src/InventarCSV.java`. Erstelle ein Inventar und speichere es als CSV.

**Das Programm soll:**
1. Ein Array mit Item-Daten erstellen (Name, Anzahl, Typ)
2. Die Daten in `data/inventar.csv` schreiben
3. Danach die Datei lesen und zur Kontrolle anzeigen

**Erwartete Konsolen-Ausgabe:**
```
=== INVENTAR ALS CSV SPEICHERN ===
Speichere 5 Items...
- Diamant-Schwert,1,Waffe
- Eisenspitzhacke,1,Werkzeug
- Fackel,64,Block
- Steak,32,Nahrung
- Enderperle,16,Spezial
Gespeichert in data/inventar.csv!

=== KONTROLLE - DATEI LESEN ===
Diamant-Schwert   | Anzahl: 1  | Typ: Waffe
Eisenspitzhacke   | Anzahl: 1  | Typ: Werkzeug
Fackel            | Anzahl: 64 | Typ: Block
Steak             | Anzahl: 32 | Typ: Nahrung
Enderperle        | Anzahl: 16 | Typ: Spezial
```

**Hinweis:** Benutze Arrays fuer die Daten und eine Schleife zum Schreiben:
```java
String[] namen = {"Diamant-Schwert", "Eisenspitzhacke", "Fackel", "Steak", "Enderperle"};
int[] anzahlen = {1, 1, 64, 32, 16};
String[] typen = {"Waffe", "Werkzeug", "Block", "Nahrung", "Spezial"};
```

**Ausfuehren:** Klicke ▶ oben in `InventarCSV.java`.

### Aufgabe 7.2: Spieler-Eingabe in CSV speichern

**Ziel:** Erstelle `src/SpielerCSV.java`. Der Benutzer gibt Spieler-Daten ein, die in CSV gespeichert werden.

**Das Programm soll:**
1. Den Benutzer nach Spielerdaten fragen (Name, Level, XP, Klasse)
2. Fragen ob weitere Spieler hinzugefuegt werden sollen
3. Alle Spieler in `data/spieler_liste.csv` speichern
4. Am Ende die gespeicherten Daten anzeigen

**Erwartete Konsolen-Ausgabe:**
```
=== SPIELER-DATENBANK ===
Spieler 1:
  Name: Steve
  Level: 5
  XP: 1500
  Klasse: Krieger
Gespeichert!

Weiteren Spieler hinzufuegen? (ja/nein): ja

Spieler 2:
  Name: Alex
  Level: 12
  XP: 5000
  Klasse: Baumeister
Gespeichert!

Weiteren Spieler hinzufuegen? (ja/nein): nein

=== GESPEICHERTE SPIELER ===
1. Steve | Level 5 | 1500 XP | Krieger
2. Alex | Level 12 | 5000 XP | Baumeister
2 Spieler in data/spieler_liste.csv gespeichert!
```

**Erwarteter Datei-Inhalt von `data/spieler_liste.csv`:**
```
Steve,5,1500,Krieger
Alex,12,5000,Baumeister
```

**Ausfuehren:** Klicke ▶ oben in `SpielerCSV.java`.

### Aufgabe 7.3: Lesen, Aendern, Speichern

**Ziel:** Erstelle `src/DatenEditor.java`. Lese eine CSV-Datei, aendere Werte und speichere sie zurueck.

**Nutze die Datei `data/spieler_liste.csv` aus Aufgabe 7.2 (oder erstelle sie manuell).**

**Das Programm soll:**
1. Die CSV-Datei laden und alle Spieler anzeigen
2. Den Benutzer fragen, welchen Spieler er bearbeiten will (nach Nummer)
3. Den neuen Level-Wert abfragen
4. Die geaenderten Daten zurueck in die Datei speichern

**Erwartete Konsolen-Ausgabe:**
```
=== DATEN-EDITOR ===
Lade data/spieler_liste.csv...

Aktuelle Daten:
1. Steve | Level 5 | 1500 XP | Krieger
2. Alex | Level 12 | 5000 XP | Baumeister

Welchen Spieler bearbeiten? (1-2): 1
Neues Level fuer Steve: 10

Speichere Aenderungen...
Gespeichert!

Aktualisierte Daten:
1. Steve | Level 10 | 1500 XP | Krieger
2. Alex | Level 12 | 5000 XP | Baumeister
```

**Hinweis:** Lade ALLE Zeilen in ein Array (oder ArrayList), aendere den gewuenschten Eintrag, und schreibe dann ALLE Zeilen zurueck in die Datei. Dafuer brauchst du:
1. Erst alle Zeilen lesen und in Arrays speichern
2. Den gewuenschten Eintrag im Array aendern
3. Alle Eintraege wieder in die Datei schreiben

**Ausfuehren:** Klicke ▶ oben in `DatenEditor.java`.

### Quiz Lektion 7

**Frage 1:** Wie schreibt man eine neue Zeile beim FileWriter?
- A) writer.newLine()
- B) writer.write("Text\n")
- C) writer.writeLine("Text")
- D) writer.println("Text")

**Frage 2:** Was passiert wenn du eine vorhandene CSV-Datei mit `new FileWriter("datei.csv")` oeffnest?
- A) Text wird angehaengt
- B) Die Datei wird komplett ueberschrieben
- C) Fehler
- D) Nichts passiert

**Frage 3:** Wie baut man eine CSV-Zeile aus Variablen zusammen?
- A) writer.write(name, level, xp)
- B) writer.write(name + "," + level + "," + xp + "\n")
- C) writer.csv(name, level, xp)
- D) writer.writeCSV(name + level + xp)

**Frage 4:** Warum liest man beim "Lesen-Aendern-Speichern" zuerst ALLE Daten?
- A) Weil man nur eine Datei gleichzeitig oeffnen kann
- B) Weil beim Schreiben die alte Datei ueberschrieben wird
- C) Weil Java das so verlangt
- D) Das muss man nicht

**Antworten:** 1-B, 2-B, 3-B, 4-B

### Checkliste Lektion 7

- [ ] InventarCSV.java speichert Items als CSV und liest sie zur Kontrolle
- [ ] SpielerCSV.java nimmt Benutzer-Eingaben und speichert sie als CSV
- [ ] DatenEditor.java kann Daten lesen, aendern und zurueck speichern
- [ ] CSV-Zeilen aus Variablen zusammenbauen verstanden
- [ ] Workflow "Lesen - Aendern - Speichern" verstanden
- [ ] try/catch beim Schreiben benutzt

---

## Lektion 8: Alles zusammen - Config-System bauen

**Dauer:** ca. 90-120 Minuten
**Voraussetzungen:** Lektion 7 abgeschlossen
**Ziel:** Ein vollstaendiges Config-System bauen das lesen, schreiben und Fehler behandeln kann
**Belohnung:** 200 XP

### Konzept

In dieser letzten Lektion baust du ein richtiges **Config-System**, wie es echte Minecraft-Mods verwenden! Das System kann:
- Eine Config-Datei laden (lesen)
- Werte aendern
- Die Config speichern (schreiben)
- Fehler abfangen (wenn die Datei fehlt oder kaputte Daten enthaelt)
- Eine Standard-Config erstellen (wenn noetig)

**Minecraft-Bezug:**
Jeder Minecraft-Mod hat eine Config-Datei! Zum Beispiel `mod_config.txt`:
```
difficulty=hard
mob_spawn_rate=5
max_players=20
enable_pvp=true
```
Diese Dateien liest der Mod beim Starten und speichert Aenderungen. Genau DAS baust du jetzt!

### Code-Struktur des Config-Systems

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileWriter;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.util.HashMap;

public class ConfigSystem {
    // Speichert alle Config-Eintraege als Schluessel=Wert
    private HashMap<String, String> einstellungen;
    private String dateiPfad;

    public ConfigSystem(String dateiPfad) {
        this.dateiPfad = dateiPfad;
        this.einstellungen = new HashMap<>();
    }

    // Config laden
    public void laden() {
        try {
            Scanner scanner = new Scanner(new File(dateiPfad));
            while (scanner.hasNextLine()) {
                String zeile = scanner.nextLine();
                String[] teile = zeile.split("=");
                if (teile.length == 2) {
                    einstellungen.put(teile[0], teile[1]);
                }
            }
            scanner.close();
            System.out.println("Config geladen!");
        } catch (FileNotFoundException e) {
            System.out.println("Config nicht gefunden. Erstelle Standardwerte...");
            standardwerteSetzen();
            speichern();
        }
    }

    // Config speichern
    public void speichern() {
        try {
            FileWriter writer = new FileWriter(dateiPfad);
            for (String key : einstellungen.keySet()) {
                writer.write(key + "=" + einstellungen.get(key) + "\n");
            }
            writer.close();
            System.out.println("Config gespeichert!");
        } catch (IOException e) {
            System.out.println("Fehler beim Speichern: " + e.getMessage());
        }
    }

    // Wert lesen
    public String getWert(String schluessel) {
        return einstellungen.getOrDefault(schluessel, "unbekannt");
    }

    // Wert setzen
    public void setWert(String schluessel, String wert) {
        einstellungen.put(schluessel, wert);
    }

    // Standardwerte
    private void standardwerteSetzen() {
        einstellungen.put("spielername", "Spieler1");
        einstellungen.put("schwierigkeit", "normal");
        einstellungen.put("leben", "20");
        einstellungen.put("pvp", "false");
    }
}
```

### Aufgabe 8.1: Einfaches Config-System

**Ziel:** Erstelle `src/MeineConfig.java` mit einem einfachen Config-System (OHNE HashMap, nur mit Arrays).

**Das Programm soll:**
1. Versuchen, `data/game_config.txt` zu laden
2. Wenn die Datei nicht existiert: Standardwerte erstellen und speichern
3. Die Config anzeigen
4. Den Benutzer fragen ob er etwas aendern will
5. Aenderungen speichern

**Config-Format (Schluessel=Wert):**
```
spielername=Steve
schwierigkeit=normal
max_leben=20
pvp_aktiv=false
```

**Erwartete Ausgabe (erster Start):**
```
=== GAME CONFIG ===
Lade data/game_config.txt...
Config-Datei nicht gefunden!
Erstelle Standard-Konfiguration...
Standard-Config gespeichert!

Aktuelle Einstellungen:
1. spielername = Steve
2. schwierigkeit = normal
3. max_leben = 20
4. pvp_aktiv = false

Moechtest du etwas aendern? (ja/nein): ja
Welche Einstellung? (1-4): 1
Neuer Wert fuer spielername: Alex
Gespeichert!

Aktualisierte Einstellungen:
1. spielername = Alex
2. schwierigkeit = normal
3. max_leben = 20
4. pvp_aktiv = false
```

**Erwartete Ausgabe (zweiter Start):**
```
=== GAME CONFIG ===
Lade data/game_config.txt...
Config erfolgreich geladen!

Aktuelle Einstellungen:
1. spielername = Alex
2. schwierigkeit = normal
3. max_leben = 20
4. pvp_aktiv = false

Moechtest du etwas aendern? (ja/nein): nein
Bis zum naechsten Mal!
```

**Hinweis:** Du kannst Arrays benutzen:
```java
String[] schluessel = {"spielername", "schwierigkeit", "max_leben", "pvp_aktiv"};
String[] werte = {"Steve", "normal", "20", "false"};
```

**Ausfuehren:** Klicke ▶ oben in `MeineConfig.java`.

### Aufgabe 8.2: Config-Klasse erstellen

**Ziel:** Erstelle `src/GameConfig.java` (die Klasse) und `src/ConfigTest.java` (der Test).

**Klasse GameConfig mit Methoden:**
- `GameConfig(String dateiPfad)` - Konstruktor
- `void laden()` - Datei lesen, bei Fehler Standardwerte setzen
- `void speichern()` - Daten in Datei schreiben
- `String getWert(String schluessel)` - Einen Wert lesen
- `void setWert(String schluessel, String wert)` - Einen Wert aendern
- `void alleAnzeigen()` - Alle Einstellungen anzeigen
- `int getWertAlsInt(String schluessel)` - Wert als int lesen (mit try/catch!)

**Teste in ConfigTest.java:**

**Erwartete Ausgabe:**
```
=== CONFIG-SYSTEM TEST ===

--- Test 1: Config laden ---
Config-Datei nicht gefunden! Erstelle Standardwerte...
Config gespeichert!

--- Test 2: Werte lesen ---
Spielername: Spieler1
Schwierigkeit: normal
Max Leben: 20
PVP aktiv: false

--- Test 3: Werte aendern ---
Aendere Spielername zu 'ProGamer'...
Aendere Schwierigkeit zu 'hard'...
Aendere PVP zu 'true'...
Config gespeichert!

--- Test 4: Geaenderte Config ---
Spielername: ProGamer
Schwierigkeit: hard
Max Leben: 20
PVP aktiv: true

--- Test 5: Config neu laden ---
Config geladen!
Spielername: ProGamer
Schwierigkeit: hard
Alles korrekt gespeichert und geladen!
```

**Ausfuehren:** Klicke ▶ oben in `ConfigTest.java`.

### Aufgabe 8.3: Interaktiver Config-Editor

**Ziel:** Erstelle `src/ConfigEditor.java`. Ein vollstaendiges Programm mit Menue.

**Das Programm soll ein Menue haben:**
1. Alle Einstellungen anzeigen
2. Einstellung aendern
3. Einstellung hinzufuegen
4. Config neu laden
5. Config speichern
6. Beenden

**Erwartete Ausgabe:**
```
=== MINECRAFT CONFIG EDITOR ===
Config geladen! (4 Einstellungen)

Was moechtest du tun?
1. Alle Einstellungen anzeigen
2. Einstellung aendern
3. Neue Einstellung hinzufuegen
4. Config neu laden (aus Datei)
5. Config speichern (in Datei)
6. Beenden

Deine Wahl: 1

=== EINSTELLUNGEN ===
spielername = ProGamer
schwierigkeit = hard
max_leben = 20
pvp_aktiv = true
(4 Einstellungen)

Deine Wahl: 3
Schluessel: render_distance
Wert: 16
Hinzugefuegt: render_distance = 16

Deine Wahl: 5
Config gespeichert! (5 Einstellungen)

Deine Wahl: 6
Auf Wiedersehen!
```

**Hinweis:** Benutze eine while-Schleife fuer das Menue:
```java
boolean laeuft = true;
while (laeuft) {
    // Menue anzeigen
    System.out.print("Deine Wahl: ");
    String wahl = scanner.nextLine();

    if (wahl.equals("1")) {
        // Einstellungen anzeigen
    } else if (wahl.equals("6")) {
        laeuft = false;
    }
    // ...
}
```

**Ausfuehren:** Klicke ▶ oben in `ConfigEditor.java`.

### Quiz Lektion 8

**Frage 1:** Was ist ein typisches Format fuer Config-Dateien?
- A) name:wert
- B) schluessel=wert
- C) <schluessel>wert</schluessel>
- D) schluessel->wert

**Frage 2:** Was soll passieren wenn die Config-Datei beim Laden nicht existiert?
- A) Das Programm soll abstuerzen
- B) Standardwerte erstellen und die Datei neu anlegen
- C) Eine leere Config benutzen
- D) Den Benutzer fragen

**Frage 3:** Warum benutzt man try/catch bei `getWertAlsInt()`?
- A) Weil int-Werte langsam sind
- B) Weil der gespeicherte Wert keine gueltige Zahl sein koennte
- C) Weil Java das fuer ints verlangt
- D) Braucht man nicht

**Frage 4:** Welches Muster (Pattern) benutzt man beim Bearbeiten einer Config?
- A) Nur schreiben
- B) Nur lesen
- C) Laden -> Aendern -> Speichern
- D) Loeschen -> Neu erstellen

**Antworten:** 1-B, 2-B, 3-B, 4-C

### Checkliste Lektion 8

- [ ] MeineConfig.java laedt/erstellt/aendert/speichert eine Config-Datei
- [ ] GameConfig.java Klasse mit allen Methoden erstellt
- [ ] ConfigTest.java testet alle Funktionen der GameConfig-Klasse
- [ ] ConfigEditor.java mit interaktivem Menue laeuft
- [ ] Config laden mit Fehlerbehandlung verstanden
- [ ] Config speichern mit try/catch verstanden
- [ ] Schluessel=Wert Format verstanden und mit split("=") geparst
- [ ] Gesamter Workflow: Laden -> Anzeigen -> Aendern -> Speichern beherrscht

---

## Phase 4 abgeschlossen?

Wenn du alle 8 Lektionen durchgearbeitet hast:

1. Pruefe alle Checklisten - sind alle Punkte abgehakt?
2. Oeffne das **ABSCHLUSSPROJEKT.md**
3. Baue das **Minecraft Spielstand-Manager System**!
4. Zeig deinem Tutor das Ergebnis fuer ein Code-Review

**XP-Zusammenfassung:**
- 8 Lektionen x 200 XP = 1600 XP
- Abschlussprojekt = 1000 XP
- Phase 4 gesamt: 2600 XP moeglich!

### Was du jetzt kannst:

- Scanner fuer Benutzer-Eingaben benutzen
- Textdateien lesen mit Scanner und File
- Textdateien schreiben mit FileWriter
- Fehler abfangen mit try/catch
- Verschiedene Exception-Typen unterscheiden
- CSV-Dateien lesen und parsen mit String.split()
- CSV-Dateien schreiben und Daten speichern
- Ein vollstaendiges Config-System bauen

**Das sind die Faehigkeiten, die du fuer echte Minecraft-Mod-Entwicklung brauchst!**

**Nach dem Abschlussprojekt bist du bereit fuer Phase 5: Minecraft Modding!**
