# 🎮 Phase 3: Collections & Datenstrukturen
## Arbeiten mit größeren Datenmengen

**Voraussetzung:** Phase 1 & 2 abgeschlossen ✅

---

## 📊 Phase 3 - Was lernst du?

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | ArrayList Basics | Dynamische Arrays |
| 2 | ArrayList Methoden | add, remove, get |
| 3 | for-each Schleife | Einfacher iterieren |
| 4 | HashMap | Schlüssel-Wert-Paare |
| 5 | Iterator | Durch Collections gehen |
| 6 | Minecraft Beispiele | Inventar als HashMap |
| 7 | Mini-Projekt | Dein Inventar-System |
| 8 | Performance | Wann welche Collection? |

---

## 🎯 Warum Collections?

**Problem mit Arrays:**
```java
String[] items = new String[5];  // Größe 5, nicht flexibel!
```

**Lösung mit ArrayList:**
```java
ArrayList<String> items = new ArrayList<>();  // Wächst automatisch!
items.add("Schwert");
items.add("Gold");
items.remove(0);  // Löschen leicht gemacht
```

---

## 📚 Die wichtigsten Collections

### ArrayList - "Dynamisches Array"
```java
ArrayList<String> items = new ArrayList<>();
items.add("Schwert");
items.size();  // 1
items.get(0);  // "Schwert"
items.remove(0);  // Löscht erstes Element
```

### HashMap - "Wörterbuch"
```java
HashMap<String, Integer> inventory = new HashMap<>();
inventory.put("Gold", 100);
inventory.put("Diamanten", 5);
inventory.get("Gold");  // 100
```

---

## 🚀 Start mit Phase 3

1. Diese Phase öffnen in VS Code:
   `java-lernen/03-java-collections`

2. README.md lesen

3. Mit Lektion 1 starten

---

## 🎯 Abschlussprojekt

Nach den 8 Lektionen öffne **`ABSCHLUSSPROJEKT.md`** 🎮

Baue ein **Minecraft Inventarsystem** mit:
- ArrayList für Inventar-Slots
- HashMap für Lagerverwaltung
- Item-Management

**Dein erstes Data-Structure Projekt!**

## ⏰ Zeitrahmen

- **Zeit pro Lektion:** 40-50 Minuten
- **Pro Woche:** 2-3 Lektionen
- **Gesamt:** 2-3 Wochen

---

## ✅ Checkliste am Ende

- [ ] ArrayList verwenden ✅
- [ ] HashMap verwenden ✅
- [ ] for-each Schleife ✅
- [ ] Iterator verstehen ✅
- [ ] Praktische Anwendung ✅

---

**Nach Phase 3 verstehst du, wie man mit vielen Daten umgeht!** 🚀
