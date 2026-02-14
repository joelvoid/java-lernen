# AGENT INSTRUCTIONS - Phase 2: OOP (Objekt-Orientierte Programmierung)

> **FUER ALLE LLMs/AI-TOOLS:** Dies sind die phasenspezifischen Tutor-Regeln fuer Phase 2.
> Lies ZUERST die allgemeine `../AGENT_INSTRUCTIONS.md` im Root-Verzeichnis.

---

## PHASE 2 KONTEXT

| Feld | Wert |
|------|------|
| Phase | 2 - OOP |
| Ordner | 02-java-oop/ |
| Lektionen | 8 (in LERNPFAD.md) |
| Abschlussprojekt | Zombie Kampfsimulator (ABSCHLUSSPROJEKT.md) |
| Voraussetzung | Phase 1 komplett (Variablen, if/else, Schleifen, Arrays, Funktionen) |
| Schwierigkeit | Mittel - OOP ist SCHWER fuer Anfaenger! |

---

## WAS DER SCHUELER IN PHASE 2 LERNT

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | Klassen und Objekte | class, new, Eigenschaften, Methoden |
| 2 | Konstruktoren | Werte beim Erstellen setzen |
| 3 | this-Keyword | Eigenes Objekt referenzieren |
| 4 | Getter und Setter | private/public, Kapselung |
| 5 | Methoden vertiefen | Objekte als Parameter, Interaktion |
| 6 | Vererbung | extends, super(), protected |
| 7 | @Override | Methoden ueberschreiben, Polymorphie |
| 8 | Alles zusammen | Mini-RPG Projekt |

---

## ERLAUBTE KONZEPTE IN PHASE 2

**JA - alles aus Phase 1 PLUS:**
- Klassen definieren (class)
- Objekte erstellen (new)
- Eigenschaften (Instanzvariablen)
- Methoden (nicht-statisch)
- Konstruktoren
- this und super
- private, protected, public
- Getter und Setter
- Vererbung (extends) - maximal 1 Ebene tief
- @Override
- Objekt-Arrays (Mob[] mobs)

**NEIN - diese Konzepte gehoeren in SPAETERE Phasen:**
- ArrayList, HashMap (Phase 3)
- for-each Schleife (Phase 3)
- import java.util.ArrayList/HashMap (Phase 3)
- Abstrakte Klassen (zu komplex)
- Interfaces (zu komplex)
- Generics `<T>` (Phase 3)
- Try/Catch (Phase 4)
- File I/O (Phase 4)
- Design Patterns (zu fortgeschritten)
- Nested/Inner Classes (zu komplex)

---

## DIDAKTISCHE HINWEISE PHASE 2

### OOP ist der WICHTIGSTE Schritt
- Wenn der Schueler OOP nicht versteht, scheitern Minecraft-Mods
- Lieber langsam und gruendlich als schnell und oberflaechlich
- Jedes Konzept mit Minecraft-Beispielen erklaeren

### Minecraft-Analogien fuer Phase 2
- Klasse = Blaupause/Bauplan (Zombie-Template)
- Objekt = Konkretes Ding (ein bestimmter Zombie in der Welt)
- Konstruktor = Spawn-Vorgang (Zombie bekommt HP, Position, etc.)
- this = "meine eigenen" Werte
- Vererbung = Mob -> Zombie, Creeper, Skelett (alle sind Mobs)
- @Override = Gleiche Aktion, anderes Verhalten (alle greifen an, aber anders)

### Haeufige Anfaenger-Fehler
```java
// new vergessen
Spieler s = Spieler();        // FALSCH
Spieler s = new Spieler();    // RICHTIG

// this vergessen im Konstruktor
class Mob {
    String name;
    Mob(String name) {
        name = name;           // FALSCH: Parameter weist sich selbst zu
        this.name = name;      // RICHTIG
    }
}

// Konstruktor mit void
class Mob {
    void Mob() { }             // FALSCH: Das ist eine Methode, kein Konstruktor!
    Mob() { }                  // RICHTIG: Kein Rueckgabetyp
}

// private von aussen
spieler.leben = 50;            // FEHLER wenn leben private ist
spieler.setLeben(50);          // RICHTIG: ueber Setter

// super() vergessen
class Zombie extends Mob {
    Zombie(String name) {
        // FEHLER: Eltern-Konstruktor nicht aufgerufen
        super(name, 20);       // RICHTIG
    }
}
```

### Vererbung nicht uebertreiben
- Maximal 1 Vererbungsebene: Mob -> Zombie (NICHT Mob -> Zombie -> FastZombie -> BurningFastZombie)
- Einfach halten!

---

## WENN DER SCHUELER STECKENBLEIBT

### "Ich verstehe Klassen nicht"
-> "Stell dir vor du baust ein Haus. Der Bauplan ist die Klasse. Das echte Haus ist das Objekt. Du kannst mit EINEM Bauplan viele Haeuser bauen!"

### "Was ist this?"
-> "Wenn ein Zombie sagt 'mein Name', meint er SEINEN Namen. this = mein/meine."

### "Warum brauche ich Getter/Setter?"
-> "Stell dir vor jeder koennte deine HP auf 9999 setzen. Das waere unfair! Mit private und Settern kontrollierst du WER WAS aendern darf."

### "Was ist extends/super?"
-> "In Minecraft sind Zombie, Skelett und Creeper alle Mobs. Sie ERBEN die Mob-Eigenschaften (HP, Schaden) und fuegen eigene hinzu."

---

## ERFOLGS-SIGNALE (bereit fuer Phase 3)

- [ ] Kann Klassen mit Eigenschaften und Methoden erstellen
- [ ] Nutzt Konstruktoren mit this korrekt
- [ ] Versteht private/public und nutzt Getter/Setter
- [ ] Kann einfache Vererbung mit extends/super nutzen
- [ ] Kann @Override fuer verschiedenes Verhalten nutzen
- [ ] Kann Objekte in Arrays speichern und iterieren
- [ ] Hat das Abschlussprojekt erfolgreich abgeschlossen
