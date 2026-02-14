# AGENT INSTRUCTIONS - Phase 3: Collections und Datenstrukturen

> **FUER ALLE LLMs/AI-TOOLS:** Dies sind die phasenspezifischen Tutor-Regeln fuer Phase 3.
> Lies ZUERST die allgemeine `../AGENT_INSTRUCTIONS.md` im Root-Verzeichnis.

---

## PHASE 3 KONTEXT

| Feld | Wert |
|------|------|
| Phase | 3 - Collections |
| Ordner | 03-java-collections/ |
| Lektionen | 8 (in LERNPFAD.md) |
| Abschlussprojekt | Minecraft Inventarsystem (ABSCHLUSSPROJEKT.md) |
| Voraussetzung | Phase 1 + 2 komplett (Basics + OOP) |
| Schwierigkeit | Mittel-Hoch |

---

## WAS DER SCHUELER IN PHASE 3 LERNT

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | ArrayList Grundlagen | Dynamische Listen vs Array |
| 2 | ArrayList Methoden | add, remove, get, set, contains, size, indexOf |
| 3 | for-each Schleife | Einfacher ueber Collections iterieren |
| 4 | ArrayList mit Objekten | ArrayList<Spieler>, ArrayList<Item> |
| 5 | HashMap Grundlagen | Schluessel-Wert-Paare |
| 6 | HashMap Methoden | put, get, containsKey, keySet, values, remove |
| 7 | HashMap mit Objekten | Komplexe Werte in HashMap |
| 8 | Collections kombinieren | ArrayList + HashMap zusammen |

---

## ERLAUBTE KONZEPTE IN PHASE 3

**JA - alles aus Phase 1+2 PLUS:**
- `import java.util.ArrayList;`
- `import java.util.HashMap;`
- ArrayList<String>, ArrayList<Integer>, ArrayList<eigeneKlasse>
- HashMap<String, Integer>, HashMap<String, eigeneKlasse>
- ArrayList-Methoden: add(), get(), remove(), size(), contains(), isEmpty(), indexOf(), set()
- HashMap-Methoden: put(), get(), containsKey(), containsValue(), keySet(), values(), remove(), size()
- for-each Schleife: `for (String item : liste) { }`
- Iterator (einfache Form)
- Generics in Grundform: `<String>`, `<Integer>`, `<eigeneKlasse>`

**NEIN - diese Konzepte sind ZU KOMPLEX:**
- Generics selbst definieren `<T>` (zu abstrakt)
- Set, Queue, Deque, LinkedList, TreeMap (nicht noetig)
- Lambda Expressions `->` (zu fortgeschritten)
- Stream API `.stream().filter()...` (zu fortgeschritten)
- Collections.sort() mit Comparator (zu komplex)
- Verschachtelte Collections: `ArrayList<HashMap<...>>` (zu komplex)
- Try/Catch (Phase 4)
- File I/O (Phase 4)

---

## DIDAKTISCHE HINWEISE PHASE 3

### Reihenfolge ist WICHTIG
1. Zuerst ArrayList komplett meistern (Lektion 1-4)
2. DANN erst HashMap (Lektion 5-7)
3. Zum Schluss kombinieren (Lektion 8)
- HashMap NICHT einfuehren bevor ArrayList sitzt!

### Minecraft-Analogien fuer Phase 3
- ArrayList = Inventar-Slots (geordnete Liste, wachst dynamisch)
- HashMap = Truhen-Lager (Item-Name -> Anzahl, schnelles Nachschlagen)
- for-each = "Fuer jedes Item im Inventar, mache..."
- ArrayList<Item> = Inventar mit richtigen Item-Objekten

### Haeufige Anfaenger-Fehler
```java
// Generics vergessen
ArrayList items = new ArrayList();          // FALSCH (funktioniert, aber unsicher)
ArrayList<String> items = new ArrayList<>(); // RICHTIG

// Array-Syntax auf ArrayList
items[0];        // FALSCH
items.get(0);    // RICHTIG

// int statt Integer bei ArrayList
ArrayList<int> zahlen;      // FALSCH (primitive Typen gehen nicht)
ArrayList<Integer> zahlen;  // RICHTIG (Wrapper-Klasse)

// HashMap ohne Generics
HashMap map = new HashMap();                    // FALSCH
HashMap<String, Integer> map = new HashMap<>(); // RICHTIG

// containsKey vs get bei HashMap
int wert = map.get("Gold");  // FEHLER wenn "Gold" nicht existiert -> null
// BESSER:
if (map.containsKey("Gold")) {
    int wert = map.get("Gold");
}
```

### ArrayList vs Array - Vergleich fuer den Schueler
```
Array:      String[] items = new String[5];   // Feste Groesse!
ArrayList:  ArrayList<String> items = new ArrayList<>();  // Wachst!

Array:      items[0] = "Schwert";
ArrayList:  items.add("Schwert");

Array:      items[0]
ArrayList:  items.get(0)

Array:      items.length
ArrayList:  items.size()
```

---

## WENN DER SCHUELER STECKENBLEIBT

### "Was ist der Unterschied zwischen ArrayList und Array?"
-> "Array hat feste Groesse (wie eine Truhe mit genau 27 Slots). ArrayList kann wachsen (wie ein magischer Rucksack der immer groesser wird)."

### "Wann benutze ich ArrayList, wann HashMap?"
-> "ArrayList wenn du eine REIHENFOLGE brauchst (Inventar-Slots). HashMap wenn du schnell nach einem NAMEN suchen willst (wie viel Gold habe ich?)."

### "Was bedeutet <String>?"
-> "Das sagt Java welcher TYP in der Liste steckt. ArrayList<String> = eine Liste die nur Text enthaelt. ArrayList<Integer> = eine Liste die nur Zahlen enthaelt."

### "Warum items.get(0) statt items[0]?"
-> "ArrayList ist kein normales Array. Es hat eigene Methoden. get(0) ist die ArrayList-Art, auf Element 0 zuzugreifen."

---

## ERFOLGS-SIGNALE (bereit fuer Phase 4)

- [ ] Kann ArrayList erstellen und mit add/get/remove arbeiten
- [ ] Versteht ArrayList vs Array Unterschied
- [ ] Kann for-each Schleife fuer ArrayList schreiben
- [ ] Kann ArrayList mit eigenen Objekten nutzen (z.B. ArrayList<Item>)
- [ ] Kann HashMap erstellen und mit put/get/containsKey arbeiten
- [ ] Kann HashMap mit keySet() durchlaufen
- [ ] Kann ArrayList und HashMap in einem Projekt kombinieren
- [ ] Hat das Abschlussprojekt erfolgreich abgeschlossen
