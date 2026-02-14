# 🎮 Phase 4: I/O & Exceptions
## Dateibearbeitung & Fehlerbehandlung

**Voraussetzung:** Phase 1, 2 & 3 abgeschlossen ✅

---

## 📊 Phase 4 - Was lernst du?

| Lektion | Thema | Konzept |
|---------|-------|---------|
| 1 | Textdateien lesen | FileReader/Scanner |
| 2 | Textdateien schreiben | FileWriter |
| 3 | Scanner Input | User-Eingaben |
| 4 | Try/Catch | Fehlerbehandlung |
| 5 | Verschiedene Exceptions | RuntimeException, IOException |
| 6 | Konfigurationsdateien | Config laden/speichern |
| 7 | JSON/Properties | Strukturierte Daten |
| 8 | Mini-Projekt | Minecraft Launcher Config |

---

## 🎯 Warum I/O & Exceptions?

**Szenario:** Dein Programm brauchte eine Konfigurationsdatei, aber sie existiert nicht!
```java
File file = new File("config.txt");  // Fehler!
```

**Lösung - Mit Exception Handling:**
```java
try {
    File file = new File("config.txt");
    if (!file.exists()) {
        System.out.println("Datei nicht gefunden!");
    }
} catch (Exception e) {
    System.out.println("Fehler: " + e.getMessage());
}
```

---

## 📚 Wichtige Klassen

### Scanner - Eingabe lesen
```java
Scanner scanner = new Scanner(System.in);
System.out.print("Dein Name: ");
String name = scanner.nextLine();
```

### FileWriter - Datei schreiben
```java
FileWriter fw = new FileWriter("datei.txt");
fw.write("Hallo Welt!");
fw.close();
```

### FileReader - Datei lesen
```java
FileReader fr = new FileReader("datei.txt");
Scanner scanner = new Scanner(fr);
while (scanner.hasNextLine()) {
    System.out.println(scanner.nextLine());
}
```

---

## 🚀 Start mit Phase 4

1. Diese Phase öffnen:
   `java-lernen/04-java-io`

2. README.md lesen

3. Mit Lektion 1 starten

---

## ⏰ Zeitrahmen

- **Zeit pro Lektion:** 30-40 Minuten
- **Pro Woche:** 2-3 Lektionen
- **Gesamt:** 1-2 Wochen

---

## ✅ Checkliste am Ende

- [ ] Dateien lesen ✅
- [ ] Dateien schreiben ✅
- [ ] User-Eingaben verarbeiten ✅
- [ ] Fehler abfangen (Try/Catch) ✅
- [ ] Mini-Projekt erstellen ✅

---

## 🎯 Abschlussprojekt

Nach den 8 Lektionen öffne **`ABSCHLUSSPROJEKT.md`** 🎮

Baue ein **Spieler-Verwaltungssystem** mit:
- Spieler speichern & laden (File I/O)
- Exception-Handling
- CSV/TXT Format
- Interaktives Menü

**Dein erstes vollständiges Datenspeichersystem!**

---

**Nach Phase 4 kannst du mit Dateien & Fehlern arbeiten!** 🚀
