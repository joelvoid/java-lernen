# 🎮 Phase 1 Abschlussprojekt: Minecraft Character Generator

## 📋 Großartig! Du hast Phase 1 abgeschlossen!

Nun ist es Zeit für dein **Abschlussprojekt**. Du wirst ein Programm erstellen, das einen Minecraft-Charakter mit zufälligen Stats generiert.

**Dieses Projekt testet ALLES aus Phase 1:**
- ✅ System.out.println() (Ausgabe)
- ✅ Variablen (int, String, double)
- ✅ Rechnen mit Java (Math/Berechnungen)
- ✅ if/else Bedingungen
- ✅ for Schleifen
- ✅ Arrays
- ✅ Funktionen (Methoden)

---

## 📝 Projektaufgabe: Character Generator

### Was soll das Programm tun?

Schreibe ein Programm `CharacterGenerator.java`, das:

1. **Einen Charakter mit Basis-Stats erstellt** (Variablen):
   - Name (String) - Du kannst selbst einen Namen eingeben
   - Level (int) - Zwischen 1-50
   - Health Points (HP) - Zwischen 20-100
   - Mana Points (MP) - Zwischen 10-50
   - Erfahrung (XP) - Zwischen 0-1000

2. **Waffenset generiert** (Arrays):
   - Minestens 3 verschiedene Waffen in einem Array speichern
   - Z.B.: ["Schwert", "Bogen", "Schaufel"]

3. **Stats mit Formeln berechnet** (Rechnen + if/else):
   - Schadensleistung (Damage) = (Level * 2) + 5
   - Magischer Schaden = MP / 2
   - Lebens-Multiplikator: wenn Level > 30, dann HP * 1.5 (Berechnung)

4. **Klasse bestimmen** (if/else):
   - Wenn HP > 60 → "Krieger"
   - Wenn MP > 30 → "Magier"
   - Ansonsten → "Schütze"

5. **Charakter-Übersicht ausdrucken** (System.out.println()),
   - In gutem Format mit Dashes/Linien

6. **Eine Funktion erstellen** (Methode):
   ```java
   void zeigeStats() {
       // Hier kommt die schöne Ausgabe hin
   }
   ```

---

## 🛠️ Anleitung Schritt-für-Schritt

### Schritt 1: Neue Datei erstellen
```bash
# In VS Code im src/ Ordner:
# Rechtsklick → New File → CharacterGenerator.java
```

### Schritt 2: Basis-Gerüst schreiben
```java
public class CharacterGenerator {
    
    // VARIABLEN für den Charakter
    String charName = "Mein Charakter";
    int level = 15;
    int healthPoints = 75;
    int manaPoints = 35;
    double experience = 500;
    
    // WAFFEN-ARRAY
    String[] waffen = {"Schwert", "Bogen", "Schaufel"};
    
    // BERECHNETE WERTE
    int damage;
    double magicDamage;
    int finalHP;
    String characterClass;
    
    // FUNKTIONEN
    void berechneStats() {
        // Hier kommt deine Berechnung hin
    }
    
    void zeigeStats() {
        // Hier kommt die Ausgabe hin
    }
    
    public static void main(String[] args) {
        // Programm starten
    }
}
```

### Schritt 3: berechneStats() ausfüllen
```java
void berechneStats() {
    // Damage berechnen
    damage = (level * 2) + 5;
    
    // Magic Damage berechnen
    magicDamage = manaPoints / 2.0;
    
    // HP anpassen wenn Level > 30
    if (level > 30) {
        finalHP = (int)(healthPoints * 1.5);
    } else {
        finalHP = healthPoints;
    }
    
    // Klasse bestimmen
    if (finalHP > 60) {
        characterClass = "Krieger";
    } else if (manaPoints > 30) {
        characterClass = "Magier";
    } else {
        characterClass = "Schütze";
    }
}
```

### Schritt 4: zeigeStats() ausfüllen
```java
void zeigeStats() {
    System.out.println("╔════════════════════════════════════╗");
    System.out.println("║  ⚔️  MINECRAFT CHARACTER  ⚔️  ║");
    System.out.println("╚════════════════════════════════════╝");
    System.out.println();
    System.out.println("👤 Name: " + charName);
    System.out.println("📊 Level: " + level);
    System.out.println("❤️  HP: " + finalHP);
    System.out.println("💜 Mana: " + manaPoints);
    System.out.println("⭐ XP: " + experience);
    System.out.println("🎯 Klasse: " + characterClass);
    System.out.println();
    System.out.println("⚔️  Damage: " + damage);
    System.out.println("✨ Magic Damage: " + magicDamage);
    System.out.println();
    System.out.println("🗡️  Waffen:");
    
    // SCHLEIFE um Waffen zu zeigen
    for (int i = 0; i < waffen.length; i++) {
        System.out.println("   " + (i+1) + ". " + waffen[i]);
    }
    
    System.out.println();
    System.out.println("╔════════════════════════════════════╗");
}
```

### Schritt 5: main() ausfüllen
```java
public static void main(String[] args) {
    CharacterGenerator character = new CharacterGenerator();
    character.berechneStats();
    character.zeigeStats();
}
```

### Schritt 6: Kompilieren und Testen
```bash
javac src/CharacterGenerator.java
java -cp src CharacterGenerator
```

---

## 📊 Bewertungskriterien

Dein Programm ist erfolgreich, wenn:

| Kriterium | Punkte |
|-----------|--------|
| ✅ Alle Variablen definiert (Name, Level, HP, MP, XP) | 10 |
| ✅ Waffen-Array mit mindestens 3 Elementen | 10 |
| ✅ Damage korrekt berechnet (Level*2+5) | 15 |
| ✅ if/else Klassen-Logik funktioniert | 15 |
| ✅ berechneStats() Methode existiert und wird aufgerufen | 15 |
| ✅ zeigeStats() Methode existiert und wird aufgerufen | 15 |
| ✅ for-Schleife zeigt alle Waffen | 10 |
| ✅ Programm kompiliert ohne Fehler | 5 |
| **GESAMT** | **95** |

**Bestanden: 70+ Punkte** ✅

---

## 🎯 Anforderungen PRO Level

### BRONZE 🥉 (Minimum)
- [ ] Alle Basis-Variablen vorhanden
- [ ] berechneStats() läuft
- [ ] zeigeStats() gibt etwas aus
- [ ] Programm kompiliert

### SILBER 🥈 (Gut)
- [ ] ALLE Berechnungen korrekt
- [ ] if/else Klassen-Logik vollständig
- [ ] Waffen-Array mit Schleife
- [ ] Schöne formatierte Ausgabe

### GOLD 🥇 (Sehr Gut!)
- [ ] ALLES aus Silber
- [ ] Zusätz-Features:
  - Random Stats (Math.random())
  - Mehrere Charaktere generieren
  - Charakter-Vergleich (wer stärker?)
  - Waffen-Upgrade-System

---

## 🚀 Bonus-Herausforderungen

Wenn du fertig bist und Zeit hast:

### Bonus 1: Zufälligkeit hinzufügen
```java
// Waffle Level random
level = (int)(Math.random() * 50) + 1;  // Zwischen 1 und 50
```

### Bonus 2: Mehrere Charaktere
Erstelle 3 Charaktere und zeig ihre Stats!

### Bonus 3: Vergleich
```java
void vergleicheMit(CharacterGenerator anderer) {
    if (this.damage > anderer.damage) {
        System.out.println(charName + " ist stärker!");
    } else {
        System.out.println(anderer.charName + " ist stärker!");
    }
}
```

---

## ✅ Checkliste zum Abhacken

- [ ] CharacterGenerator.java erstellt
- [ ] Alle Variablen definiert
- [ ] berechneStats() fertig
- [ ] zeigeStats() fertig
- [ ] main() aufgerufen
- [ ] Programm kompiliert
- [ ] Programm läuft ohne Fehler
- [ ] Output sieht gut aus
- [ ] Code ist kommentiert (optional aber gut!)
- [ ] Bonus-Features gemacht (optional)

---

## 💡 Tipps & Tricks

1. **Kommentiere deinen Code!**
   ```java
   // Das ist ein Kommentar
   /* Das auch */
   ```

2. **Teste mit verschiedenen Werten**
   - Level 5 vs Level 50
   - HP 20 vs HP 100

3. **Wenn etwas nicht funktioniert:**
   - Schreib Zwischenausgaben: `System.out.println("Debug: " + damage);`
   - Schau auf Tippfehler
   - Datei neu speichern

4. **Ausgabe schön machen:**
   - Nutze `\n` für neue Zeilen (oder einfach mehrere println)
   - Unicode Characters: ⚔️ ❤️ 💜 ✨ 🗡️ u.v.m.

---

## 🎊 Viel Erfolg!

Dieses Projekt ist DEIN Beweis, dass du Phase 1 verstanden hast.
Wenn du es schaffst → **Phase 2 öffnet sich!** 🚀

**Zeig mir dein Abschlussprojekt, wenn du fertig bist!**

---

## 📧 Feedback & Code-Review

Nach Fertigstellung:
1. Speichere deine Datei
2. Kompiliere: `javac src/CharacterGenerator.java`
3. Teste: `java -cp src CharacterGenerator`
4. Zeig mir: Die `.java` Datei + Terminal-Output

Ich gebe dir Feedback zu:
- Lesbarkeit
- Logik-Korrektheit
- Best Practices
- Verbesserungsvorschläge

**Du packst das! 💪**
