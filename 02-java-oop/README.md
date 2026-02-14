# 🎮 Phase 2: Objekt-Orientierte Programmierung (OOP)
## Der Schlüssel zu Minecraft-Mods

**Voraussetzung:** Phase 1 (Java Basics) abgeschlossen ✅

---

## 📊 Phase 2 - Was lernst du?

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | Klassen & Objekte | Blaupause für Objekte |
| 2 | Konstruktoren | Objekte erstellen |
| 3 | This & Getter/Setter | Zugriff auf Variablen |
| 4 | Vererbung | Klassen erweitern |
| 5 | Polymorphie | Mehrere Formen |
| 6 | Encapsulation | private/public |
| 7 | Minecraft-Klassen | Mob, Item, Block |
| 8 | Mini-Projekt | Dein erstes OOP-System |

---

## 🎯 Lernziele dieser Phase

Nach dieser Phase kannst du:
- ✅ Klassen definieren
- ✅ Objekte erstellen
- ✅ Vererbung verwenden
- ✅ Minecraft-Mods-relevanten Code verstehen
- ✅ Mit mehreren Klassen arbeiten

---

## 💡 Warum ist OOP wichtig?

**Ohne OOP:** 100 Variablen, 100 Funktionen, Chaos 😵
```java
int zombieHp = 20;
int creeperHp = 20;
int skelettHp = 20;
// ... immer wieder das gleiche!
```

**Mit OOP:** Klasse erstellen, Objekte davon machen, sauber! ✅
```java
class Mob {
    int hp;
    String name;
}

Mob zombie = new Mob("Zombie", 20);
Mob creeper = new Mob("Creeper", 20);
```

---

## 🚀 Start mit Phase 2

1. **Wenn du Phase 1 fertig hast:**
   - Öffne diesen Ordner: `02-java-oop`
   
2. **Öffne in VS Code:**
   - `File` → `Open Folder`
   - Wähle `java-lernen/02-java-oop`

3. **Starte mit der 1. Lektion (siehe oben)**

---

## 🎯 Abschlussprojekt

Nach den 8 Lektionen öffne **`ABSCHLUSSPROJEKT.md`** 🎮

Baue einen **Zombie Kampfsimulator** mit:
- Charakter & Zombie Klassen
- Vererbung
- Kampf-Logik
- Gewinner-Bestimmung

**Dein erstes großes OOP-Projekt!**

---

## 📚 Was ist eine Klasse?

**Analoge:** Eine Klasse ist wie ein Rezept
```java
public class Zombie {
    // Eigenschaften (Zutaten)
    String name;
    int hp;
    int schaden;
    
    // Methoden (Anweisungen)
    public void angreifen() {
        System.out.println(name + " greift an!");
    }
}
```

**Dann erstellst du Objekte davon (die fertigen Gerichte):**
```java
Zombie zombie1 = new Zombie();
Zombie zombie2 = new Zombie();
```

---

## ⏰ Zeitrahmen

- **Zeit pro Lektion:** 45-60 Minuten
- **Pro Woche:** 2-3 Lektionen gemütlich
- **Gesamt:** 4-6 Wochen

---

## ✅ Checkliste

Wenn du alle 8 Lektionen bestanden hast:
- [ ] Klassen definieren ✅
- [ ] Objekte erstellen ✅
- [ ] Vererbung verstehen ✅
- [ ] Minecraft-Code lesen ✅
- [ ] Encapsulation anwenden ✅

---

**Bereit? Dann auf zur 1. Lektion!** 🚀

(Die genauen Lektionen findest du in LERNPFAD.md)
