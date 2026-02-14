# 💾 Phase 4 Abschlussprojekt: Spieler-Verwaltungssystem

## 📋 Phase 4 abgeschlossen - Persisten-Zeit!

Du wirst ein **Spieler-Verwaltungssystem** bauen, das Daten speichert & lädt. Wie ein echtes Spiel!

**Dieses Projekt testet ALLES aus Phase 4:**
- ✅ FileWriter / FileReader
- ✅ Scanner für Input
- ✅ Try / Catch Exception-Handling
- ✅ Dateien schreiben
- ✅ Dateien lesen
- ✅ Fehlerbehandlung
- ✅ Daten formatieren & parsen

---

## 📝 Projektaufgabe: Spieler-DB

### Deine Aufgaben:

#### 1. Klasse `Spieler` erstellen
Mit Eigenschaften:
- `name` (String)
- `level` (int)
- `experience` (int)
- `health` (int)
- `koordinaten` (String) - z.B. "X:100 Y:64 Z:200"

Mit Methoden:
- Konstruktor
- `String toCSV()` - Format: "name,level,exp,hp,xyz"
- `void zeigeInfo()` - Ausgabe
- Getter/Setter

#### 2. Klasse `SpielerverwaltungFileSave`
Speichern/Laden in Datei `spieler.txt`:
- `void speichereSpielerdaten(ArrayList<Spieler> spieler)` - In Datei schreiben
- `ArrayList<Spieler> lade Spielerdaten()` - Aus Datei lesen
- Mit **Exception-Handling** (Try/Catch)

#### 3. Benutzerinteraktion in `main()`
- Menü:
  1. Neuer Spieler
  2. Daten laden
  3. Daten speichern
  4. Alle Spieler zeigen
  5. Beenden
- Mit **Scanner** für Input

#### 4. Datei-Format (spieler.txt)
```
Max,25,5000,100,X:245 Y:64 Z:512
Alex,18,2500,85,X:100 Y:72 Z:100
Sarah,32,8500,120,X:450 Y:80 Z:350
```

---

## 🛠️ Anleitung Schritt-für-Schritt

### Schritt 1: Spieler Klasse

```java
public class Spieler {
    String name;
    int level;
    int experience;
    int health;
    String koordinaten;
    
    // Konstruktor
    public Spieler(String name, int level, int experience, 
                   int health, String koordinaten) {
        this.name = name;
        this.level = level;
        this.experience = experience;
        this.health = health;
        this.koordinaten = koordinaten;
    }
    
    // CSV Format (zum Speichern)
    public String toCSV() {
        return name + "," + level + "," + experience + "," + 
               health + "," + koordinaten;
    }
    
    // Spieler aus CSV String erstellen (parsen)
    public static Spieler fromCSV(String csv) {
        String[] teile = csv.split(",");
        
        String name = teile[0];
        int level = Integer.parseInt(teile[1]);
        int experience = Integer.parseInt(teile[2]);
        int health = Integer.parseInt(teile[3]);
        String koordinaten = teile[4];
        
        return new Spieler(name, level, experience, health, koordinaten);
    }
    
    // Info zeigen
    public void zeigeInfo() {
        System.out.println("👤 " + name);
        System.out.println("   📊 Level: " + level);
        System.out.println("   ⭐ XP: " + experience);
        System.out.println("   ❤️  HP: " + health);
        System.out.println("   📍 Pos: " + koordinaten);
    }
    
    // Getter
    public String getName() { return name; }
    public int getLevel() { return level; }
}
```

### Schritt 2: SpielerverwaltungFileSave Klasse

```java
import java.io.FileWriter;
import java.io.FileReader;
import java.io.BufferedReader;
import java.io.IOException;
import java.util.ArrayList;

public class SpielerverwaltungFileSave {
    
    String dateiname = "spieler.txt";
    
    // Dateipfad (im src/ Ordner)
    String pfad = "spieler.txt";  // Oder "./spieler.txt"
    
    // Spieler SPEICHERN
    public void speichereSpielerdaten(ArrayList<Spieler> spieler) {
        try {
            // FileWriter erstellen
            FileWriter writer = new FileWriter(pfad);
            
            // Jeden Spieler schreiben
            for (Spieler s : spieler) {
                writer.write(s.toCSV() + "\n");
            }
            
            // Datei schließen
            writer.close();
            
            System.out.println("✅ " + spieler.size() + " Spieler gespeichert!");
            
        } catch (IOException e) {
            System.out.println("❌ Fehler beim Speichern: " + e.getMessage());
        }
    }
    
    // Spieler LADEN
    public ArrayList<Spieler> ladeSpieler daten() {
        ArrayList<Spieler> spieler = new ArrayList<Spieler>();
        
        try {
            // FileReader & BufferedReader
            FileReader reader = new FileReader(pfad);
            BufferedReader buffer = new BufferedReader(reader);
            
            String zeile;
            
            // Jede Zeile lesen
            while ((zeile = buffer.readLine()) != null) {
                // Leere Zeilen überspringen
                if (zeile.trim().isEmpty()) {
                    continue;
                }
                
                // CSV parsen
                Spieler s = Spieler.fromCSV(zeile);
                spieler.add(s);
            }
            
            // Schließen
            buffer.close();
            reader.close();
            
            System.out.println("✅ " + spieler.size() + " Spieler geladen!");
            
        } catch (IOException e) {
            System.out.println("⚠️  Datei nicht gefunden oder Fehler: " + 
                             e.getMessage());
            System.out.println("   Starte mit leerer Liste...\n");
        }
        
        return spieler;
    }
    
    // Alle Spieler anzeigen
    public void zeigeSpieler(ArrayList<Spieler> spieler) {
        System.out.println("\n═══════════════════════════════════════════");
        System.out.println("📊 ALLE SPIELER (" + spieler.size() + ")");
        System.out.println("═══════════════════════════════════════════");
        
        if (spieler.isEmpty()) {
            System.out.println("(keine Spieler)");
        } else {
            for (int i = 0; i < spieler.size(); i++) {
                System.out.println("\n[" + (i+1) + "]");
                spieler.get(i).zeigeInfo();
            }
        }
        System.out.println();
    }
}
```

### Schritt 3: Hauptprogramm mit Menü

```java
import java.util.ArrayList;
import java.util.Scanner;

public class SpielerverwaltungMain {
    
    public static void main(String[] args) {
        System.out.println("🎮 *** MINECRAFT SPIELER-VERWALTUNG *** 🎮\n");
        
        // Systeme erstellen
        SpielerverwaltungFileSave manager = new SpielerverwaltungFileSave();
        ArrayList<Spieler> spieler = new ArrayList<Spieler>();
        Scanner input = new Scanner(System.in);
        
        boolean running = true;
        
        while (running) {
            System.out.println("═══════════════════════════════════════════");
            System.out.println("📋 HAUPTMENÜ");
            System.out.println("═══════════════════════════════════════════");
            System.out.println("1️⃣  Neuen Spieler hinzufügen");
            System.out.println("2️⃣  Spielerdaten laden");
            System.out.println("3️⃣  Spielerdaten speichern");
            System.out.println("4️⃣  Alle Spieler anzeigen");
            System.out.println("5️⃣  Beenden");
            System.out.print("\n➡️  Wähle (1-5): ");
            
            String wahl = input.nextLine();
            
            switch (wahl) {
                case "1":
                    neuerSpieler(spieler, input);
                    break;
                    
                case "2":
                    spieler = manager.ladeSpieler daten();
                    break;
                    
                case "3":
                    manager.speichereSpielerdaten(spieler);
                    break;
                    
                case "4":
                    manager.zeigeSpieler(spieler);
                    break;
                    
                case "5":
                    System.out.println("\n👋 Auf Wiedersehen!");
                    running = false;
                    break;
                    
                default:
                    System.out.println("❌ Ungültige Wahl!\n");
            }
        }
        
        input.close();
    }
    
    // Hilfsfunktion: Neuen Spieler erstellen
    static void neuerSpieler(ArrayList<Spieler> spieler, Scanner input) {
        System.out.println("\n📝 Neuen Spieler erstellen:");
        System.out.print("   Name: ");
        String name = input.nextLine();
        
        System.out.print("   Level: ");
        int level = Integer.parseInt(input.nextLine());
        
        System.out.print("   Erfahrung (XP): ");
        int xp = Integer.parseInt(input.nextLine());
        
        System.out.print("   Health (HP): ");
        int hp = Integer.parseInt(input.nextLine());
        
        System.out.print("   Koordinaten (z.B. X:100 Y:64 Z:200): ");
        String pos = input.nextLine();
        
        Spieler s = new Spieler(name, level, xp, hp, pos);
        spieler.add(s);
        
        System.out.println("✅ Spieler hinzugefügt!\n");
        s.zeigeInfo();
        System.out.println();
    }
}
```

### Schritt 4: Datei manuell erstellen (optional)

Erstelle `spieler.txt` im Projekt-Ordner:

```
Max,25,5000,100,X:245 Y:64 Z:512
Alex,18,2500,85,X:100 Y:72 Z:100
Sarah,32,8500,120,X:450 Y:80 Z:350
```

---

## 📊 Bewertungskriterien

| Kriterium | Punkte |
|-----------|--------|
| ✅ Spieler Klasse mit Variablen | 10 |
| ✅ toCSV() / fromCSV() korrekt | 15 |
| ✅ FileWriter speichert korrekt | 15 |
| ✅ FileReader lädt korrekt | 15 |
| ✅ Try/Catch Exception-Handling | 15 |
| ✅ BufferedReader nutzen | 10 |
| ✅ Scanner für Input | 10 |
| ✅ Menü funktioniert | 10 |
| ✅ Datei-Format konsistent | 5 |
| ✅ Code läuft ohne Fehler | 10 |
| **GESAMT** | **115** |

**Bestanden: 80+ Punkte** ✅

---

## 🎯 Anforderungen nach Level

### BRONZE 🥉 (Minimum)
- [ ] Spieler Klasse
- [ ] Einfaches File I/O
- [ ] Try/Catch vorhanden
- [ ] Code kompiliert

### SILBER 🥈 (Gut)
- [ ] toCSV() / fromCSV()
- [ ] Speichern & Laden
- [ ] Menü funktioniert
- [ ] Exception-Handling

### GOLD 🥇 (Sehr Gut!)
- [ ] ALLES aus Silber
- [ ] Zusatz-Features:
  - Spieler löschen
  - Spieler bearbeiten
  - Sortierung (nach Level)
  - Backup-System
  - JSON statt CSV

---

## 🚀 Bonus-Herausforderungen

### Bonus 1: Spieler löschen
```java
case "6":
    System.out.print("Spieler zu löschen: ");
    String toDelete = input.nextLine();
    spieler.removeIf(s -> s.getName().equals(toDelete));
    System.out.println("✅ Gelöst!");
    break;
```

### Bonus 2: Backup-System
```java
public void erstelleBackup() {
    // Kopiere spieler.txt → spieler_backup.txt
}
```

### Bonus 3: JSON Format
```java
// Statt CSV:
// {"name":"Max","level":25,"experience":5000}
```

### Bonus 4: Nach Level sortieren
```java
spieler.sort((a, b) -> Integer.compare(b.getLevel(), a.getLevel()));
```

---

## ✅ Checkliste zum Abhacken

- [ ] Spieler.java erstellt
- [ ] toCSV() / fromCSV() funktioniert
- [ ] SpielerverwaltungFileSave.java erstellt
- [ ] speichereSpielerdaten() funktioniert
- [ ] ladeSpieler daten() funktioniert
- [ ] Try/Catch vorhanden
- [ ] SpielerverwaltungMain.java mit Menü
- [ ] Scanner für Input aktiv
- [ ] Alle Dateien kompilieren
- [ ] Test: Spieler hinzufügen
- [ ] Test: Speichern
- [ ] Test: Laden
- [ ] spieler.txt Datei existiert
- [ ] Bonus-Features gemacht (optional)

---

## 💡 Tipps & Tricks

1. **Try/Catch Struktur**
   ```java
   try {
       // Code der fehler werpen könnte
   } catch (IOException e) {
       System.out.println("Fehler: " + e);
   }
   ```

2. **Dateiformat konsistent**
   - CSV mit Komaa separieren
   - Keine Kommas in Wert!
   - Konstanter Separator

3. **BufferedReader für effizienz**
   ```java
   BufferedReader buffer = new BufferedReader(reader);
   String zeile;
   while ((zeile = buffer.readLine()) != null) {
       // Verarbeite Zeile
   }
   ```

4. **Relative Pfade**
   ```java
   String pfad = "spieler.txt";  // Im root
   String pfad = "src/spieler.txt";  // Im src/
   ```

5. **Integer.parseInt() für Umwandlung**
   ```java
   int level = Integer.parseInt("25");  // String → int
   ```

---

## 🎊 Viel Erfolg!

Du beherrschst jetzt File I/O und Exceptions! 🚀

**Wenn du fertig bist → Du kennst ALLE Grundlagen für Minecraft MDK!**

---

## 📧 Feedback & Code-Review

Nach Fertigstellung:
1. Alle 3 Dateien speichern
2. Kompilieren: `javac src/Spieler.java src/SpielerverwaltungFileSave.java src/SpielerverwaltungMain.java`
3. Testen: `java -cp src SpielerverwaltungMain`
4. Zeig mir: Die 3 `.java` Dateien + spieler.txt + Terminal-Output

Ich gebe dir Feedback zu:
- File I/O Handling
- Exception-Behandlung
- Code-Struktur
- Daten-Format
- Fehlerquellen

**Du packst das! 💪**

---

## 🎮 Nächster Schritt

Nach Phase 4 bist du ready für **Phase 5: Minecraft Modding**!

Phase 5 wird dich lehren:
- Forge/Fabric Framework
- Event-Handling
- Custom Items / Blöcke
- Rezepte
- Dein erstes echtes Mod! 🚀
