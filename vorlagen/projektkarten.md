# Projektkarten für freies Experimentieren

Diese Karten können ausgedruckt und laminiert werden, um Kindern Ideen für eigene Projekte zu geben.

---

## 🔵 Projekt: Nachtlicht

**Level:** ⭐ Einfach  
**Zeit:** 20-30 Min.

### Du brauchst:
- Arduino
- LDR (Lichtsensor)
- 10kΩ Widerstand
- LED
- 220Ω Widerstand

### Aufgabe:
Baue ein Licht, das automatisch angeht, wenn es dunkel wird!

### Tipp:
Nutze `analogRead()` für den Sensor und `if()` für die Entscheidung.

---

## 🟢 Projekt: Ampel

**Level:** ⭐ Einfach  
**Zeit:** 30 Min.

### Du brauchst:
- Arduino
- 3 LEDs (rot, gelb, grün)
- 3x 220Ω Widerstände

### Aufgabe:
Programmiere eine Ampel mit realistischen Phasen!

### Bonus:
Füge eine Fußgängerampel mit Taster hinzu.

---

## 🟡 Projekt: Temperatur-Alarm

**Level:** ⭐⭐ Mittel  
**Zeit:** 30-40 Min.

### Du brauchst:
- Arduino
- TMP36 Temperatursensor
- LED
- Summer

### Aufgabe:
Baue ein Warnsystem, das bei zu hoher Temperatur Alarm schlägt!

### Tipp:
Zeige die Temperatur im Serial Monitor an.

---

## 🟠 Projekt: Reaktionsspiel

**Level:** ⭐⭐ Mittel  
**Zeit:** 40-50 Min.

### Du brauchst:
- Arduino
- 3 LEDs verschiedene Farben
- 3 Taster
- Summer (optional)

### Aufgabe:
Eine LED leuchtet zufällig auf. Drücke schnell die richtige Taste!

### Bonus:
Miss die Reaktionszeit mit `millis()`.

---

## 🔴 Projekt: Servo-Roboterarm

**Level:** ⭐⭐⭐ Fortgeschritten  
**Zeit:** 60 Min.

### Du brauchst:
- Arduino
- 2-3 Servos
- Potentiometer (für jeden Servo)
- Karton oder LEGO

### Aufgabe:
Baue einen Arm, den du mit Drehreglern steuerst!

### Bonus:
Programmiere eine automatische Bewegung.

---

## 🟣 Projekt: Hindernisvermeider

**Level:** ⭐⭐⭐⭐ Fortgeschritten  
**Zeit:** 90+ Min.

### Du brauchst:
- Arduino
- HC-SR04 Ultraschall-Sensor
- 2 DC-Motoren
- 2 Transistoren
- Chassis mit Rädern

### Aufgabe:
Baue einen Roboter, der automatisch Hindernissen ausweicht!

### Tipp:
Miss Entfernung und drehe bei < 20cm.

---

## 🟤 Projekt: Wetterstation

**Level:** ⭐⭐⭐ Mittel  
**Zeit:** 60 Min.

### Du brauchst:
- Arduino
- DHT11 (Temperatur + Luftfeuchte)
- LCD-Display (optional)
- LEDs für Status-Anzeige

### Aufgabe:
Miss Temperatur und Luftfeuchtigkeit und zeige sie an!

### Bonus:
Speichere Werte auf SD-Karte.

---

## ⚪ Projekt: Morse-Code Sender

**Level:** ⭐⭐ Mittel  
**Zeit:** 40 Min.

### Du brauchst:
- Arduino
- LED
- Taster
- Summer (optional)

### Aufgabe:
Sende SOS oder deinen Namen in Morse-Code!

### Morse-Code:
- Kurz = 200ms
- Lang = 600ms
- SOS = • • • — — — • • •

---

## 🔵 Projekt: LED-Würfel

**Level:** ⭐ Einfach  
**Zeit:** 30 Min.

### Du brauchst:
- Arduino
- 7 LEDs (oder 6)
- 7x 220Ω Widerstände
- Taster

### Aufgabe:
Erstelle einen elektronischen Würfel! Taste drücken = Zufallszahl.

### Tipp:
Nutze `random(1, 7)` für Zahlen 1-6.

---

## 🟢 Projekt: Pflanzen-Monitor

**Level:** ⭐⭐ Mittel  
**Zeit:** 40 Min.

### Du brauchst:
- Arduino
- Bodenfeuchte-Sensor
- LED (rot/grün)
- Summer

### Aufgabe:
Warne, wenn die Pflanze Wasser braucht!

### Bonus:
Messe auch Licht und Temperatur.

---

## 🟡 Projekt: Lauflicht

**Level:** ⭐ Einfach  
**Zeit:** 30 Min.

### Du brauchst:
- Arduino
- 8-10 LEDs
- 8-10x 220Ω Widerstände

### Aufgabe:
Erstelle ein Lauflicht (Knight Rider Style)!

### Bonus:
Ändere Geschwindigkeit mit Potentiometer.

---

## 🟠 Projekt: Quiz-Buzzer

**Level:** ⭐ Einfach  
**Zeit:** 30 Min.

### Du brauchst:
- Arduino
- 4 Taster
- 4 LEDs verschiedene Farben
- Summer

### Aufgabe:
Wer zuerst drückt, dessen LED leuchtet!

### Bonus:
Zeige Punkte auf LCD-Display.

---

## 🔴 Projekt: Entfernungsmesser

**Level:** ⭐⭐⭐ Mittel  
**Zeit:** 40 Min.

### Du brauchst:
- Arduino
- HC-SR04 Ultraschall
- 5 LEDs
- 5x 220Ω Widerstände

### Aufgabe:
Zeige Entfernung mit LED-Balken an (näher = mehr LEDs)!

### Tipp:
Entfernung = `duration * 0.034 / 2` (in cm)

---

## 🟣 Projekt: Linienfolger

**Level:** ⭐⭐⭐⭐ Fortgeschritten  
**Zeit:** 90+ Min.

### Du brauchst:
- Arduino
- 2 Infrarot-Sensoren
- 2 DC-Motoren
- Chassis
- Schwarze Linie auf weißem Papier

### Aufgabe:
Baue einen Roboter, der einer Linie folgt!

### Tipp:
Wenn links Linie → rechts steuern.

---

## 🟤 Projekt: Musik-Box

**Level:** ⭐⭐ Mittel  
**Zeit:** 50 Min.

### Du brauchst:
- Arduino
- Summer/Buzzer
- 8 Taster
- Widerstände

### Aufgabe:
Baue ein einfaches Keyboard! Jede Taste = ein Ton.

### Töne:
C=262Hz, D=294Hz, E=330Hz, F=349Hz, G=392Hz, A=440Hz, B=494Hz

### Tipp:
Nutze `tone(pin, frequency)`.

---

## ⚪ Projekt: Automatische Türklingel

**Level:** ⭐⭐ Mittel  
**Zeit:** 40 Min.

### Du brauchst:
- Arduino
- PIR Bewegungssensor
- Summer
- LED

### Aufgabe:
Klingel läutet, wenn sich jemand nähert!

### Bonus:
Zähle Besucher mit.

---

## Eigene Projekt-Idee

**Level:** _______  
**Zeit:** _______ Min.

### Du brauchst:
- 
- 
- 

### Aufgabe:
_____________________________________________
_____________________________________________
_____________________________________________

### Skizze:



---

**Tipp:** Kombiniere mehrere Projekte für komplexere Systeme!
