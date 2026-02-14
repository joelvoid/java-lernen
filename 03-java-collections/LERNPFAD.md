# 🎮 Phase 3: Collections - Detaillierter Lernpfad

## Gamification System
**Freischalten der Lektionen:**
- 🔒 Lektion 1: FREIGESCHALTET ✅
- 🔒 Lektion 2: Schaltet frei, wenn L1 bestanden ✅
- 🔒 Lektion 3-8: Nachfolgende Lektionen
- 🔓 BONUS: Mini-Projekt

---

## Lektion 1: ArrayList - Dynamische Arrays

**Status:** 🔄 In Bearbeitung...

### Das Problem mit Arrays
```java
String[] items = new String[5];  // Fest: nur 5 Elemente!
```

### Die Lösung: ArrayList
```java
ArrayList<String> items = new ArrayList<>();  // Beliebig viele!
items.add("Schwert");
items.add("Gold");
System.out.println(items.size());  // 2
```

### Wichtige Methoden
```java
ArrayList<String> list = new ArrayList<>();

list.add("Element");        // Hinzufügen
list.get(0);                // Abrufen
list.remove(0);             // Löschen
list.size();                // Größe
list.contains("Element");   // Enthalten?
```

### 📝 Aufgabe 1.1: Inventar mit ArrayList

**Aufgabe:** Erstelle `Inventar.java`:

```
=== Mein Inventar ===
1. Schwert
2. Gold
3. Diamanten
4. Schaufel
5. Kohle
Gesamt: 5 Items
```

**Code-Template:**
```java
import java.util.ArrayList;

public class Inventar {
    public static void main(String[] args) {
        ArrayList<String> items = new ArrayList<>();
        
        items.add("Schwert");
        items.add("Gold");
        // ... mehr hinzufügen
        
        System.out.println("=== Mein Inventar ===");
        for (int i = 0; i < items.size(); i++) {
            System.out.println((i + 1) + ". " + items.get(i));
        }
        System.out.println("Gesamt: " + items.size() + " Items");
    }
}
```

**Deine Lösung:** Zeige mir den Code!

---

### 📝 Aufgabe 1.2: Items hinzufügen & löschen

**Aufgabe:** Erweitere das Programm:
- Füge 2 Items hinzu
- Lösche 1 Item
- Gib das Inventar 2x aus (vorher/nachher)

**Deine Lösung:** Zeige mir den Code!

---

## Weitere Lektionen

[Lektionen 2-8 in Kürze...]

---

**Die vollständige Phase 3 Struktur ist ähnlich wie Phase 2.**

Viel Erfolg! 🎉
