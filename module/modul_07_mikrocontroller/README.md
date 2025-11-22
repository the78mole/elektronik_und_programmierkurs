# Modul 4: Einführung in Mikrocontroller

**Zielgruppe:** Ab 4. Klasse  
**Dauer:** 1,5 Stunden  
**Schwierigkeitsgrad:** ⭐⭐⭐ Fortgeschritten

## 🎯 Lernziele

- Verstehen, was ein Mikrocontroller ist
- Arduino oder Calliope kennenlernen
- Erste LED mit Code zum Blinken bringen
- Programme hochladen und testen
- Grundlagen der Programmierung mit Arduino IDE

## 💻 Benötigte Materialien (pro Team)

- 1x Arduino Uno ODER Calliope mini
- 1x USB-Kabel (Typ A zu Typ B für Arduino)
- 1x Computer mit Arduino IDE oder MakeCode
- 1x LED (extern)
- 1x Widerstand 220Ω
- 1x Breadboard
- 3x Jumper-Kabel
- Optional: Mehrere LEDs für Experimente

## 📖 Kursablauf

### 1. Einführung: Was ist ein Mikrocontroller? (10 Min.)

**Was ist ein Mikrocontroller?**
- Ein kleiner Computer auf einem Chip
- Kann Sensoren auslesen und Aktoren steuern
- Überall: Waschmaschine, Auto, Roboter, Spielzeug

**Vergleich:**
- Computer: Flexibel, viele Programme
- Mikrocontroller: Macht eine Sache sehr gut

**Demo:**
- Zeige Arduino oder Calliope
- Erkläre: Pins, USB-Anschluss, Power

### 2. Setup und Installation (15 Min.)

#### Für Arduino:

**Arduino IDE installieren:**
1. Download von https://www.arduino.cc/en/software
2. Arduino per USB verbinden
3. IDE öffnen
4. Board auswählen: "Tools" → "Board" → "Arduino Uno"
5. Port auswählen: "Tools" → "Port" → COM3 (oder ähnlich)

**Teste die Verbindung:**
- Beispiel öffnen: "Datei" → "Beispiele" → "01.Basics" → "Blink"
- Upload-Button klicken (→)
- LED auf dem Board sollte blinken!

#### Für Calliope:

**MakeCode Editor:**
1. Öffne https://makecode.calliope.cc/
2. Calliope per USB verbinden
3. Erstelle ein neues Projekt

### 3. Projekt 1: LED blinken lassen (20 Min.)

#### Arduino-Code:

```cpp
// LED Blink Programm
int ledPin = 13; // Pin 13 (eingebaute LED)

void setup() {
  pinMode(ledPin, OUTPUT); // Pin als Ausgang
}

void loop() {
  digitalWrite(ledPin, HIGH); // LED an
  delay(1000);                // Warte 1 Sekunde
  digitalWrite(ledPin, LOW);  // LED aus
  delay(1000);                // Warte 1 Sekunde
}
```

**Code-Erklärung:**
- `setup()`: Wird einmal beim Start ausgeführt
- `loop()`: Wird immer wieder wiederholt
- `digitalWrite()`: Schaltet einen Pin an oder aus
- `delay()`: Wartet (in Millisekunden)

**Aufgabe:**
1. Tippe den Code ab (oder kopiere das Beispiel)
2. Klicke auf Upload (→)
3. Die LED auf dem Arduino blinkt!

**Experimente:**
- Ändere die Zahlen bei `delay()`
- Was passiert bei `delay(100)`?
- Was bei `delay(2000)`?

#### Calliope-Programm:

**Blöcke in MakeCode:**
```
Dauerhaft:
    zeige LED (alle an)
    pausiere 1000 ms
    zeige LED (alle aus)
    pausiere 1000 ms
```

### 4. Projekt 2: Externe LED steuern (25 Min.)

**Aufgabe:**
Schließe eine eigene LED an und steuere sie.

#### Aufbau (Arduino):

**Schaltplan:**
```
Arduino Pin 9 → Widerstand 220Ω → LED (langes Bein)
LED (kurzes Bein) → Arduino GND
```

**Schritt-für-Schritt:**
1. Stecke Breadboard auf
2. LED ins Breadboard (Beine in verschiedene Reihen)
3. Widerstand von langem LED-Bein zu einer Reihe
4. Jumper-Kabel von Arduino Pin 9 zum Widerstand
5. Jumper-Kabel von kurzem LED-Bein zu Arduino GND

#### Code anpassen:

```cpp
int ledPin = 9; // Geändert auf Pin 9!

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH);
  delay(500);
  digitalWrite(ledPin, LOW);
  delay(500);
}
```

**Teste:**
- Upload → Externe LED blinkt!

### 5. Projekt 3: SOS-Signal (20 Min.)

**Aufgabe:**
Programmiere ein SOS-Signal in Morse-Code!

**Morse-Code:**
- S = • • • (3x kurz)
- O = — — — (3x lang)
- S = • • • (3x kurz)

**Code:**

```cpp
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // S: 3x kurz
  for(int i=0; i<3; i++) {
    digitalWrite(ledPin, HIGH);
    delay(200);
    digitalWrite(ledPin, LOW);
    delay(200);
  }
  
  delay(400); // Pause zwischen Buchstaben
  
  // O: 3x lang
  for(int i=0; i<3; i++) {
    digitalWrite(ledPin, HIGH);
    delay(600);
    digitalWrite(ledPin, LOW);
    delay(200);
  }
  
  delay(400);
  
  // S: 3x kurz
  for(int i=0; i<3; i++) {
    digitalWrite(ledPin, HIGH);
    delay(200);
    digitalWrite(ledPin, LOW);
    delay(200);
  }
  
  delay(2000); // Lange Pause vor Wiederholung
}
```

### 6. Präsentation (10 Min.)

**Zeigt eure Projekte:**
- Wie schnell blinkt eure LED?
- Habt ihr andere Muster programmiert?
- Was war die größte Herausforderung?

### 7. Freies Experimentieren (20 Min.)

**Weitere Ideen:**
- Mehrere LEDs gleichzeitig steuern
- Lauflicht mit 3 LEDs
- Verschiedene Blinkmuster
- Ampelsteuerung mit Code

## 💡 Tipps für Betreuer

### Vorbereitung
- Alle Arduino-Boards vorher testen
- Arduino IDE auf allen Computern installieren
- Treiber evtl. vorab installieren (je nach OS)
- Ersatz-USB-Kabel bereithalten

### Häufige Probleme

**"Port nicht gefunden"**
- Richtigen Port auswählen (Tools → Port)
- USB-Kabel wechseln (manche sind nur zum Laden)
- Treiber installieren (bei älteren Boards)

**"Upload fehlgeschlagen"**
- Richtiges Board ausgewählt?
- USB-Kabel richtig angeschlossen?
- Arduino-Reset-Button drücken und nochmal versuchen

**"LED blinkt nicht"**
- Code kompiliert ohne Fehler?
- Richtige Pin-Nummer?
- LED richtig herum? (Polarität!)
- Widerstand verbaut?

### Differenzierung
- **Schnelle Kinder:** Mehrere LEDs, for-Schleifen, eigene Funktionen
- **Jüngere Kinder:** Calliope mit MakeCode (visueller)
- **Ältere Kinder:** C++-Syntax erklären, Schleifen, Funktionen

## 🎓 Programmier-Konzepte

### Arduino-Programm-Struktur
```cpp
// Variablen und Konstanten

void setup() {
  // Einmalige Initialisierung
}

void loop() {
  // Wird wiederholt ausgeführt
}
```

### Wichtige Befehle
- `pinMode(pin, OUTPUT)`: Pin als Ausgang
- `digitalWrite(pin, HIGH/LOW)`: Pin an/aus
- `delay(ms)`: Warten in Millisekunden

### Pin-Typen
- **Digital:** An/Aus (HIGH/LOW)
- **Analog:** Später mit PWM für Helligkeit

## 🔒 Sicherheitshinweise

- ✅ Arduino-USB ist sicher (5V)
- ✅ LEDs mit Widerstand schützen
- ⚠️ Maximal 40mA pro Pin
- ❌ Nie 5V direkt mit GND verbinden (Kurzschluss!)

## 📸 Dokumentation

- Fotos vom Breadboard-Aufbau
- Screenshots vom Code
- Video der blinkenden LED
- Schaltplan skizzieren

## 🏠 Hausaufgaben (optional)

1. **Recherche:**
   - Wo werden Mikrocontroller verwendet?
   - Finde 5 Geräte zu Hause mit Mikrocontroller

2. **Programmieren:**
   - Verändere das Blinkmuster
   - Erstelle dein eigenes Morse-Signal (deinen Namen?)

3. **Ideen sammeln:**
   - Was möchtest du mit Arduino bauen?

## 📚 Weiterführende Ressourcen

- **Arduino-Website:** https://www.arduino.cc/
- **Tutorials:** https://www.arduino.cc/en/Tutorial/HomePage
- **Calliope:** https://calliope.cc/
- **YouTube:** "Arduino für Anfänger"
- **Projekte:** Instructables, Hackster.io

## 🎁 Projekt-Ideen für Fortgeschrittene

- Ampelsteuerung mit LEDs
- Lauflicht (Knight Rider)
- LED-Würfel (zufällige Zahlen)
- Reaktionsspiel mit Taste
- Helligkeitssteuerung mit PWM

---

**Vorheriges Modul:** [Modul 6: Programmieren mit Scratch](../modul_06_scratch/)  
**Nächstes Modul:** [Modul 8: Sensoren erkunden](../modul_08_sensoren/)
