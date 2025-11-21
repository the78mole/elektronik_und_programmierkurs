# Modul 5: Sensoren erkunden

**Zielgruppe:** Ab 4. Klasse (nach Modul 4)  
**Dauer:** 1,5 Stunden  
**Schwierigkeitsgrad:** ⭐⭐⭐ Fortgeschritten

## 🎯 Lernziele

- Verschiedene Sensoren kennenlernen
- Sensor-Werte auslesen und verstehen
- Auf Umgebung reagieren
- Serial Monitor für Debugging nutzen
- Einfache Regelung programmieren

## 💻 Benötigte Materialien (pro Team)

- 1x Arduino Uno oder Calliope
- 1x USB-Kabel
- 1x Lichtsensor (LDR - Light Dependent Resistor)
- 1x Temperatursensor (TMP36 oder DHT11)
- 1x Potentiometer (10kΩ)
- 2x LEDs
- 2x Widerstände 220Ω
- 1x Widerstand 10kΩ (für LDR)
- 1x Breadboard
- 10x Jumper-Kabel

## 📖 Kursablauf

### 1. Einführung: Was sind Sensoren? (10 Min.)

**Was ist ein Sensor?**
- Ein Bauteil, das die Umwelt misst
- Wandelt physikalische Größen in elektrische Signale um
- Beispiele: Temperatur, Licht, Abstand, Bewegung

**Sensoren in unserem Alltag:**
- Smartphone: Helligkeitssensor, Beschleunigungssensor
- Auto: Regensensor, Abstandssensor
- Haus: Rauchmelder, Thermostat

**Demo:**
- Zeige verschiedene Sensoren
- Erkläre, was sie messen

### 2. Projekt 1: Potentiometer (Drehregler) (15 Min.)

**Was ist ein Potentiometer?**
- Ein variabler Widerstand
- Kann von 0 bis maximalen Wert gedreht werden
- Gibt einen Wert zwischen 0 und 1023 zurück (10-Bit ADC)

**Aufbau:**
```
Potentiometer:
- Pin 1 (links) → Arduino 5V
- Pin 2 (mitte) → Arduino A0
- Pin 3 (rechts) → Arduino GND
```

**Code:**

```cpp
int sensorPin = A0;
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600); // Starte serielle Kommunikation
}

void loop() {
  int sensorValue = analogRead(sensorPin); // Lese Wert (0-1023)
  
  Serial.print("Potentiometer: ");
  Serial.println(sensorValue); // Zeige im Serial Monitor
  
  // Steuere LED-Helligkeit (PWM)
  int brightness = sensorValue / 4; // 0-1023 → 0-255
  analogWrite(ledPin, brightness);
  
  delay(100);
}
```

**Teste:**
1. Upload Code
2. Öffne Serial Monitor (Lupe-Symbol oben rechts)
3. Drehe am Potentiometer
4. Beobachte Werte und LED-Helligkeit!

### 3. Projekt 2: Lichtsensor (LDR) (25 Min.)

**Was ist ein LDR?**
- Light Dependent Resistor
- Widerstand ändert sich mit Lichtmenge
- Hell → Niedriger Widerstand
- Dunkel → Hoher Widerstand

**Aufbau (Spannungsteiler):**
```
Arduino 5V → LDR → Arduino A0
                   ↓
Arduino A0 → 10kΩ Widerstand → Arduino GND
```

**Code:**

```cpp
int ldrPin = A0;
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int lightValue = analogRead(ldrPin);
  
  Serial.print("Licht: ");
  Serial.println(lightValue);
  
  // Wenn dunkel (Wert < 500), schalte LED an
  if(lightValue < 500) {
    digitalWrite(ledPin, HIGH);
    Serial.println("→ LED AN (dunkel)");
  } else {
    digitalWrite(ledPin, LOW);
    Serial.println("→ LED AUS (hell)");
  }
  
  delay(200);
}
```

**Experimente:**
- Halte Hand über Sensor → LED geht an
- Taschenlampe darauf → LED geht aus
- Finde den richtigen Schwellwert für deinen Raum

**Projekt: Automatisches Nachtlicht**
- LED geht bei Dunkelheit an
- Praktisch für Flur oder Kinderzimmer!

### 4. Projekt 3: Temperatursensor (25 Min.)

**Was ist ein TMP36?**
- Analoger Temperatursensor
- Misst von -40°C bis +125°C
- Gibt Spannung proportional zur Temperatur aus

**Aufbau:**
```
TMP36 (von links nach rechts):
- Pin 1 → Arduino 5V
- Pin 2 → Arduino A0
- Pin 3 → Arduino GND
```

**Code:**

```cpp
int tempPin = A0;
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(tempPin);
  
  // Umrechnung in Spannung (0-1023 → 0-5V)
  float voltage = sensorValue * (5.0 / 1023.0);
  
  // Umrechnung in Temperatur (TMP36: 10mV/°C, 500mV bei 0°C)
  float temperature = (voltage - 0.5) * 100.0;
  
  Serial.print("Temperatur: ");
  Serial.print(temperature);
  Serial.println(" °C");
  
  // Wenn zu warm (> 25°C), schalte LED an
  if(temperature > 25.0) {
    digitalWrite(ledPin, HIGH);
    Serial.println("→ Zu warm! LED AN");
  } else {
    digitalWrite(ledPin, LOW);
    Serial.println("→ OK. LED AUS");
  }
  
  delay(1000);
}
```

**Experimente:**
- Halte Finger auf Sensor → Temperatur steigt
- Puste darauf → Temperatur sinkt
- Miss Raumtemperatur

**Projekt: Temperatur-Alarm**
- Bei zu hoher Temperatur blinkt LED
- Füge Summer hinzu für akustischen Alarm

### 5. Kombinations-Projekt (20 Min.)

**Aufgabe:**
Kombiniere mehrere Sensoren!

**Idee: Klima-Station**
```cpp
int ldrPin = A0;
int tempPin = A1;
int redLED = 9;
int greenLED = 10;

void setup() {
  pinMode(redLED, OUTPUT);
  pinMode(greenLED, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // Lese Sensoren
  int light = analogRead(ldrPin);
  int tempRaw = analogRead(tempPin);
  float temp = (tempRaw * (5.0/1023.0) - 0.5) * 100.0;
  
  // Zeige Werte
  Serial.print("Licht: ");
  Serial.print(light);
  Serial.print(" | Temp: ");
  Serial.print(temp);
  Serial.println(" °C");
  
  // LED-Anzeige
  if(light > 500 && temp > 20 && temp < 26) {
    digitalWrite(greenLED, HIGH); // Alles OK
    digitalWrite(redLED, LOW);
    Serial.println("→ Perfekte Bedingungen!");
  } else {
    digitalWrite(greenLED, LOW);
    digitalWrite(redLED, HIGH); // Warnung
    Serial.println("→ Achtung: Bedingungen nicht optimal");
  }
  
  delay(1000);
}
```

### 6. Präsentation (10 Min.)

**Zeigt eure Projekte:**
- Welche Sensoren habt ihr verwendet?
- Was misst euer Projekt?
- Wofür könnte man es verwenden?

### 7. Freies Experimentieren (15 Min.)

**Weitere Ideen:**
- Pflanzen-Monitor (zu trocken → LED)
- Helligkeitsregler (Poti steuert LED)
- Temperatur-Farbanzeige (kalt=blau, warm=rot)
- Lichtorgel (Sound-Sensor + LEDs)

## 💡 Tipps für Betreuer

### Vorbereitung
- Alle Sensoren vorher testen
- Spannungsteiler-Aufbau üben (für LDR)
- Serial Monitor erklären (wichtig für Debugging!)

### Serial Monitor
- "Werkzeuge" → "Serieller Monitor" oder Strg+Shift+M
- Baud-Rate: 9600 (muss mit Code übereinstimmen)
- Hilfreich zum Debuggen und Werte anzeigen

### Häufige Probleme

**"Sensor gibt komische Werte"**
- Kabel richtig angeschlossen? (5V, GND, Signal)
- Bei LDR: Spannungsteiler mit 10kΩ?
- Serial Monitor zur Diagnose nutzen

**"Temperatur stimmt nicht"**
- Umrechnung korrekt? (TMP36-Formel)
- Sensor richtig herum? (Pin-Belegung prüfen)
- Erst stabilisieren lassen (einige Sekunden)

**"LED reagiert nicht auf Sensor"**
- Schwellwert anpassen (im Serial Monitor prüfen)
- if-Bedingung logisch richtig?

### Differenzierung
- **Schnelle Kinder:** Mehrere Sensoren kombinieren, Durchschnittswerte
- **Jüngere Kinder:** Einfache Schwellwert-Prüfung, viel Serial-Output
- **Ältere Kinder:** Kalibrierung, Mittelwerte, Hysterese

## 🎓 Wichtige Konzepte

### Analoger Input
- `analogRead(pin)`: Liest Wert 0-1023 (10 Bit)
- Pins A0-A5 auf Arduino Uno

### PWM-Output
- `analogWrite(pin, value)`: Schreibt Wert 0-255
- Simuliert analoge Spannung
- Nur auf PWM-Pins (~3, ~5, ~6, ~9, ~10, ~11)

### Serial Monitor
- Kommunikation zwischen Arduino und Computer
- `Serial.begin(9600)`: Starte Kommunikation
- `Serial.println(wert)`: Sende Wert zum Computer
- Wichtig für Debugging!

### Spannungsteiler
```
         5V
          |
        [R1] (z.B. LDR)
          |
          +--- A0
          |
        [R2] (z.B. 10kΩ)
          |
         GND
```

## 🔒 Sicherheitshinweise

- ✅ Sensoren sind generell sicher (5V)
- ⚠️ Temperatursensor kann warm werden (normal)
- ⚠️ Polarität beachten (bei TMP36)
- ❌ Keine Sensoren direkt zwischen 5V und GND (Kurzschluss!)

## 📸 Dokumentation

- Fotos vom Breadboard-Aufbau
- Screenshots vom Serial Monitor
- Diagramme der Sensor-Werte
- Video der reagierenden LEDs

## 🏠 Hausaufgaben (optional)

1. **Beobachtung:**
   - Miss Temperatur zu verschiedenen Tageszeiten
   - Erstelle ein Diagramm

2. **Experiment:**
   - Wo ist es am hellsten/dunkelsten zu Hause?
   - Miss mit dem LDR

3. **Idee entwickeln:**
   - Welchen Sensor würdest du gerne ausprobieren?
   - Ultraschall? Feuchtigkeit? Bewegung?

## 📚 Weiterführende Ressourcen

- **Sensor-Kit:** Arduino Starter Kits mit 20+ Sensoren
- **Tutorials:** Adafruit, SparkFun Sensor-Guides
- **Weitere Sensoren:** Ultraschall (HC-SR04), Bewegung (PIR), Feuchtigkeit

## 🎁 Projekt-Ideen für Fortgeschrittene

- Wetterstation mit Display
- Pflanzen-Monitor mit Feuchtigkeitssensor
- Entfernungsmesser mit Ultraschall
- Bewegungsmelder mit PIR
- Datenlogger (Werte auf SD-Karte speichern)
- Grafische Anzeige im Processing

---

**Vorheriges Modul:** [Modul 4: Einführung in Mikrocontroller](../modul_04_mikrocontroller/)  
**Nächstes Modul:** [Modul 6: Motoren und Bewegung](../modul_06_motoren/)
