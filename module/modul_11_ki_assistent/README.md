# Modul 11: KI als Lernassistent - Weitermachen mit eigenem Wissen

**Zielgruppe:** Ab 6. Klasse (nach allen vorherigen Modulen)  
**Dauer:** 1,5 Stunden  
**Schwierigkeitsgrad:** ⭐⭐⭐⭐ Fortgeschritten

## 🎯 Lernziele

- KI-Tools wie GitHub Copilot, ChatGPT, Claude kennenlernen
- Verstehen, wie KI beim Lernen und Entwickeln hilft
- Effektive Fragen an KI stellen (Prompt Engineering)
- KI für Elektronik-Schaltungen nutzen
- KI für Programmierung einsetzen
- Eigenständig Hardware/Software-Projekte mit KI-Unterstützung umsetzen

## 📦 Benötigte Materialien

### Hardware
- Computer mit Internetzugang (1 pro Team)
- Arduino Uno + Breadboard + Bauteile aus vorherigen Modulen
- Optional: GitHub Account (für Copilot)

### Software
- Webbrowser
- Arduino IDE
- Zugang zu KI-Tools:
  - ChatGPT (kostenlos: chat.openai.com)
  - Claude (kostenlos: claude.ai)
  - GitHub Copilot (kostenlos für Studenten/Bildung)
  - Perplexity (kostenlos: perplexity.ai)

## 📖 Kursablauf

### 1. Einführung: Was ist KI? (10 Min.)

**Was ist Künstliche Intelligenz?**
- Computer, die "denken" und "lernen" können
- Trainiert mit riesigen Mengen an Informationen
- Kann Fragen beantworten, Code schreiben, Probleme lösen

**KI als Lernassistent:**
- Wie ein Lehrer, der immer verfügbar ist
- Erklärt Konzepte
- Hilft bei Fehlern
- Gibt Vorschläge und Ideen

**Wichtig:**
- ❌ KI ist nicht perfekt - manchmal macht sie Fehler!
- ✅ KI ist ein Werkzeug - du musst verstehen, was sie vorschlägt
- ✅ Kombiniere KI mit eigenem Wissen aus den Modulen 1-10

**Zeige Live-Demo:**
Stelle eine einfache Frage an ChatGPT:
"Erkläre einem 12-Jährigen, wie eine LED funktioniert."

### 2. Teil 1: KI für Elektronik-Fragen (25 Min.)

#### 2.1 Schaltungen verstehen und planen

**Aufgabe 1: Schaltung erklären lassen**

Nehmt eine Schaltung aus Modul 5 (z.B. LED mit Temperatursensor).

**Prompt an KI:**
```
Ich habe folgende Schaltung aufgebaut:
- Arduino Uno
- TMP36 Temperatursensor an Pin A0
- LED an Pin 9 mit 220Ω Widerstand
- LED soll leuchten, wenn Temperatur > 25°C

Kannst du mir Schritt für Schritt erklären, wie diese Schaltung funktioniert?
```

**Was die KI tut:**
- Erklärt jeden Bauteil
- Beschreibt den Stromfluss
- Erklärt die Logik

**Aufgabe 2: Neue Schaltung planen**

**Prompt:**
```
Ich möchte eine Schaltung bauen mit:
- 5 LEDs in verschiedenen Farben
- Sollen nacheinander angehen (Lauflicht)
- Arduino Uno verwenden

Welche Bauteile brauche ich und wie schließe ich sie an?
```

**KI-Antwort analysieren:**
- Ist die Teileliste vollständig?
- Macht der Schaltplan Sinn?
- Passen die Pin-Nummern?

**Lernziel:**
Kritisch prüfen, was die KI vorschlägt!

#### 2.2 Probleme debuggen

**Szenario:** LED leuchtet nicht

**Schlechter Prompt:**
```
Meine LED funktioniert nicht.
```

**Guter Prompt:**
```
Meine LED-Schaltung funktioniert nicht. Details:
- Arduino Uno
- LED an Pin 9, Kathode (kurzes Bein) an GND
- 220Ω Widerstand zwischen Pin 9 und LED-Anode
- Code: digitalWrite(9, HIGH)
- LED leuchtet nicht

Was könnte das Problem sein?
```

**KI gibt strukturierte Checkliste:**
1. Pin als OUTPUT definiert?
2. LED richtig herum?
3. Widerstand korrekt?
4. Code hochgeladen?
5. Stromversorgung?

**Übung:**
Beschreibe dein eigenes Problem aus früheren Modulen und lass die KI helfen!

#### 2.3 Bauteil-Informationen

**Prompt-Beispiele:**
```
Was ist der Unterschied zwischen einem Servo-Motor und einem DC-Motor?

Welchen Widerstand brauche ich für eine rote LED mit 20mA bei 5V?

Wie funktioniert ein Ultraschall-Sensor HC-SR04?
```

**Tipp:** Frage immer nach Quellen zum Weiterlesen!

### 3. Teil 2: KI für Programmierung (30 Min.)

#### 3.1 Code-Snippets generieren

**Aufgabe:** Blinkende LED (aus Modul 7)

**Prompt an KI:**
```
Schreibe Arduino-Code für:
- LED an Pin 13
- Soll 3x schnell blinken (200ms)
- Dann 2 Sekunden Pause
- Dann wiederholen

Erkläre jeden Teil des Codes.
```

**KI-generierter Code:**
```cpp
// LED Blink Muster
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // 3x schnell blinken
  for(int i = 0; i < 3; i++) {
    digitalWrite(ledPin, HIGH);
    delay(200);
    digitalWrite(ledPin, LOW);
    delay(200);
  }
  
  // 2 Sekunden Pause
  delay(2000);
}
```

**Code-Review mit KI:**
- Lass dir jeden Befehl erklären
- Frage: "Was macht die for-Schleife?"
- Experimentiere: "Wie ändere ich es für 5x blinken?"

#### 3.2 Code verbessern

**Aufgabe:** Code aus Modul 8 optimieren

Zeige der KI deinen Code:
```
Hier ist mein Arduino-Code für einen Temperatursensor:

[Dein Code einfügen]

Kannst du diesen Code verbessern?
- Besser lesbar machen
- Erklärende Kommentare hinzufügen
- Best Practices anwenden
```

**KI zeigt:**
- Bessere Variablennamen
- Hilfreiche Kommentare
- Optimierungen

#### 3.3 Fehler finden (Debugging)

**Prompt:**
```
Mein Arduino-Code kompiliert nicht. Hier ist der Code:

int ledPin = 13

void setup() {
  PinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, high);
  delay(1000);
}

Was ist falsch?
```

**KI findet:**
1. Semikolon fehlt in Zeile 1
2. `PinMode` → `pinMode` (Groß-/Kleinschreibung)
3. `high` → `HIGH` (Konstante großgeschrieben)

**Übung:**
Baue absichtlich Fehler in deinen Code ein und lass KI helfen!

#### 3.4 Neue Funktionen lernen

**Prompt:**
```
Ich kenne digitalWrite() für an/aus.
Wie kann ich die Helligkeit einer LED steuern?
Erkläre es für Arduino-Anfänger.
```

**KI erklärt:**
- PWM (Pulse Width Modulation)
- `analogWrite()` Funktion
- Welche Pins funktionieren (PWM-fähige)
- Beispielcode

**Prompt-Kette:**
```
1. "Was ist PWM?"
2. "Zeige mir ein Beispiel mit LED-Fading"
3. "Wie kombiniere ich das mit einem Potentiometer?"
```

### 4. Teil 3: Hardware + Software Projekt mit KI (35 Min.)

#### 4.1 Projekt-Idee entwickeln

**Brainstorming mit KI:**
```
Ich habe folgende Komponenten:
- Arduino Uno
- 3 LEDs (rot, gelb, grün)
- Ultraschall-Sensor HC-SR04
- Summer/Buzzer
- Taster

Schlage 3 interessante Projekte vor, die ich damit bauen kann.
Projekte sollten für Anfänger geeignet sein.
```

**KI schlägt vor:**
1. Einpark-Assistent (Entfernung → LEDs)
2. Reaktionsspiel mit LEDs
3. Ultraschall-Alarm-System

**Wähle ein Projekt aus!**

#### 4.2 Projekt mit KI umsetzen

**Schritt-für-Schritt mit KI:**

**Schritt 1: Schaltplan**
```
Projekt: Einpark-Assistent
Wie schließe ich die Bauteile an?
Erstelle eine Pin-Liste.
```

**Schritt 2: Code-Struktur**
```
Für den Einpark-Assistent:
Welche Funktionen brauche ich?
Wie ist der Code strukturiert?
```

**Schritt 3: Code schreiben**
```
Schreibe den Arduino-Code für:
- Entfernung mit HC-SR04 messen
- Grüne LED bei > 50cm
- Gelbe LED bei 20-50cm
- Rote LED + Summer bei < 20cm
```

**Schritt 4: Testen und Debuggen**
```
Der Sensor gibt komische Werte aus (immer 0).
Mein Code: [Code einfügen]
Was ist falsch?
```

**Schritt 5: Verbessern**
```
Wie kann ich folgende Features hinzufügen:
- Blink-Frequenz steigt bei näherem Abstand
- Lautstärke des Summers anpassen
```

#### 4.3 Live-Coding mit KI

**Gemeinsames Projekt (alle Teams):**
Einpark-Assistent mit KI-Unterstützung bauen

**Workflow:**
1. Team stellt Frage an KI
2. KI gibt Antwort
3. Team setzt es um
4. Testen
5. Bei Problemen: KI um Hilfe fragen
6. Iterieren

**Dokumentation:**
- Welche Fragen habt ihr gestellt?
- Welche Antworten waren hilfreich?
- Wo hat KI Fehler gemacht?

### 5. Best Practices: Effektiv mit KI arbeiten (10 Min.)

#### 5.1 Gute Prompts schreiben

**Schlecht:**
```
Mach mir einen Code.
```

**Gut:**
```
Schreibe Arduino-Code für:
- [Genaue Beschreibung]
- [Verwendete Bauteile]
- [Erwartetes Verhalten]
Erkläre den Code Schritt für Schritt.
```

**Template für gute Prompts:**
```
Kontext: [Was habe ich schon gelernt/gemacht]
Aufgabe: [Was möchte ich erreichen]
Details: [Bauteile, Pins, spezifische Anforderungen]
Erwartung: [Code / Erklärung / Schaltplan]
Zielgruppe: [Anfänger / Fortgeschritten]
```

#### 5.2 KI-Antworten validieren

**Checkliste:**
- ✅ Macht die Antwort logisch Sinn?
- ✅ Passen die Bauteile, die ich habe?
- ✅ Verstehe ich, was der Code tut?
- ✅ Kann ich es selbst erklären?
- ❌ Blindes Copy-Paste → Schlecht!
- ✅ Verstehen und anpassen → Gut!

**Wenn KI falsch liegt:**
- Stelle Nachfragen
- Gebe mehr Kontext
- Vergleiche mehrere KI-Antworten
- Frage Betreuer

#### 5.3 KI-Tools im Vergleich

| Tool | Stärken | Schwächen | Kosten |
|------|---------|-----------|--------|
| **ChatGPT** | Sehr gute Erklärungen, Code-Generierung | Manchmal veraltete Infos | Kostenlos / Plus |
| **Claude** | Lange Konversationen, sehr höflich | Manchmal zu vorsichtig | Kostenlos / Pro |
| **GitHub Copilot** | In IDE integriert, Code-Completion | Braucht Kontext aus Code | Kostenlos (Bildung) |
| **Perplexity** | Sucht aktuelle Infos, gibt Quellen | Weniger Code-fokussiert | Kostenlos / Pro |

**Tipp:** Nutze mehrere Tools und vergleiche!

### 6. Präsentation und Reflexion (10 Min.)

**Projekt-Präsentation:**
- Zeigt euer Hardware/Software-Projekt
- Welche KI-Tools habt ihr verwendet?
- Was hat besonders geholfen?
- Wo hatte KI Probleme?

**Diskussion:**
- Wo ist KI hilfreich?
- Wo ist menschliche Kreativität wichtiger?
- Wann sollte man KI nutzen?
- Wann sollte man selbst überlegen?

## 💡 Tipps für Betreuer

### Vorbereitung
- Teste alle KI-Tools vorher
- Bereite Beispiel-Prompts vor
- Habe Backup, falls Internet ausfällt
- Überlege Datenschutz (keine persönlichen Daten in KI!)

### Ethik und verantwortungsvoller Umgang

**Wichtig zu vermitteln:**
- ✅ KI ist ein Werkzeug zum Lernen
- ✅ Verstehen ist wichtiger als Copy-Paste
- ✅ KI kann Fehler machen
- ❌ Nicht blind vertrauen
- ❌ Keine Aufgaben komplett von KI machen lassen ohne zu verstehen

### Alternativen ohne Internet

Falls kein Internet verfügbar:
- Offline-Tools vorbereiten
- Screenshots von KI-Konversationen
- Vorbereitete KI-Antworten zu typischen Fragen
- Fokus auf Methodik, nicht konkrete Tools

## 🎓 Was haben wir gelernt?

### KI-Kompetenz
- Wie man effektive Fragen stellt
- Wie man Antworten validiert
- Verschiedene KI-Tools kennen
- KI als Lernassistent nutzen

### Eigenständiges Lernen
- Mit KI kann man weitermachen
- Neue Bauteile selbst erkunden
- Komplexere Projekte angehen
- Probleme selbstständig lösen

### Kritisches Denken
- KI-Antworten hinterfragen
- Fehler erkennen
- Quellen überprüfen
- Eigenes Wissen anwenden

## 🚀 Nach dem Kurs: Weitermachen!

### Lernpfade mit KI

**Für Elektronik:**
```
Prompt-Kette für neuen Sensor:
1. "Was ist ein [Sensor-Name] und wofür wird er verwendet?"
2. "Wie schließe ich [Sensor] an Arduino an?"
3. "Zeige mir Beispiel-Code für [Sensor]"
4. "Wie kann ich [Sensor] in mein Projekt [X] integrieren?"
```

**Für Programmierung:**
```
Lernpfad für neue Konzepte:
1. "Erkläre [Konzept] für Arduino-Anfänger"
2. "Zeige mir ein einfaches Beispiel"
3. "Wie verwende ich [Konzept] mit [Hardware]?"
4. "Zeige mir ein fortgeschrittenes Beispiel"
```

### Projekt-Ideen zum Weitermachen

**Mit KI-Unterstützung machbar:**
1. **Smart Home Mini:** Licht + Temperatur + Display
2. **Roboter-Auto:** Mit Hindernis-Vermeidung
3. **Wetterstation:** Sensoren + Daten-Logging
4. **MIDI-Instrument:** Musik mit Arduino
5. **IoT-Projekt:** Arduino + WiFi

**Für jedes Projekt:**
- Lass KI helfen, aber verstehe jeden Schritt!
- Dokumentiere deine Fragen und Antworten
- Teile dein Wissen mit anderen

## 📚 Ressourcen

### KI-Tools (Stand 2025)
- **ChatGPT:** chat.openai.com
- **Claude:** claude.ai
- **GitHub Copilot:** github.com/copilot
- **Perplexity:** perplexity.ai

### Lern-Plattformen mit KI
- **Arduino Project Hub:** Mit KI nach Projekten suchen
- **Instructables:** KI hilft, Anleitungen zu verstehen
- **Stack Overflow:** Fragen + KI-gestützte Suche

### Communities
- Arduino Forum
- Reddit r/arduino
- Discord-Server für Maker
- Lokale Maker-Spaces (wie ZAM Erlangen!)

## ⚠️ Wichtige Hinweise

### Datenschutz
- Keine persönlichen Daten in KI eingeben
- Keine Fotos von Personen hochladen
- Bei Unsicherheit: Betreuer fragen

### Verantwortung
- Überprüfe Code vor dem Hochladen
- Verstehe, was der Code macht
- Teste sicher (keine gefährlichen Spannungen!)

### Lernen vs. Abschreiben
- ✅ KI nutzen zum Verstehen
- ✅ KI als Lehrer sehen
- ❌ Nicht blind kopieren
- ❌ Nicht als Ersatz für eigenes Denken

## 🎉 Gratulation!

Ihr habt nun:
- ✅ Grundlagen der Elektronik gelernt (Module 1-5)
- ✅ Programmierung verstanden (Module 6-7)
- ✅ Fortgeschrittene Themen gemeistert (Module 8-10)
- ✅ KI als Werkzeug kennengelernt (Modul 11)

**Ihr seid bereit, eigene Projekte zu entwickeln!**

Die Kombination aus:
- Eurem Wissen (Module 1-10)
- KI als Assistent (Modul 11)
- Kreativität und Neugier

...macht euch zu selbstständigen Makern! 🔧⚡💻

**Viel Erfolg bei euren zukünftigen Projekten!**

---

**Vorheriges Modul:** [Modul 10: Eigene Projekte entwickeln](../modul_10_projekte/)

**Ende des Kurses** - Aber Anfang eurer Maker-Reise! 🚀
