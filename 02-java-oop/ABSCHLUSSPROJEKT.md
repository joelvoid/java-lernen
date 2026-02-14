# 🧟 Phase 2 Abschlussprojekt: Zombie Kampfsimulator

## 📋 Phase 2 abgeschlossen - Jetzt wird's spannend!

Du wirst ein **Kampfsystem** bauen, bei dem Spieler gegen Zombies kämpfen. Dieses Projekt testet dein OOP-Wissen!

**Dieses Projekt testet ALLES aus Phase 2:**
- ✅ Klassen erstellen
- ✅ Konstruktoren
- ✅ Instance-Variablen (this)
- ✅ Methoden schreiben
- ✅ Objekte erstellen & nutzen
- ✅ Getter & Setter
- ✅ Vererbung (optional)

---

## 📝 Projektaufgabe: Kampfsimulator

### Deine Aufgaben:

#### 1. Klasse `Charakter` erstellen
Mit diesen Eigenschaften:
- `name` (String)
- `health` (int)
- `damage` (int)
- `level` (int)

Mit diesen Methoden:
- `Charakter(name, health, damage, level)` - Konstruktor
- `boolean istAm Leben()` - Gibt true zurück wenn health > 0
- `void nimmeSchaden(int schaden)` - Zieht Schaden ab
- `void heile(int betrag)` - Heilt den Charakter
- `void zeigeInfo()` - Gibt Name, Health, Damage aus
- `int angreife()` - Gibt zufälligen Schaden zurück (damage ± 5)

#### 2. Klasse `Zombie` erstellen
Erbt von `Charakter` oder hat ähnliche Struktur:
- `String typ` - z.B. "normaler Zombie" oder "schneller Zombie"
- Konstruktor: `Zombie(typ, health, damage)`
- `void zeigeInfo()` - Gibt Zombie-Info aus (anders als Charakter)
- `int angreife()` - Zombie macht Schaden (mit Variabilität)

#### 3. Kampf-System in `main()`
- Spieler vs Zombie erstellen
- Kampfschleife (while):
  - Spieler greift an
  - Schaden anzeigen
  - Check: Ist Zombie am Leben?
  - Zombie greift zurück
  - Check: Ist Spieler am Leben?
  - Runde anzeigen
- Gewinner anzeigen

---

## 🛠️ Anleitung Schritt-für-Schritt

### Schritt 1: Charakter Klasse

```java
public class Charakter {
    
    // Variablen
    protected String name;
    protected int health;
    protected int damage;
    protected int level;
    
    // Konstruktor
    public Charakter(String name, int health, int damage, int level) {
        this.name = name;
        this.health = health;
        this.damage = damage;
        this.level = level;
    }
    
    // Ist noch am Leben?
    public boolean istAmLeben() {
        return health > 0;
    }
    
    // Nimmt Schaden
    public void nimmSchaden(int schaden) {
        health -= schaden;
        if (health < 0) {
            health = 0;
        }
    }
    
    // Heilt sich
    public void heile(int betrag) {
        health += betrag;
    }
    
    // Greift an (random Schaden)
    public int angreife() {
        int varianz = (int)(Math.random() * 11) - 5;  // -5 bis +5
        return damage + varianz;
    }
    
    // Info anzeigen
    public void zeigeInfo() {
        System.out.println("👤 " + name);
        System.out.println("   ❤️  Health: " + health);
        System.out.println("   ⚔️  Damage: " + damage);
        System.out.println("   📊 Level: " + level);
    }
}
```

### Schritt 2: Zombie Klasse

```java
public class Zombie extends Charakter {
    
    String typ;
    
    // Konstruktor
    public Zombie(String typ, int health, int damage) {
        super(typ + "-Zombie", health, damage, 1);  // Level 1
        this.typ = typ;
    }
    
    // Zombie-Info
    @Override
    public void zeigeInfo() {
        System.out.println("🧟 " + name);
        System.out.println("   ❤️  Health: " + health);
        System.out.println("   ⚔️  Schaden: " + damage);
        System.out.println("   Typ: " + typ);
    }
    
    // Zombie greift aggressiver an
    @Override
    public int angreife() {
        // Zombie macht bis zu +2 extra damage
        int varianz = (int)(Math.random() * 8) - 2;
        return damage + varianz;
    }
}
```

### Schritt 3: Kampfsimulator Klasse

```java
public class KampfSimulator {
    
    public static void main(String[] args) {
        
        // Spieler erstellen
        Charakter spieler = new Charakter("Held", 100, 20, 5);
        
        // Zombie erstellen
        Zombie zombie = new Zombie("schnell", 50, 15);
        
        System.out.println("⚔️  *** KAMPF STARTET *** ⚔️\n");
        
        spieler.zeigeInfo();
        System.out.println();
        zombie.zeigeInfo();
        System.out.println();
        
        int runde = 0;
        
        // Kampfschleife
        while (spieler.istAmLeben() && zombie.istAmLeben()) {
            runde++;
            System.out.println("🔄 === RUNDE " + runde + " ===");
            
            // Spieler greift an
            int spielerSchaden = spieler.angreife();
            zombie.nimmSchaden(spielerSchaden);
            System.out.println("💥 " + spieler.name + " macht " + spielerSchaden + " Schaden!");
            System.out.println("   Zombie-Health: " + zombie.health);
            
            if (!zombie.istAmLeben()) {
                break;  // Zombie ist tot
            }
            
            // Zombie greift an
            int zombieSchaden = zombie.angreife();
            spieler.nimmSchaden(zombieSchaden);
            System.out.println("💥 " + zombie.name + " macht " + zombieSchaden + " Schaden!");
            System.out.println("   Spieler-Health: " + spieler.health);
            
            System.out.println();
        }
        
        // Gewinner
        System.out.println("🏆 *** KAMPF ENDE *** 🏆\n");
        
        if (spieler.istAmLeben()) {
            System.out.println("✅ " + spieler.name + " GEWINNT!");
        } else {
            System.out.println("❌ " + zombie.name + " GEWINNT!");
        }
        
        System.out.println();
        spieler.zeigeInfo();
        System.out.println();
        zombie.zeigeInfo();
    }
}
```

---

## 📊 Bewertungskriterien

| Kriterium | Punkte |
|-----------|--------|
| ✅ Charakter Klasse mit Variablen | 15 |
| ✅ Charakter Konstruktor funktioniert | 10 |
| ✅ istAmLeben() Methode korrekt | 10 |
| ✅ nimmSchaden() Methode korrekt | 10 |
| ✅ angreife() mit Randomness | 10 |
| ✅ Zombie Klasse erstellt | 15 |
| ✅ Vererbung nutzen (extends) | 10 |
| ✅ Kampfschleife funktioniert | 10 |
| ✅ Gewinner wird korrekt ermittelt | 10 |
| ✅ Code läuft ohne Fehler | 5 |
| **GESAMT** | **105** |

**Bestanden: 75+ Punkte** ✅

---

## 🎯 Anforderungen nach Level

### BRONZE 🥉 (Minimum)
- [ ] Charakter Klasse mit Konstruktor
- [ ] Zombie Klasse erstellen
- [ ] Kampf-Loop läuft
- [ ] Code kompiliert

### SILBER 🥈 (Gut)
- [ ] ALLE Methoden funktionieren
- [ ] Vererbung nutzen
- [ ] Gewinner wird angezeigt
- [ ] Output ist verständlich

### GOLD 🥇 (Sehr Gut!)
- [ ] ALLES aus Silber
- [ ] Zusatz-Features:
  - Mehrere Zombies hintereinander
  - Spieler kann heilen
  - Unterschiedliche Zombie-Typen
  - Statistiken (Runden, Gesamtschaden)

---

## 🚀 Bonus-Herausforderungen

### Bonus 1: Mehrere Zombies
```java
Zombie[] zombies = new Zombie[3];
zombies[0] = new Zombie("schnell", 50, 15);
zombies[1] = new Zombie("stark", 80, 25);
zombies[2] = new Zombie("normal", 60, 18);

for (Zombie z : zombies) {
    // Gegen jeden kämpfen
}
```

### Bonus 2: Spieler kann heilen
```java
// In der Kampfschleife:
if (spieler.health < 30) {
    spieler.heile(20);
    System.out.println("💚 " + spieler.name + " heilt sich!");
}
```

### Bonus 3: Boss-Zombie
```java
class BossZombie extends Zombie {
    public BossZombie() {
        super("BOSS", 200, 30);
    }
    
    @Override
    public int angreife() {
        // Boss macht doppelten Schaden!
        return super.angreife() * 2;
    }
}
```

---

## ✅ Checkliste zum Abhacken

- [ ] Charakter.java erstellt
- [ ] Zombie.java erstellt
- [ ] KampfSimulator.java erstellt
- [ ] Alle Methoden implementiert
- [ ] Kampf-Loop läuft
- [ ] Gewinner wird angezeigt
- [ ] Code ist kommentiert
- [ ] Alle 3 Dateien kompilieren
- [ ] Programm läuft fehlerfrei
- [ ] Output sieht gut aus
- [ ] Bonus-Features gemacht (optional)

---

## 💡 Tipps & Tricks

1. **this nutzen!** 
   ```java
   this.name = name;  // Unterscheidet Variablen
   ```

2. **super() für Vererbung**
   ```java
   super(name, health, damage, level);  // Ruft Parent-Konstruktor auf
   ```

3. **@Override Annotation**
   - Hilft, Fehler zu erkennen wenn Method falsch überschrieben wird

4. **Teste mit verschiedenen Werten**
   - Spieler zu stark? Zombie zu schwach?
   - Die Zahlen anpassen!

5. **Debuggen mit sysout()**
   ```java
   System.out.println("[DEBUG] spielerSchaden = " + spielerSchaden);
   ```

---

## 🎊 Viel Erfolg!

Du bist jetzt ein OOP-Coder! 🚀

**Wenn du fertig bist → Phase 3 öffnet sich!**

---

## 📧 Feedback & Code-Review

Nach Fertigstellung:
1. Alle 3 Dateien speichern
2. Kompilieren: `javac src/Charakter.java src/Zombie.java src/KampfSimulator.java`
3. Testen: `java -cp src KampfSimulator`
4. Zeig mir: Die 3 `.java` Dateien + Terminal-Output mehrmals

Ich gebe dir Feedback zu:
- OOP-Design
- Code-Struktur
- Vererbun Nutzung
- Performance-Tipps

**Du packst das! 💪**
