# Modul 6: Motoren und Bewegung

**Zielgruppe:** Ab 4. Klasse (nach Modul 4 & 5)  
**Dauer:** 1,5 Stunden  
**Schwierigkeitsgrad:** ⭐⭐⭐⭐ Fortgeschritten

## 🎯 Lernziele

- Unterschied zwischen Servo- und DC-Motoren verstehen
- Servo-Motor präzise steuern
- DC-Motor mit Transistor schalten
- Einfachen Roboter oder bewegliche Konstruktion bauen
- Motoren mit Sensoren kombinieren

## 💻 Benötigte Materialien (pro Team)

- 1x Arduino Uno
- 1x USB-Kabel
- 1x Servo-Motor (SG90 oder ähnlich)
- 1x DC-Motor (klein, 3-6V)
- 1x Transistor (BC547 oder 2N2222)
- 1x Diode 1N4007 (Freilaufdiode)
- 1x Widerstand 1kΩ (für Transistor-Basis)
- 1x Batteriehalter (AA) mit Batterien
- 1x Breadboard
- 10x Jumper-Kabel
- Optional: Propeller, Räder, Bastelmaterial

## 📖 Kursablauf

### 1. Einführung: Motoren-Arten (10 Min.)

**Was ist ein Motor?**
- Wandelt elektrische Energie in Bewegung um
- Viele verschiedene Typen für unterschiedliche Aufgaben

**Servo-Motor:**
- Dreht sich zu einer bestimmten Position (0-180°)
- Präzise Steuerung
- Eingebaute Regelung
- Beispiel: Roboterarm, Lenkung

**DC-Motor:**
- Dreht sich kontinuierlich
- Geschwindigkeit durch Spannung steuerbar
- Einfach, günstig, stark
- Beispiel: Ventilator, Fahrzeug-Antrieb

**Demo:**
- Zeige beide Motor-Typen
- Lass sie kurz laufen

### 2. Projekt 1: Servo-Motor steuern (20 Min.)

**Was ist ein Servo?**
- 3 Kabel: Rot (5V), Braun/Schwarz (GND), Orange/Gelb (Signal)
- Dreht sich zu Position 0° bis 180°
- Bleibt an Position stehen

**Aufbau:**
```
Servo:
- Rotes Kabel → Arduino 5V
- Braunes/Schwarzes Kabel → Arduino GND
- Oranges/Gelbes Kabel → Arduino Pin 9
```

**Code:**

```cpp
#include <Servo.h>

Servo myServo; // Servo-Objekt erstellen
int servoPin = 9;

void setup() {
  myServo.attach(servoPin); // Servo an Pin 9
}

void loop() {
  // Zu Position 0° drehen
  myServo.write(0);
  delay(1000);
  
  // Zu Position 90° drehen (Mitte)
  myServo.write(90);
  delay(1000);
  
  // Zu Position 180° drehen
  myServo.write(180);
  delay(1000);
}
```

**Teste:**
- Der Servo bewegt sich hin und her!

**Experiment: Servo-Sweep**
```cpp
void loop() {
  // Von 0° bis 180°
  for(int pos = 0; pos <= 180; pos++) {
    myServo.write(pos);
    delay(15);
  }
  
  // Zurück von 180° bis 0°
  for(int pos = 180; pos >= 0; pos--) {
    myServo.write(pos);
    delay(15);
  }
}
```

### 3. Projekt 2: Servo mit Potentiometer (15 Min.)

**Aufgabe:**
Steuere den Servo mit einem Drehregler!

**Zusätzliches Material:**
- 1x Potentiometer

**Aufbau:**
- Servo wie vorher
- Potentiometer: Links=5V, Mitte=A0, Rechts=GND

**Code:**

```cpp
#include <Servo.h>

Servo myServo;
int servoPin = 9;
int potiPin = A0;

void setup() {
  myServo.attach(servoPin);
}

void loop() {
  int potiValue = analogRead(potiPin); // 0-1023
  int angle = map(potiValue, 0, 1023, 0, 180); // Umrechnen zu 0-180°
  
  myServo.write(angle);
  delay(15);
}
```

**Teste:**
- Drehe am Potentiometer → Servo folgt!

**Projekt-Ideen:**
- Baue einen Roboterarm
- Steuer eine Barriere
- Mach eine Winkmaschine

### 4. Projekt 3: DC-Motor mit Transistor (25 Min.)

**Warum Transistor?**
- Arduino-Pins geben max. 40mA
- Motoren brauchen oft 100-500mA
- Transistor = Elektrischer Schalter für hohe Ströme

**Aufbau (wichtig: genau so!):**
```
Arduino Pin 9 → 1kΩ Widerstand → Transistor Basis (mittlerer Pin)
Transistor Emitter (links) → Arduino GND
Transistor Kollektor (rechts) → DC-Motor (-) 
DC-Motor (+) → Batterie (+)
Batterie (-) → Arduino GND (gemeinsam!)
Diode: Parallel zum Motor (Kathode zu Batterie +)
```

**Transistor BC547 Pins:**
```
Flache Seite zu dir:
  C  B  E
  |  |  |
Kollektor Basis Emitter
```

**Code:**

```cpp
int motorPin = 9;

void setup() {
  pinMode(motorPin, OUTPUT);
}

void loop() {
  // Motor an (volle Geschwindigkeit)
  digitalWrite(motorPin, HIGH);
  delay(2000);
  
  // Motor aus
  digitalWrite(motorPin, LOW);
  delay(2000);
}
```

**Teste:**
- Motor dreht sich 2 Sek., stoppt 2 Sek., wiederholt

**Geschwindigkeitssteuerung mit PWM:**
```cpp
void loop() {
  // Langsam
  analogWrite(motorPin, 64); // 25%
  delay(2000);
  
  // Mittel
  analogWrite(motorPin, 128); // 50%
  delay(2000);
  
  // Schnell
  analogWrite(motorPin, 255); // 100%
  delay(2000);
}
```

### 5. Projekt: Ventilator mit Temperaturregelung (25 Min.)

**Aufgabe:**
Baue einen automatischen Ventilator!

**Material:**
- DC-Motor mit Propeller
- Temperatursensor (TMP36)
- Transistor-Schaltung

**Code:**

```cpp
int motorPin = 9;
int tempPin = A0;

void setup() {
  pinMode(motorPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // Temperatur messen
  int sensorValue = analogRead(tempPin);
  float voltage = sensorValue * (5.0 / 1023.0);
  float temperature = (voltage - 0.5) * 100.0;
  
  Serial.print("Temperatur: ");
  Serial.print(temperature);
  Serial.print(" °C | Motor: ");
  
  // Motor-Geschwindigkeit basierend auf Temperatur
  if(temperature < 22) {
    analogWrite(motorPin, 0); // Aus
    Serial.println("AUS (kalt)");
  } else if(temperature < 25) {
    analogWrite(motorPin, 128); // 50%
    Serial.println("MITTEL (warm)");
  } else {
    analogWrite(motorPin, 255); // 100%
    Serial.println("VOLL (heiß)");
  }
  
  delay(1000);
}
```

**Teste:**
- Halte Hand auf Temperatursensor
- Motor dreht schneller bei Wärme!

### 6. Bonus: Mini-Roboter (20 Min.)

**Aufgabe:**
Baue einen einfachen fahrbaren Roboter!

**Material:**
- 2x DC-Motoren mit Rädern
- 2x Transistor-Schaltungen
- Chassis (Karton oder Bastelplatte)
- Batterien

**Einfache Steuerung:**
```cpp
int motor1Pin = 9;
int motor2Pin = 10;

void setup() {
  pinMode(motor1Pin, OUTPUT);
  pinMode(motor2Pin, OUTPUT);
}

void loop() {
  // Vorwärts
  digitalWrite(motor1Pin, HIGH);
  digitalWrite(motor2Pin, HIGH);
  delay(2000);
  
  // Stopp
  digitalWrite(motor1Pin, LOW);
  digitalWrite(motor2Pin, LOW);
  delay(1000);
  
  // Rechts drehen (nur Motor 1)
  digitalWrite(motor1Pin, HIGH);
  digitalWrite(motor2Pin, LOW);
  delay(1000);
  
  // Stopp
  digitalWrite(motor1Pin, LOW);
  digitalWrite(motor2Pin, LOW);
  delay(1000);
}
```

### 7. Präsentation (10 Min.)

**Zeigt eure Projekte:**
- Was bewegt sich in eurem Projekt?
- Wie steuert ihr die Bewegung?
- Welche Sensoren habt ihr verwendet?

### 8. Freies Experimentieren (15 Min.)

**Weitere Ideen:**
- Hindernisvermeider (Ultraschall-Sensor)
- Linienfolger (Lichtsensoren)
- Roboterarm mit mehreren Servos
- Ferngesteuertes Auto (mit serieller Steuerung)

## 💡 Tipps für Betreuer

### Vorbereitung
- Transistor-Schaltung vorher testen
- Freilaufdiode nicht vergessen! (Wichtig!)
- Batterien prüfen
- Propeller sicher befestigen

### Häufige Probleme

**"Motor dreht nicht"**
- Transistor richtig herum? (C-B-E beachten!)
- Basis-Widerstand vorhanden? (1kΩ)
- Gemeinsame GND-Verbindung?
- Batterie voll?

**"Motor dreht langsam"**
- Batterie schwach?
- PWM-Wert zu niedrig?
- Motor zu groß für Transistor?

**"Arduino stürzt ab"**
- Motor direkt an Arduino? (FALSCH!)
- Immer Transistor verwenden!
- Separate Spannungsversorgung für Motor

**"Servo zuckt"**
- Zu viel Last?
- Nicht genug Strom (verwende ggf. externe 5V)

### Differenzierung
- **Schnelle Kinder:** Zwei Motoren, H-Brücke für Richtungswechsel
- **Jüngere Kinder:** Nur Servo, einfache Bewegungen
- **Ältere Kinder:** PWM-Theorie, Transistor-Funktion erklären

## 🎓 Wichtige Konzepte

### Transistor als Schalter
- Basis: Steuereingang (Arduino)
- Kollektor/Emitter: Schalterstrecke (Motor)
- Kleiner Basis-Strom schaltet großen Motor-Strom

### Freilaufdiode
- Schützt vor Spannungsspitzen beim Motor-Ausschalten
- Motor = Spule → erzeugt Gegenspannung
- Diode: Parallel zum Motor, Kathode zu +

### PWM (Pulse Width Modulation)
- Ein/Aus-Schaltung sehr schnell
- Duty Cycle: 0% = aus, 100% = voll an
- Motor merkt es als durchschnittliche Spannung

### Servo-Bibliothek
- `#include <Servo.h>`: Bibliothek einbinden
- `myServo.attach(pin)`: Servo an Pin anschließen
- `myServo.write(winkel)`: Position setzen

## 🔒 Sicherheitshinweise

- ✅ Servo am Arduino ist sicher (max. 500mA)
- ⚠️ DC-Motoren immer mit Transistor!
- ⚠️ Freilaufdiode ist wichtig (sonst Arduino-Schaden!)
- ⚠️ Propeller können abfliegen → Befestigen!
- ❌ Motor nie direkt zwischen 5V und GND
- ❌ Nicht in drehende Teile fassen

## 📸 Dokumentation

- Fotos vom Transistor-Aufbau
- Videos von bewegten Projekten
- Schaltplan skizzieren
- Servo-Positionen dokumentieren

## 🏠 Hausaufgaben (optional)

1. **Beobachtung:**
   - Finde 5 Dinge zu Hause mit Motoren
   - Welche Motor-Art könnten sie verwenden?

2. **Planung:**
   - Skizziere einen eigenen Roboter
   - Welche Sensoren und Motoren bräuchtest du?

3. **Recherche:**
   - Wie funktioniert ein Schrittmotor?
   - Was ist eine H-Brücke?

## 📚 Weiterführende Ressourcen

- **Motor-Shield:** Vereinfacht Motorsteuerung
- **H-Brücke:** L293D, L298N für Richtungswechsel
- **Schrittmotoren:** Präzise Positionierung
- **Bürstenlose Motoren:** Für Drohnen
- **YouTube:** "Arduino Motor Control Tutorial"

## 🎁 Projekt-Ideen für Fortgeschrittene

- Linienfolgender Roboter
- Hindernisvermeider mit Ultraschall
- Roboterarm mit mehreren Servos
- Ferngesteuertes Auto (Bluetooth)
- Plotter/Zeichenroboter
- Drohne (sehr fortgeschritten!)

---

**Vorheriges Modul:** [Modul 5: Sensoren erkunden](../modul_05_sensoren/)  
**Nächstes Modul:** [Modul 7: Eigene Projekte entwickeln](../modul_07_projekte/)
