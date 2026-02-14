# 🎮 Phase 2: OOP - Detaillierter Lernpfad

## Gamification System
**Freischalten der Lektionen:**
- 🔒 Lektion 1: FREIGESCHALTET ✅
- 🔒 Lektion 2: Schaltet frei, wenn L1 bestanden ✅
- 🔒 Lektion 3: Schaltet frei, wenn L2 bestanden ✅
- 🔒 Lektion 4: Schaltet frei, wenn L3 bestanden ✅
- 🔒 Lektion 5: Schaltet frei, wenn L4 bestanden ✅
- 🔒 Lektion 6: Schaltet frei, wenn L5 bestanden ✅
- 🔒 Lektion 7: Schaltet frei, wenn L6 bestanden ✅
- 🔒 Lektion 8: Schaltet frei, wenn L7 bestanden ✅

---

## Lektion 1: Klassen & Objekte verstehen

**Status:** 🔄 In Bearbeitung...

### Die Idee
Eine **Klasse** ist wie eine Blaupause. Ein **Objekt** ist etwas, das von dieser Blaupause gebaut wird.

**Beispiel - Minecraft:**
- Klasse `Zombie` = Blaupause "wie sieht ein Zombie aus und was kann er tun"
- Objekt `zombie1` = Ein spezieller Zombie in der Welt
- Objekt `zombie2` = Ein anderer spezieller Zombie

### Code-Struktur
```java
public class Zombie {
    // Eigenschaften (Variablen)
    String name;
    int hp;
    int damage;
    
    // Methoden (Funktionen)
    public void angreifen() {
        System.out.println(name + " attackiert!");
    }
    
    public void nimmSchaden(int dmg) {
        hp -= dmg;
        System.out.println(name + " hat noch " + hp + " HP");
    }
}
```

### 📝 Aufgabe 1.1: Deine erste Klasse

**Aufgabe:** Erstelle `Spieler.java` mit einer Spieler-Klasse:

```
=== Spieler-Info ===
Name: Marco
Level: 5
Experience: 1200
```

**Code-Template:**
```java
public class Spieler {
    String name;
    int level;
    int exp;
    
    public void infos() {
        System.out.println("=== Spieler-Info ===");
        System.out.println("Name: " + name);
        System.out.println("Level: " + level);
        System.out.println("Experience: " + exp);
    }
}
```

**Aufgabe:** 
1. Erstelle `Spieler.java` mit der Klasse
2. Erstelle eine `main.java` die:
   - Ein Spieler-Objekt erstellt
   - Die Variablen mit Werten füllt
   - Die `infos()` Methode aufruft

**Deine Lösung:** Zeige mir beide Dateien!

---

### 📝 Aufgabe 1.2: Mehrere Objekte

**Aufgabe:** Erstelle 3 verschiedene Spieler-Objekte und gib ihre Infos aus.

**Deine Lösung:** Zeige mir den Code!

---

## Nach Lektion 1

Du hast verstanden:
- ✅ Was eine Klasse ist
- ✅ Was ein Objekt ist
- ✅ Wie man Klassen definiert
- ✅ Wie man Objekte erstellt

**Nächste:** Lektion 2 - Konstruktoren 🚀

---

## Weitere Lektionen

[Lektionen 2-8 in Kürze...]

---

**Die vollständige Phase 2 ist umfangreich - diese Übersicht zeigt die Struktur.**

Viel Erfolg! 🎉
