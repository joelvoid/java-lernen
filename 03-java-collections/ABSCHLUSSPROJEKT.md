# 🎒 Phase 3 Abschlussprojekt: Minecraft Inventarsystem

## 📋 Phase 3 abgeschlossen - Sammel-Quest beginnt!

Du wirst ein **realistisches Inventarsystem** bauen wie in Minecraft. Gegenstände sammeln, lagern, tauschen!

**Dieses Projekt testet ALLES aus Phase 3:**
- ✅ ArrayList verwenden
- ✅ HashMap verwenden
- ✅ add() / remove() / get()
- ✅ for-each Schleifen
- ✅ Iterator (optional)
- ✅ Collections durchsuchen
- ✅ Daten speichern & abrufen

---

## 📝 Projektaufgabe: Inventarsystem

### Deine Aufgaben:

#### 1. Klasse `Item` erstellen
```java
public class Item {
    String name;
    int menge;  // Wie viel davon
    int maxStack;  // Max pro Slot
    String rarität;  // "common", "rare", "epic"
    
    // Konstruktor, zeigeInfo(), etc.
}
```

#### 2. Klasse `Inventar`
- ArrayList von Items
- Max 27 Slots (wie Minecraft)
- Methoden:
  - `void addItem(Item item)` - Item hinzufügen
  - `boolean removeItem(String name)` - Item entfernen
  - `Item findeItem(String name)` - Item suchen
  - `void zeigeAlleItems()` - Alle Items anzeigen
  - `int zaehlePlatz()` - Verbleibender Platz

#### 3. Klasse `ItemLager` (mit HashMap)
- HashMap um Items nach Name zu speichern
- "Diamanten" → 64
- "Holz" → 32
- etc.
- Methoden:
  - `void lagerItem(String name, int menge)` - Item lagern
  - `int getItemMenge(String name)` - Menge abrufen
  - `void zeigeLager()` - Alle Items im Lager

#### 4. Kampf-Szenario in `main()`
- Spieler sammelt Items in verschiedenen Biomen
- Items ins Inventar
- Wenn Inventar voll → ins Lager
- Statistiken zeigen

---

## 🛠️ Anleitung Schritt-für-Schritt

### Schritt 1: Item Klasse

```java
public class Item {
    String name;
    int menge;
    int maxStack;
    String rarität;
    
    // Konstruktor
    public Item(String name, int menge, int maxStack, String rarität) {
        this.name = name;
        this.menge = menge;
        this.maxStack = maxStack;
        this.rarität = rarität;
    }
    
    // Info anzeigen
    public void zeigeInfo() {
        String icon = "📦";
        if (rarität.equals("rare")) { icon = "💎"; }
        if (rarität.equals("epic")) { icon = "⭐"; }
        
        System.out.println(icon + " " + name + " x" + menge + 
                         " (max " + maxStack + ") - " + rarität);
    }
    
    // Getter
    public String getName() { return name; }
    public int getMenge() { return menge; }
}
```

### Schritt 2: Inventar Klasse

```java
import java.util.ArrayList;

public class Inventar {
    ArrayList<Item> items;
    int maxSlots = 27;  // Minecraft Standard
    
    // Konstruktor
    public Inventar() {
        items = new ArrayList<Item>();
    }
    
    // Item hinzufügen
    public void addItem(Item item) {
        if (items.size() < maxSlots) {
            items.add(item);
            System.out.println("✅ " + item.getName() + " hinzugefügt!");
        } else {
            System.out.println("❌ Inventar voll!");
        }
    }
    
    // Item entfernen
    public boolean removeItem(String name) {
        for (int i = 0; i < items.size(); i++) {
            if (items.get(i).getName().equals(name)) {
                items.remove(i);
                System.out.println("🗑️  " + name + " entfernt!");
                return true;
            }
        }
        System.out.println("❌ Item nicht gefunden!");
        return false;
    }
    
    // Item suchen
    public Item findeItem(String name) {
        for (Item item : items) {
            if (item.getName().equals(name)) {
                return item;
            }
        }
        return null;
    }
    
    // Alle Items zeigen
    public void zeigeAlleItems() {
        System.out.println("═══════════════════════════════");
        System.out.println("🎒 INVENTAR (" + items.size() + "/" + maxSlots + ")");
        System.out.println("═══════════════════════════════");
        
        if (items.isEmpty()) {
            System.out.println("(leer)");
        } else {
            int slot = 1;
            for (Item item : items) {
                System.out.print("[" + slot + "] ");
                item.zeigeInfo();
                slot++;
            }
        }
        System.out.println();
    }
    
    // Verbleibenden Platz zählen
    public int zaehlePlatz() {
        return maxSlots - items.size();
    }
}
```

### Schritt 3: ItemLager Klasse (HashMap)

```java
import java.util.HashMap;

public class ItemLager {
    HashMap<String, Integer> lager;
    
    // Konstruktor
    public ItemLager() {
        lager = new HashMap<String, Integer>();
    }
    
    // Item lagern
    public void lagerItem(String name, int menge) {
        if (lager.containsKey(name)) {
            int aktuelle = lager.get(name);
            lager.put(name, aktuelle + menge);
        } else {
            lager.put(name, menge);
        }
        System.out.println("💾 " + menge + "x " + name + " gelagert!");
    }
    
    // Item-Menge abrufen
    public int getItemMenge(String name) {
        if (lager.containsKey(name)) {
            return lager.get(name);
        }
        return 0;
    }
    
    // Alle Items zeigen
    public void zeigeLager() {
        System.out.println("═══════════════════════════════");
        System.out.println("🏠 LAGER (" + lager.size() + " Arten)");
        System.out.println("═══════════════════════════════");
        
        if (lager.isEmpty()) {
            System.out.println("(leer)");
        } else {
            // HashMap durchlaufen mit for-each
            for (String name : lager.keySet()) {
                int menge = lager.get(name);
                System.out.println("📦 " + name + " x" + menge);
            }
        }
        System.out.println();
    }
    
    // Gesamt-Items
    public int getGesamt() {
        int gesamt = 0;
        for (int menge : lager.values()) {
            gesamt += menge;
        }
        return gesamt;
    }
}
```

### Schritt 4: Haupt-Programm

```java
public class InventarSimulator {
    
    public static void main(String[] args) {
        System.out.println("🎮 *** MINECRAFT SAMMLER-ABENTEUER *** 🎮\n");
        
        // Systeme erstellen
        Inventar inventar = new Inventar();
        ItemLager lager = new ItemLager();
        
        // Biom 1: Wald - Items sammeln
        System.out.println("🌳 === BIOM 1: WALD ===\n");
        inventar.addItem(new Item("Holz", 32, 64, "common"));
        inventar.addItem(new Item("Blätter", 16, 64, "common"));
        inventar.addItem(new Item("Apfel", 8, 64, "common"));
        inventar.zeigeAlleItems();
        
        // Biom 2: Mine - Mehr Items
        System.out.println("⛏️  === BIOM 2: MINE ===\n");
        inventar.addItem(new Item("Kohle", 32, 64, "common"));
        inventar.addItem(new Item("Eisen", 16, 64, "rare"));
        inventar.addItem(new Item("Diamanten", 4, 64, "epic"));
        inventar.addItem(new Item("Gold", 12, 64, "rare"));
        inventar.zeigeAlleItems();
        
        // Biom 3: Ozean - Inventar wird voll!
        System.out.println("🌊 === BIOM 3: OZEAN ===\n");
        inventar.addItem(new Item("Fisch", 24, 64, "common"));
        inventar.addItem(new Item("Segelkraut", 20, 64, "common")); // Inventar voll!
        
        System.out.println("Platz übrig: " + inventar.zaehlePlatz() + "\n");
        inventar.zeigeAlleItems();
        
        // Items ins Lager
        System.out.println("📦 === ITEMS INS LAGER ===\n");
        lager.lagerItem("Holz", inventar.findeItem("Holz").getMenge());
        inventar.removeItem("Holz");
        
        lager.lagerItem("Kohle", 32);
        inventar.removeItem("Kohle");
        
        lager.lagerItem("Diamanten", 4);
        inventar.removeItem("Diamanten");
        
        lager.lagerItem("Eisen", 16);
        inventar.removeItem("Eisen");
        
        System.out.println();
        
        // Finale Anzeige
        System.out.println("🎯 === FINALE STATISTIK ===\n");
        inventar.zeigeAlleItems();
        lager.zeigeLager();
        
        System.out.println("═══════════════════════════════");
        System.out.println("📊 ZUSAMMENFASSUNG:");
        System.out.println("   Inventar: " + inventar.items.size() + "/" + 
                          inventar.maxSlots + " Slots");
        System.out.println("   Lager: " + lager.getGesamt() + " Items");
        System.out.println("═══════════════════════════════");
    }
}
```

---

## 📊 Bewertungskriterien

| Kriterium | Punkte |
|-----------|--------|
| ✅ Item Klasse mit Variablen | 10 |
| ✅ Inventar Klasse mit ArrayList | 15 |
| ✅ addItem() funktioniert korrekt | 12 |
| ✅ removeItem() funktioniert korrekt | 12 |
| ✅ findeItem() / Suche funktioniert | 10 |
| ✅ ItemLager Klasse mit HashMap | 15 |
| ✅ lagerItem() funktioniert | 10 |
| ✅ Storage und Abruf korrekt | 10 |
| ✅ for-each Schleifen nutzen | 8 |
| ✅ Code läuft ohne Fehler | 7 |
| **GESAMT** | **109** |

**Bestanden: 75+ Punkte** ✅

---

## 🎯 Anforderungen nach Level

### BRONZE 🥉 (Minimum)
- [ ] Item Klasse
- [ ] Inventar mit ArrayList
- [ ] addItem() und removeItem()
- [ ] Code kompiliert

### SILBER 🥈 (Gut)
- [ ] ALLE ArrayList-Methoden
- [ ] ItemLager mit HashMap
- [ ] Alle Methoden funktionieren
- [ ] Output ist verständlich

### GOLD 🥇 (Sehr Gut!)
- [ ] ALLES aus Silber
- [ ] Zusatz-Features:
  - Item-Suchfunktion erweitert
  - Stack-Management
  - Tauschen zwischen Inventar & Lager
  - Sortierung (nach Rarität)

---

## 🚀 Bonus-Herausforderungen

### Bonus 1: Item-Slots (Max Stack)
```java
public void addItem(Item item) {
    for (Item existing : items) {
        if (existing.getName().equals(item.getName())) {
            if (existing.getMenge() < existing.getMaxStack()) {
                // Zum existierenden Stack hinzufügen
                existing.menge += item.menge;
                return;
            }
        }
    }
    // Neuer Slot
    items.add(item);
}
```

### Bonus 2: Tauschen zwischen Inventar & Lager
```java
public void transferZumLager(String itemName, ItemLager lager) {
    Item item = findeItem(itemName);
    if (item != null) {
        lager.lagerItem(itemName, item.getMenge());
        removeItem(itemName);
    }
}
```

### Bonus 3: Sortierung nach Rarität
```java
public void sortierNachRarität() {
    // Alle "epic" oben, dann "rare", dann "common"
    ArrayList<Item> sorted = new ArrayList<Item>();
    // ... Sortier-Logik ...
}
```

---

## ✅ Checkliste zum Abhacken

- [ ] Item.java erstellt
- [ ] Inventar.java mit ArrayList
- [ ] ItemLager.java mit HashMap
- [ ] InventarSimulator.java erstellt
- [ ] addItem() funktioniert
- [ ] removeItem() funktioniert
- [ ] findeItem() funktioniert
- [ ] lagerItem() funktioniert
- [ ] for-each Schleifen aktiv
- [ ] Alles kompiliert
- [ ] Test mit mehreren Items
- [ ] Bonus-Features gemacht (optional)

---

## 💡 Tipps & Tricks

1. **ArrayList vs HashMap**
   - ArrayList: Geordnete Liste (Inventar)
   - HashMap: Schnelle Suche nach Schlüssel (Lager)

2. **for-each in HashMap**
   ```java
   for (String key : hashmap.keySet()) {
       int value = hashmap.get(key);
   }
   ```

3. **contains() nutzen**
   ```java
   if (lager.containsKey("Holz")) {
       // Existiert schon
   }
   ```

4. **isEmpty() prüfen**
   ```java
   if (inventar.items.isEmpty()) {
       System.out.println("Leer!");
   }
   ```

---

## 🎊 Viel Erfolg!

Du beherrschst jetzt Collections! 🚀

**Wenn du fertig bist → Phase 4 öffnet sich!**

---

## 📧 Feedback & Code-Review

Nach Fertigstellung:
1. Alle 4 Dateien speichern
2. Kompilieren: `javac src/Item.java src/Inventar.java src/ItemLager.java src/InventarSimulator.java`
3. Testen: `java -cp src InventarSimulator`
4. Zeig mir: Die 4 `.java` Dateien + Terminal-Output

Ich gebe dir Feedback zu:
- ArrayList/HashMap Nutzung
- Datenstruktur-Design
- Effizienz
- Best Practices

**Du packst das! 💪**
