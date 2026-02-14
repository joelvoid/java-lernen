# 🎮 Phase 1: Java Basics - Dein Anfang
## Willkommen zum Java-Lernpfad!

Dies ist **Phase 1** des kompletten Java-Lernpfads für Minecraft-Modding.

---

## 📖 Schnelleinstieg (10 Minuten)

### 1️⃣ Schritt 1: VS Code starten & Projekt öffnen

**Was ist VS Code?**
VS Code ist ein **Editor** - ein Programm, in dem du Code schreibst.

**So öffnest du VS Code:**
1. Drücke `Windows-Taste + R`
2. Typ: `code`
3. Drücke `Enter`
4. *Oder* suche "Visual Studio Code" im Windows-Startmenü

**Projekt laden:**
1. Oben im Menü: `File` → `Open Folder`
2. Navigiere zu: `C:\Users\s6n9\Dev\java-lernen\01-java-basics`
3. Klick `Select Folder`
4. ✅ Das Projekt ist jetzt offen!

---

### 2️⃣ Schritt 2: Das Terminal öffnen

**Was ist das Terminal?**
Das Terminal ist eine schwarze Box, in die du Befehle tippen kannst. Damit compilierst & startest du Java-Programme.

**Terminal in VS Code öffnen:**
1. Drücke: `Strg + Ö` (oder `Ctrl + Backtick`)
2. *Oder* oben: `Terminal` → `New Terminal`
3. 👉 Eine schwarze Box öffnet sich unten

**Terminal sieht so aus:**
```
PS C:\Users\s6n9\Dev\java-lernen\01-java-basics>
```

Das `>` Symbol bedeutet: Das Terminal ist bereit für deine Befehle!

---

### 3️⃣ Schritt 3: Erste Datei anschauen

**Im VS Code Explorer (links):**
1. Klick auf `src` Ordner um ihn zu öffnen
2. Du siehst: `HelloWorld.java` ← Dein erstes Programm!
3. Klick drauf um es zu öffnen

**Du siehst jetzt Code:**
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hallo Welt! Mein erstes Java-Programm!");
    }
}
```

Das ist Java-Code! Keine Sorge, du lernst was das alles bedeutet in den Lektionen 😊

---

### 4️⃣ Schritt 4: Programm compilieren & starten

**Im Terminal unten tippst du:**

```bash
javac src/HelloWorld.java
```

Drücke `Enter` - das *compiliert* das Programm (übersetzt es).
- ✅ Wenn nichts passiert → Super, es hat geklappt!
- ❌ Wenn Fehler kommen → Java ist wahrscheinlich nicht installiert

**Jetzt das Programm starten:**

```bash
java -cp src HelloWorld
```

Drücke `Enter` - du solltest sehen:
```
Hallo Welt! Mein erstes Java-Programm!
```

**Glückwunsch! 🎉 Du hast dein erstes Java-Programm ausgeführt!**

---

## 📁 Wie erstellst du neue Dateien?

**Neue `.java` Datei erstellen:**

1. **Im Explorer links:** Rechtsklick auf `src` Ordner
2. Wähle `New File`
3. Typ den Namen, z.B.: `MeineErsteUebung.java`
4. Drücke `Enter`
5. Die Datei öffnet sich - jetzt kannst du Code rein schreiben!

**Wichtig:** Der Name MUSS mit `.java` enden!

**Datei speichern:**
- Drücke `Strg + S` (oder `Cmd + S` auf Mac)
- Der Punkt neben dem Dateinamen verschwindet = gespeichert ✅

---

## 💾 Terminal-Befehle - Die wichtigsten

**Zu Datei navigieren:**
```bash
cd src
```
(Wechselt in den `src` Ordner)

**Zurück einen Ordner nach oben:**
```bash
cd ..
```

**Alle Dateien im Ordner anzeigen:**
```bash
dir
```

**Java-Datei compilieren:**
```bash
javac MeineeDatei.java
```

**Java-Programm ausführen:**
```bash
java MeineeDatei
```

💡 **Tipp:** Mit den **Pfeiltasten (↑↓)** kannst du alte Befehle wieder ansehen!

---

## ❓ Häufige Probleme

### Problem 1: "javac ist kein erkannter Befehl"
**Lösung:** Java ist nicht richtig installiert.
- Download: https://www.oracle.com/java/technologies/downloads/
- Nach Installation: VS Code neustarten

### Problem 2: "Datei nicht gefunden"
**Lösung:** Du bist im falschen Ordner.
Typ im Terminal:
```bash
cd C:\Users\s6n9\Dev\java-lernen\01-java-basics
```

### Problem 3: "Ich sehe meine neue Datei nicht"
**Lösung:** 
- Drücke `F5` um den Explorer zu aktualisieren
- *Oder* speichern mit `Strg + S`

### Problem 4: "Fehler beim Compilieren"
**Schau auf den Fehler:**
- Zeichensalat? → Es ist OK, wir behandeln das später
- Scheint logisch? → Schreib mir den Fehler!

---

## 📊 Phase 1 - Was lernst du?

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | Was ist ein Programm? | Grundlagen |
| 2 | Erste Schritte | System.out.println() |
| 3 | Variablen | int, String, double |
| 4 | Rechnen | +, -, *, / |
| 5 | Entscheidungen | if/else |
| 6 | Schleifen | for-Schleifen |
| 7 | Arrays | Listen & Indizes |
| 8 | Funktionen | Code organisieren |

---

## 🚀 Nächste Schritte

1. ✅ Hast du das Terminal erfolgreich benutzt?
2. ✅ Hast du `HelloWorld` gestartet und Ausgabe gesehen?
3. ✅ Dann bist du bereit für die Lektionen!

**Öffne jetzt:** `LERNPFAD.md` → **Lektion 1**

---

## 📝 Notes

### Nach Phase 1 geht's los!

Nach Lektion 8 + Abschlussprojekt bist du bereit für:

**Phase 2: OOP (Objekt-Orientierte Programmierung)** 🎓
- Klassen & Objekte
- Vererbung
- Polymorphie
- Das ist der Schlüssel für Minecraft-Mods!

---

## 💡 Allgemeine Tipps

✅ **Schreib Code selbst, nicht kopieren**  
✅ **Experimentiere mit Veränderungen**  
✅ **Teste nach jeder Änderung**  
✅ **Frag wenn etwas unklar ist**  

**Los geht's! 🚀**  
✅ Frag bei Problemen sofort!

---

**Viel Spaß! Lass uns starten! 🚀**
