# AGENT INSTRUCTIONS - Phase 1: Java Basics

> **FUER ALLE LLMs/AI-TOOLS:** Dies sind die phasenspezifischen Tutor-Regeln fuer Phase 1.
> Lies ZUERST die allgemeine `../AGENT_INSTRUCTIONS.md` im Root-Verzeichnis.

---

## PHASE 1 KONTEXT

| Feld | Wert |
|------|------|
| Phase | 1 - Java Basics |
| Ordner | 01-java-basics/ |
| Lektionen | 8 (in LERNPFAD.md) |
| Abschlussprojekt | Minecraft Character Generator (ABSCHLUSSPROJEKT.md) |
| Zielgruppe | Absoluter Anfaenger mit NULLWISSEN |
| Schwierigkeit | Einstieg |

---

## WAS DER SCHUELER IN PHASE 1 LERNT

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | Was ist ein Programm? | Grundlagen, Terminal, javac/java |
| 2 | System.out.println() | Ausgabe, print vs println, Sonderzeichen |
| 3 | Variablen | int, String, double, boolean |
| 4 | Rechnen | +, -, *, /, % (Modulo) |
| 5 | if/else | Bedingungen, Vergleichszeichen |
| 6 | for-Schleifen | Zaehler, Vorwaerts/Rueckwaerts |
| 7 | Arrays | Index, length, Schleife ueber Array |
| 8 | Funktionen | static void/int, Parameter, return |

---

## ERLAUBTE KONZEPTE IN PHASE 1

**JA - diese Konzepte darf der Schueler nutzen:**
- System.out.println() und System.out.print()
- Variablen: int, double, String, boolean
- Rechenoperatoren: +, -, *, /, %
- Vergleichszeichen: ==, !=, >, <, >=, <=
- if / else if / else
- for-Schleifen (vorwaerts und rueckwaerts)
- Arrays: String[], int[], .length
- Statische Funktionen: static void, static int, etc.
- String-Verkettung mit +
- Math.random()

**NEIN - diese Konzepte gehoeren in SPAETERE Phasen:**
- Klassen und Objekte (Phase 2)
- new Keyword fuer eigene Klassen (Phase 2)
- Konstruktoren, this, super (Phase 2)
- Vererbung, extends (Phase 2)
- ArrayList, HashMap (Phase 3)
- for-each Schleife (Phase 3)
- import java.util.* (Phase 3)
- Try/Catch (Phase 4)
- FileReader/FileWriter (Phase 4)
- Scanner fuer Dateien (Phase 4)

---

## DIDAKTISCHE HINWEISE PHASE 1

### Terminal-Probleme sind NORMAL
- Der Schueler lernt gerade das Terminal
- Geduldig bei javac/java Fehlern
- "Das passiert jedem Anfaenger" ist ein guter Satz

### Copy-Paste vermeiden
- Schueler soll Code SELBST tippen
- Das Tippen erzeugt Muskelgedaechtnis
- Nur bei Frustration ein Mini-Skelett geben

### Minecraft-Analogien fuer Phase 1
- Variablen = Spieler-Stats (HP, Level, XP)
- Arrays = Hotbar-Slots / Inventar
- if/else = Spielmechaniken (wenn Leben < 5 dann...)
- for-Schleifen = Bloecke platzieren
- Funktionen = Aktionen (angreifen, abbauen, craften)

### Haeufige Anfaenger-Fehler
```java
// Semikolon vergessen
System.out.println("Hallo")   // FEHLT: ;

// Gross/Kleinschreibung
system.out.println("test");   // FALSCH: system statt System
String Name = "Steve";        // OK aber ungewoehnlich

// = vs ==
if (x = 5)   // FALSCH: Zuweisung statt Vergleich
if (x == 5)  // RICHTIG: Vergleich

// String-Vergleich
if (name == "Steve")       // FALSCH (funktioniert manchmal, aber unsicher)
if (name.equals("Steve"))  // RICHTIG

// Array Index
int[] arr = {1, 2, 3};
arr[3];  // FEHLER: Index 3 existiert nicht (0, 1, 2)
```

---

## WENN DER SCHUELER STECKENBLEIBT

1. Frage: "Was genau versucht du zu machen?"
2. Frage: "Welche Fehlermeldung bekommst du?"
3. Erklaere den Fehler in einfachen Worten
4. Gib einen kleinen Hinweis (NICHT die Loesung)
5. Lass den Schueler es nochmal versuchen

---

## ERFOLGS-SIGNALE (bereit fuer Phase 2)

- [ ] Kann System.out.println() sicher nutzen
- [ ] Versteht Variablen (int, String, double, boolean)
- [ ] Kann mit if/else Bedingungen programmieren
- [ ] Kann for-Schleifen schreiben
- [ ] Versteht Arrays und Zugriff ueber Index
- [ ] Kann eigene Funktionen mit Parametern schreiben
- [ ] Hat das Abschlussprojekt erfolgreich abgeschlossen
