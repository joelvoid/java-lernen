# 🎮 Phase 4: I/O & Exceptions - Detaillierter Lernpfad

## Gamification System
**Freischalten der Lektionen:**
- 🔒 Lektion 1: FREIGESCHALTET ✅
- 🔒 Lektion 2-8: Nachfolgende Lektionen

---

## Lektion 1: Textdateien lesen mit Scanner

**Status:** 🔄 In Bearbeitung...

### Wie man Dateien liest
```java
import java.util.Scanner;
import java.io.File;

File file = new File("meine_datei.txt");
Scanner scanner = new Scanner(file);

while (scanner.hasNextLine()) {
    String line = scanner.nextLine();
    System.out.println(line);
}
scanner.close();
```

### 📝 Aufgabe 1.1: Deine erste Datei lesen

**Aufgabe:**

1. Erstelle eine Datei `items.txt` mit:
   ```
   Schwert
   Gold
   Diamanten
   Schaufel
   ```

2. Erstelle `FileReader.java` das diese Datei liest und ausgibt:
   ```
   === Mein Inventar ===
   1. Schwert
   2. Gold
   3. Diamanten
   4. Schaufel
   ```

**Code-Template:**
```java
import java.util.Scanner;
import java.io.File;

public class FileReader {
    public static void main(String[] args) throws Exception {
        File file = new File("items.txt");
        Scanner scanner = new Scanner(file);
        
        System.out.println("=== Mein Inventar ===");
        int count = 1;
        while (scanner.hasNextLine()) {
            String item = scanner.nextLine();
            System.out.println(count + ". " + item);
            count++;
        }
        scanner.close();
    }
}
```

**Deine Lösung:** Zeige mir den Code!

---

### 📝 Aufgabe 1.2: Mit Try/Catch

**Aufgabe:** Erweitere das Programm mit Fehlerbehandlung:

```java
try {
    // Datei lesen
} catch (FileNotFoundException e) {
    System.out.println("Datei nicht gefunden: " + e.getMessage());
} catch (Exception e) {
    System.out.println("Fehler: " + e.getMessage());
}
```

**Deine Lösung:** Zeige mir den Code!

---

## Weitere Lektionen

[Lektionen 2-8 in Kürze...]

---

**Die vollständige Phase 4 mit allen Lektionen folgt.**

Viel Erfolg! 🎉
