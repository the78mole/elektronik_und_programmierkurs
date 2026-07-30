# Modul 3: Programmieren mit Scratch

**Zielgruppe:** Ab 2. Klasse  
**Dauer:** 1,5 Stunden  
**Schwierigkeitsgrad:** ⭐⭐ Anfänger (keine Vorkenntnisse nötig)

## 🎯 Lernziele

- Scratch-Oberfläche kennenlernen
- Erste Programme mit Blöcken erstellen
- Figuren (Sprites) bewegen und steuern
- Einfache Animationen und Effekte programmieren
- Grundkonzepte: Sequenz, Wiederholung, Ereignisse

## 💻 Benötigte Materialien (pro Team/Kind)

- 1x Computer oder Tablet (idealerweise 2 Kinder pro Gerät)
- Installation: Scratch Desktop ODER Zugang zu https://scratch.mit.edu
- Maus (empfohlen für jüngere Kinder)
- Optional: Beamer für Demonstrationen
- Optional: Kopfhörer (falls Sound verwendet wird)

## 📖 Kursablauf

### 1. Einführung in Scratch (10 Min.)

**Was ist Scratch?**
- Eine Programmiersprache mit bunten Bausteinen
- Wie LEGO für den Computer
- Entwickelt vom MIT für Kinder

**Demo am Beamer:**
- Öffne Scratch und zeige die Oberfläche
- Bühne, Sprite, Blöcke
- "Wir bauen Programme wie LEGO-Türme!"

**Scratch-Oberfläche:**
- **Bühne:** Hier passiert alles (rechts)
- **Sprite:** Die Figur, die wir steuern (Katze)
- **Blöcke:** Die Befehle (links)
- **Skriptbereich:** Hier bauen wir unser Programm (Mitte)

### 2. Erstes Programm: Katze bewegen (15 Min.)

**Aufgabe:**
Lass die Katze "Hallo!" sagen und sich bewegen.

**Schritt-für-Schritt:**
1. Öffne Scratch (Desktop oder Online)
2. Finde die gelben Blöcke "Ereignisse"
3. Ziehe "Wenn Flagge angeklickt" in den Skriptbereich
4. Finde die lila Blöcke "Aussehen"
5. Ziehe "sage Hallo! für 2 Sekunden" dran
6. Klicke die grüne Flagge → Die Katze spricht!

**Erweitere das Programm:**
```
Wenn Flagge angeklickt
sage "Hallo!" für 2 Sekunden
gehe 10er Schritt
warte 1 Sekunden
sage "Tschüss!" für 2 Sekunden
```

### 3. Bewegung steuern (20 Min.)

**Aufgabe:**
Steuere die Katze mit Tasten!

**Neue Blöcke:**
- "Wenn Taste [Leertaste] gedrückt"
- "gehe 10er Schritt"
- "drehe dich um 15 Grad"

**Programm 1: Bewegung mit Pfeiltasten**
```
Wenn Taste [Pfeil nach oben] gedrückt
gehe 10er Schritt

Wenn Taste [Pfeil nach unten] gedrückt
gehe -10er Schritt

Wenn Taste [Pfeil nach links] gedrückt
drehe dich nach links um 15 Grad

Wenn Taste [Pfeil nach rechts] gedrückt
drehe dich nach rechts um 15 Grad
```

**Teste das Programm:**
- Drücke die Pfeiltasten
- Die Katze bewegt sich!

### 4. Wiederholungen und Schleifen (20 Min.)

**Aufgabe:**
Lass die Katze im Kreis laufen.

**Neuer Block:**
- "wiederhole 10 mal"

**Programm: Kreis laufen**
```
Wenn Flagge angeklickt
wiederhole 36 mal
    gehe 10er Schritt
    drehe dich nach rechts um 10 Grad
```

**Experiment:**
- Ändere die Zahlen!
- Was passiert bei 72 Wiederholungen?
- Was bei 5 Grad Drehung?

**Programm: Quadrat zeichnen**
```
Wenn Flagge angeklickt
wiederhole 4 mal
    gehe 100er Schritt
    drehe dich nach rechts um 90 Grad
```

### 5. Mini-Spiel: Fang die Maus (25 Min.)

**Aufgabe:**
Erstelle ein Spiel, bei dem die Katze eine Maus fangen muss.

**Vorbereitung:**
1. Füge ein neues Sprite hinzu (z.B. eine Maus)
2. Platziere es irgendwo auf der Bühne

**Programm für die Katze:**
```
Wenn Flagge angeklickt
wiederhole fortlaufend
    wenn Taste [Pfeil nach oben] gedrückt?
        ändere y um 10
    wenn Taste [Pfeil nach unten] gedrückt?
        ändere y um -10
    wenn Taste [Pfeil nach links] gedrückt?
        ändere x um -10
    wenn Taste [Pfeil nach rechts] gedrückt?
        ändere x um 10
    
    wenn wird Maus berührt?
        sage "Gefangen!" für 2 Sekunden
        stoppe alles
```

**Programm für die Maus:**
```
Wenn Flagge angeklickt
wiederhole fortlaufend
    gehe zu zufälliger Position
    warte 2 Sekunden
```

### 6. Präsentation (10 Min.)

**Zeigt eure Programme:**
- Welche Figuren habt ihr benutzt?
- Was macht euer Programm?
- Was war schwierig?

### 7. Freies Experimentieren (20 Min.)

**Ideen zum Weitermachen:**
- Füge Sound hinzu (Blöcke "Klang")
- Ändere Kostüme für Animationen
- Baue ein eigenes Spiel
- Male einen Hintergrund
- Füge mehr Sprites hinzu

## 💡 Tipps für Betreuer

### Vorbereitung
- Scratch vorher auf allen Geräten öffnen/installieren
- Eigenes Demo-Projekt vorbereiten
- Bei Online-Nutzung: WLAN-Stabilität prüfen

### Scratch-Installation
- **Online:** https://scratch.mit.edu (kein Account nötig)
- **Desktop:** Download von https://scratch.mit.edu/download
- **Tablets:** Scratch Jr. (vereinfacht, ab 5 Jahren)

### Häufige Probleme
- **Blöcke passen nicht zusammen:** Falsche Kategorie (Farbe beachten!)
- **Programm läuft nicht:** Grüne Flagge vergessen?
- **Sprite bewegt sich nicht:** Block richtig verbunden?
- **Kind verloren:** Zeige am eigenen Bildschirm

### Differenzierung
- **Schnelle Kinder:** Komplexere Spiele, mehrere Sprites, Variablen
- **Jüngere Kinder:** Einfachere Befehle, mehr visuelle Hilfe
- **Ältere Kinder:** Bedingungen (wenn-dann), eigene Blöcke erstellen

## 🎮 Block-Kategorien im Überblick

| Farbe | Kategorie | Beispiele |
|-------|-----------|-----------|
| 🟡 Gelb | Ereignisse | Wenn Flagge angeklickt, Wenn Taste gedrückt |
| 🔵 Blau | Bewegung | Gehe Schritt, Drehe dich, Gleite zu |
| 🟣 Lila | Aussehen | Sage, Zeige, Wechsle Kostüm |
| 🟠 Orange | Steuerung | Wiederhole, Wenn-dann, Warte |
| 🟢 Grün | Klang | Spiele Klang, Setze Lautstärke |
| 🔵 Hellblau | Fühlen | Wird berührt?, Taste gedrückt? |

## 🎓 Programmier-Konzepte

### Sequenz
Programme laufen von oben nach unten ab (wie ein Rezept).

### Ereignisse
Programme starten bei einem Ereignis (Flagge klicken, Taste drücken).

### Wiederholung (Schleifen)
Befehle mehrmals ausführen ohne sie neu zu schreiben.

### Bedingungen (optional)
"Wenn-dann": Nur bei bestimmten Bedingungen etwas tun.

## 📸 Dokumentation

- Screenshots der fertigen Programme
- Aufnahmen vom Bildschirm (Screen Recording)
- Scratch-Projekte speichern: "Datei" → "Auf Deinen Computer laden"

## 🏠 Hausaufgaben (optional)

1. **Für zu Hause:**
   - Scratch-Account erstellen (mit Eltern)
   - Eigenes Projekt weiterentwickeln
   - Andere Projekte auf Scratch ansehen und "remixen"

2. **Ideen für zu Hause:**
   - Animiere deine Familie als Sprites
   - Erstelle eine Geschichte
   - Baue ein Quiz-Spiel

## 📚 Weiterführende Ressourcen

- **Scratch-Website:** https://scratch.mit.edu
- **Tutorials:** https://scratch.mit.edu/ideas
- **Scratch Jr.:** Für jüngere Kinder (5-7 Jahre)
- **Code.org:** Weitere Programmier-Tutorials
- **YouTube:** "Scratch für Anfänger"

## 🎁 Projekt-Ideen für Fortgeschrittene

- Labyrinth-Spiel
- Pong (Ball-Spiel)
- Jump'n'Run
- Malprogram
- Musik-Instrument
- Quiz mit Punkten
- Interaktive Geschichte

---

**Vorheriges Modul:** [Modul 5: Bunte Lichter und Summer](../modul_05_lichter_summer/)  
**Nächstes Modul:** [Modul 7: Einführung in Mikrocontroller](../modul_07_mikrocontroller/)
