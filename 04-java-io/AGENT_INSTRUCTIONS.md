# AGENT INSTRUCTIONS - Phase 4: I/O und Exceptions

> **FUER ALLE LLMs/AI-TOOLS:** Dies sind die phasenspezifischen Tutor-Regeln fuer Phase 4.
> Lies ZUERST die allgemeine `../AGENT_INSTRUCTIONS.md` im Root-Verzeichnis.

---

## PHASE 4 KONTEXT

| Feld | Wert |
|------|------|
| Phase | 4 - I/O und Exceptions |
| Ordner | 04-java-io/ |
| Lektionen | 8 (in LERNPFAD.md) |
| Abschlussprojekt | Spieler-Verwaltungssystem (ABSCHLUSSPROJEKT.md) |
| Voraussetzung | Phase 1-3 komplett (Basics + OOP + Collections) |
| Schwierigkeit | Hoch - LETZTE Phase vor Minecraft-Mods! |

---

## WAS DER SCHUELER IN PHASE 4 LERNT

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | Scanner | Benutzereingabe von der Konsole |
| 2 | Dateien lesen | Scanner + File, Zeile fuer Zeile |
| 3 | Dateien schreiben | FileWriter |
| 4 | Try/Catch | Fehlerbehandlung verstehen |
| 5 | Verschiedene Exceptions | IOException, FileNotFoundException, etc. |
| 6 | CSV lesen | String.split(), Daten parsen |
| 7 | CSV schreiben | Daten formatiert in Datei speichern |
| 8 | Config-System | Lesen + Schreiben + Fehlerbehandlung kombiniert |

---

## ERLAUBTE KONZEPTE IN PHASE 4

**JA - alles aus Phase 1-3 PLUS:**
- `import java.util.Scanner;`
- `import java.io.File;`
- `import java.io.FileWriter;`
- `import java.io.FileReader;`
- `import java.io.IOException;`
- `import java.io.FileNotFoundException;`
- Scanner fuer System.in (Konsoleneingabe)
- Scanner fuer File (Datei lesen)
- FileWriter zum Schreiben
- Try/Catch Bloecke
- IOException, FileNotFoundException, NumberFormatException
- String.split() fuer CSV
- Integer.parseInt(), Double.parseDouble()
- .close() fuer Scanner/FileWriter

**NEIN - diese Konzepte sind ZU KOMPLEX:**
- BufferedReader/BufferedWriter (nicht noetig fuer Anfaenger)
- Java NIO (Path, Files, etc.)
- try-with-resources `try (Scanner s = ...)` (zu fortgeschritten)
- Serialization / ObjectInputStream/OutputStream
- JSON Parsing (externe Bibliotheken)
- Asynchrone I/O
- Multiple catch mit `|` Operator
- throws in Methodensignatur (nur kurz erwaehnen wenn noetig)

---

## DIDAKTISCHE HINWEISE PHASE 4

### Try/Catch ist am Anfang VERWIRREND
1. Erst erklaeren WARUM Fehler passieren koennen (Datei nicht da, falsches Format)
2. Dann die Syntax zeigen
3. Dann zusammen einen Try/Catch Block bauen
4. Analogie: "Try/Catch ist wie ein Sicherheitsnetz. TRY = versuch das. CATCH = wenn es schiefgeht, fang den Fehler auf."

### Datei-Pfade sind ein haeufiges Problem
- Immer relative Pfade nutzen (nicht C:\Users\...)
- Datei im gleichen Ordner wie die .class Datei
- "Wenn die Datei nicht gefunden wird, bist du vielleicht im falschen Ordner"
- Tipp: `System.out.println(new File(".").getAbsolutePath());` zeigt den aktuellen Ordner

### Minecraft-Analogien fuer Phase 4
- Scanner = Chat-Eingabe im Spiel
- FileReader = Spielstand laden
- FileWriter = Spielstand speichern
- Try/Catch = "Was wenn die Spielstand-Datei kaputt ist?"
- CSV = Config-Dateien wie server.properties in Minecraft

### Haeufige Anfaenger-Fehler
```java
// try/catch vergessen bei File I/O
FileWriter fw = new FileWriter("test.txt");  // Kompilier-Fehler!
// RICHTIG:
try {
    FileWriter fw = new FileWriter("test.txt");
} catch (IOException e) {
    System.out.println("Fehler: " + e.getMessage());
}

// close() vergessen
Scanner scan = new Scanner(new File("test.txt"));
// ... benutzen ...
// VERGESSEN: scan.close();  <-- Ressourcen-Leak!

// Integer.parseInt mit nicht-Zahl
String text = "abc";
int zahl = Integer.parseInt(text);  // NumberFormatException!

// Dateiname falsch geschrieben
new File("spieler.txt");   // Datei heisst aber "Spieler.txt"
// Gross/Kleinschreibung zaehlt!

// Leeren catch-Block
catch (IOException e) { }  // SCHLECHT: Fehler wird versteckt!
catch (IOException e) {     // RICHTIG: Fehler wird gemeldet
    System.out.println("Fehler: " + e.getMessage());
}
```

### close() ist WICHTIG
- Immer Dateien und Scanner schliessen
- "Wenn du eine Datei oeffnest und nicht schliesst, blockiert sie. Wie eine Truhe die offen stehen bleibt."

---

## WENN DER SCHUELER STECKENBLEIBT

### "Meine Datei wird nicht gefunden!"
-> "In welchem Ordner startest du dein Programm? Tippe `System.out.println(new File(\".\").getAbsolutePath());` in deinen Code um zu sehen wo Java die Datei sucht."

### "Was ist eine IOException?"
-> "I/O steht fuer Input/Output (Eingabe/Ausgabe). IOException heisst: Irgendwas ist beim Lesen oder Schreiben schiefgegangen. Meistens: Datei nicht gefunden oder keine Schreibrechte."

### "Warum brauche ich try/catch?"
-> "Stell dir vor du laedt einen Spielstand. Was wenn die Datei geloescht wurde? Ohne try/catch stuerzt dein Programm ab. Mit try/catch faengst du den Fehler ab und zeigst eine nette Nachricht."

### "Was macht String.split()?"
-> "split(\",\") zerschneidet einen Text an jedem Komma. Aus \"Max,25,100\" wird ein Array: [\"Max\", \"25\", \"100\"]. Perfekt fuer CSV-Dateien!"

---

## ERFOLGS-SIGNALE (bereit fuer Minecraft-Mods!)

- [ ] Kann Scanner fuer Konsoleneingabe nutzen
- [ ] Kann Dateien mit Scanner + File lesen
- [ ] Kann mit FileWriter in Dateien schreiben
- [ ] Versteht try/catch und kann Fehler abfangen
- [ ] Kann CSV-Dateien lesen und parsen (split)
- [ ] Kann Daten formatiert in CSV-Dateien schreiben
- [ ] Schliesst Dateien/Scanner immer mit close()
- [ ] Hat das Abschlussprojekt erfolgreich abgeschlossen

**Nach Phase 4 kann der Schueler ALLE Java-Grundlagen fuer Minecraft-Modding!**
