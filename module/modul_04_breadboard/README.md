# Modul 4: Einführung ins Breadboard

**Zielgruppe:** Ab 2. Klasse (nach Modul 1-3)  
**Dauer:** 1,5 Stunden  
**Schwierigkeitsgrad:** ⭐⭐ Anfänger mit Vorkenntnissen

## 🎯 Lernziele

- Verstehen, wie ein Breadboard funktioniert
- Leitende Verbindungen im Breadboard erkennen
- Erste Schaltungen ohne Löten aufbauen
- Von Krokodilklemmen zu professionellen Steckverbindungen wechseln
- Saubere und übersichtliche Schaltungen erstellen

## 📦 Benötigte Materialien (pro Team)

- 1x Breadboard (830 Löcher, Standard)
- 1x Breadboard-Erklärungsfolie/Poster (selbst erstellt)
- 10x LEDs (verschiedene Farben)
- 10x Widerstände 220Ω
- 20x Jumper-Kabel (verschiedene Längen)
- 1x Batteriehalter mit Kabel (4xAA = 6V)
- 4x AA-Batterien
- Optional: Multimeter zum Durchgangsprüfen

## 📖 Kursablauf

### 1. Einführung: Was ist ein Breadboard? (15 Min.)

**Problem ohne Breadboard:**
- Krokodilklemmen: Unübersichtlich, fällt leicht auseinander
- Löten: Dauerhaft, für Kinder schwierig
- Lösung: **Breadboard** - schnell, einfach, wiederverwendbar!

**Zeige ein Breadboard:**
- Wie sieht es aus?
- Viele Löcher in Reihen
- Wozu sind die Löcher da?

**Das Geheimnis des Breadboards:**
"Die Löcher sind nicht alle getrennt - einige sind unter der Oberfläche verbunden!"

### 2. Breadboard-Anatomie: Wie ist es verbunden? (20 Min.)

**Zeige die Erklärungsfolie/Poster:**

```
Breadboard-Layout:

   + Stromschiene (rot)     [===================]
   - Stromschiene (blau)    [===================]
   
   ┌─────────────────────────────────────┐
   │  a  b  c  d  e     f  g  h  i  j   │
   ├─────────────────────────────────────┤
 1 │  ●  ●  ●  ●  ●  │  ●  ●  ●  ●  ●   │
 2 │  ●  ●  ●  ●  ●  │  ●  ●  ●  ●  ●   │
 3 │  ●  ●  ●  ●  ●  │  ●  ●  ●  ●  ●   │
   └─────────────────────────────────────┘

   - Stromschiene (blau)    [===================]
   + Stromschiene (rot)     [===================]
```

**Verbindungen erklären:**

1. **Stromschienen (oben und unten):**
   - Rote Linie = + (Plus)
   - Blaue Linie = - (Minus/GND)
   - **Alle Löcher einer Schiene sind horizontal verbunden**
   - Perfekt für Stromversorgung!

2. **Mittlerer Bereich (Arbeitsbereich):**
   - **Vertikal in 5er-Gruppen verbunden** (a-b-c-d-e)
   - **Vertikal in 5er-Gruppen verbunden** (f-g-h-i-j)
   - **Mittlere Spalte trennt links und rechts**
   - Perfekt für Bauteile (IC, LED, Widerstände)!

**Wichtig:**
- Reihen (1, 2, 3...) sind NICHT verbunden
- Spalten (a, b, c...) sind in 5er-Gruppen verbunden
- Mittlere Spalte trennt!

**Experiment: Durchgangstest**
Mit Multimeter oder LED+Batterie testen:
- Sind a1 und b1 verbunden? → JA!
- Sind a1 und a2 verbunden? → NEIN!
- Sind a1 und f1 verbunden? → NEIN! (Mittelspalte trennt)

### 3. Hands-On: Breadboard erkunden (15 Min.)

**Aufgabe 1: LED-Test**
Baue die einfachste Schaltung:

1. Stecke rotes Kabel von Batterie+ in rote Stromschiene
2. Stecke schwarzes Kabel von Batterie- in blaue Stromschiene
3. Nimm LED: Langes Bein in eine Lochreihe (z.B. a5)
4. Stecke Widerstand: Ein Ende in gleiche 5er-Gruppe wie LED-Lang (z.B. b5)
5. Widerstand anderes Ende: In Reihe mit Verbindung zu roter Stromschiene
6. LED kurzes Bein: Verbinde mit blauer Stromschiene
7. LED leuchtet! ✨

**Aufgabe 2: Verbindungen testen**
Mit einem Jumper-Kabel und LED:
- Finde heraus, welche Löcher verbunden sind
- Zeichne deine Erkenntnisse auf

**Tipp:** Macht Notizen auf der Breadboard-Skizze!

### 4. Projekt 1: Drei LEDs parallel (20 Min.)

**Aufgabe:**
Baue eine Schaltung mit 3 LEDs, alle leuchten gleichzeitig.

**Schaltplan:**
```
Batterie+ → Stromschiene+ → LED1+Widerstand → Stromschiene-
                          → LED2+Widerstand → Stromschiene-
                          → LED3+Widerstand → Stromschiene-
```

**Schritt-für-Schritt:**
1. Verbinde Batterie mit Stromschienen (+ und -)
2. Für jede LED:
   - Langes Bein in Arbeitsbereich (eigene Reihe)
   - Widerstand in gleiche 5er-Gruppe
   - Widerstand-Ende zu Stromschiene+
   - Kurzes LED-Bein zu Stromschiene-
3. Alle drei LEDs leuchten!

**Beobachtung:**
- Alle LEDs gleich hell?
- Ziehe eine LED raus - leuchten die anderen weiter? (Ja!)
- Das ist Parallelschaltung!

### 5. Projekt 2: Ampel mit Tastern (30 Min.)

**Aufgabe:**
Baue eine Ampel mit Tastern zum Schalten.

**Material zusätzlich:**
- 3 Taster
- 3 LEDs (rot, gelb, grün)

**Aufbau:**
1. Drei LEDs mit Widerständen aufbauen (wie Projekt 1)
2. Aber: Plus nicht direkt an Stromschiene
3. Sondern: Über Taster
4. Taster hat 4 Beine:
   - Zwei Seiten sind verbunden
   - Drücken verbindet beide Seiten
5. Eine Seite Taster an Stromschiene+
6. Andere Seite zu LED-Widerstand

**Test:**
- Taster 1 drücken → Rote LED an
- Taster 2 drücken → Gelbe LED an
- Taster 3 drücken → Grüne LED an

**Challenge:**
Kannst du zwei LEDs gleichzeitig mit einem Taster schalten?

### 6. Best Practices: Saubere Schaltungen (10 Min.)

**Tipps für übersichtliche Breadboard-Schaltungen:**

1. **Farb-System:**
   - Rot = Plus/Positive Verbindungen
   - Schwarz/Blau = Minus/GND
   - Andere Farben = Signale

2. **Kabel-Längen:**
   - Verwende passende Längen
   - Nicht zu lang (unübersichtlich)
   - Nicht zu kurz (zieht Bauteile raus)

3. **Anordnung:**
   - Bauteile ordentlich in Reihen
   - Stromversorgung immer über Schienen
   - Ähnliche Bauteile gruppieren

4. **Dokumentation:**
   - Zeichne einen Schaltplan
   - Fotografiere fertige Schaltung
   - Notiere Pin-Nummern

**Zeige gute vs. schlechte Beispiele!**

### 7. Präsentation und Reflexion (10 Min.)

**Zeigt eure Schaltungen:**
- Wie habt ihr das Breadboard verwendet?
- Was war anfangs verwirrend?
- Was ist jetzt klar?

**Diskussion:**
- Warum ist Breadboard besser als Krokodilklemmen?
- Wo sind die Vorteile?
- Wo muss man aufpassen?

## 💡 Tipps für Betreuer

### Vorbereitung
- **Wichtig:** Erstelle große Breadboard-Erklärungsfolie!
- Zeige Breadboard von unten (Metallstreifen sichtbar)
- Bereite Beispiel-Schaltungen vor
- Teste alle Breadboards vorher (manchmal sind Kontakte schlecht)

### Breadboard-Erklärungsfolie erstellen

Drucke/Male eine große Version:
```
┌────────────────────────────────────────┐
│ STROMSCHIENE + (rot)  [============]   │
│ STROMSCHIENE - (blau) [============]   │
│                                        │
│ ARBEITSBEREICH:                        │
│  Spalten a-e verbunden (vertikal)     │
│  Spalten f-j verbunden (vertikal)     │
│  Mittlere Spalte TRENNT!              │
│                                        │
│  Reihen sind NICHT verbunden!         │
│                                        │
│ [Zeichne die Verbindungslinien ein]   │
└────────────────────────────────────────┘
```

### Häufige Probleme

**"LED leuchtet nicht"**
- Beine in falscher 5er-Gruppe?
- Kabel in gleicher Reihe wie LED-Bein?
- Stromschienen richtig angeschlossen?

**"Kurzschluss"**
- Plus und Minus direkt verbunden?
- LED ohne Widerstand?
- Bauteile berühren sich?

**"Breadboard funktioniert nicht"**
- Kontakte verschmutzt? (Mit Druckluft reinigen)
- Beine zu dick/zu dünn?
- Kaputte Kontakte? (Anderes Breadboard probieren)

### Differenzierung
- **Schnelle Kinder:** Komplexere Schaltungen, mehr LEDs, Taster-Kombinationen
- **Jüngere Kinder:** Erst mit wenigen Bauteilen, viel Anleitung
- **Ältere Kinder:** Reihenschaltung vs. Parallelschaltung vertiefen

## 🎓 Was haben wir gelernt?

### Breadboard-Wissen
- Breadboard = Steckbrett ohne Löten
- Löcher sind in Gruppen verbunden
- Stromschienen horizontal verbunden
- Arbeitsbereich vertikal in 5er-Gruppen
- Mittlere Spalte trennt links/rechts

### Vorteile Breadboard
- ✅ Schnell und einfach
- ✅ Wiederverwendbar
- ✅ Keine permanenten Verbindungen
- ✅ Professioneller als Krokodilklemmen
- ✅ Standard in Elektronik

### Workflow
1. Schaltplan zeichnen
2. Stromversorgung aufbauen (Schienen)
3. Bauteile einstecken
4. Verbindungen mit Jumpern
5. Testen!

## 📸 Dokumentation

- Foto der Erklärungsfolie
- Fotos von Schaltungen (von oben)
- Markiere Verbindungen auf Fotos
- Schaltpläne der Projekte

## 🏠 Für zu Hause

**Übungen:**
- Zeichne dein eigenes Breadboard-Diagramm
- Erkläre jemandem zu Hause, wie es funktioniert
- Baue eine Schaltung aus Modul 3 nach (aber mit Breadboard!)

**Eltern-Info:**
- Breadboards sind wiederverwendbar
- Kein Löten = kinderfreundlich
- Perfekt zum Experimentieren
- Günstig zu kaufen (ca. 3-5€)

## 📚 Weiterführende Ressourcen

- "How to use a Breadboard" (YouTube - viele gute Videos)
- Arduino-Tutorials verwenden alle Breadboards
- Fritzing: Software zum Zeichnen von Breadboard-Schaltungen

## 🎯 Nächste Schritte

Ab jetzt verwenden wir **immer Breadboards**!

In den folgenden Modulen werdet ihr:
- Komplexere Schaltungen bauen
- Mikrocontroller verwenden
- Sensoren und Motoren integrieren
- Alles auf dem Breadboard!

**Das Breadboard ist euer bester Freund beim Experimentieren!** 🔌

---

**Vorheriges Modul:** [Modul 3: Erste Schritte mit Strom](../modul_03_stromkreise/)  
**Nächstes Modul:** [Modul 5: Bunte Lichter und Summer](../modul_05_lichter_summer/)
