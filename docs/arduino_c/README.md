---
mathjax:
  presets: '\def\lr#1#2#3{\left#1#2\right#3}'
---



# Cursus: Arduino C Programmeren voor Beginners

---

## Inleiding

Deze cursus is ontworpen om beginners kennis te laten maken met de basisprincipes van programmeren in C voor de Arduino-microcontroller. De cursus begint met de basisconcepten van programmeren en gaat verder met meer geavanceerde technieken. Aan het einde van de cursus zul je in staat zijn om je eigen projecten te ontwikkelen en de Arduino-microcontroller effectief te gebruiken.

---

## Week 1: Introductie tot Arduino en de C Programmeertaal

### 1.1 Wat is Arduino?
- Inleiding tot de Arduino-hardware
- De Arduino IDE (Integrated Development Environment)
- Verschillende soorten Arduino-borden

### 1.2 Basisprincipes van de C Programmeertaal

#### Variabelen en Datatypes
- **Wat is een variabele?**
  - Een variabele is een opslagplaats in het geheugen van de Arduino waarin je gegevens kunt opslaan die je programma gebruikt of bewerkt. Bijvoorbeeld: het opslaan van een getal dat een sensorwaarde vertegenwoordigt.
- **Soorten variabelen:**
  - `int`: Geheel getal, bijvoorbeeld `int ledPin = 13;`
  - `float`: Kommagetal, bijvoorbeeld `float temperatuur = 23.5;`
  - `char`: Enkel karakter, bijvoorbeeld `char letter = 'A';`
  - `boolean`: Waar of niet waar (true of false), bijvoorbeeld `boolean isAan = true;`

#### Operators
- **Toewijzingsoperator (`=`):** Gebruikt om een waarde toe te wijzen aan een variabele, bijvoorbeeld `int x = 10;`
- **Wiskundige operators:** Optellen (`+`), aftrekken (`-`), vermenigvuldigen (`*`), delen (`/`), bijvoorbeeld `int resultaat = 5 + 3;`
- **Vergelijkingsoperators:** Groter dan (`>`), kleiner dan (`<`), gelijk aan (`==`), bijvoorbeeld `if (x > 5)`

### 1.3 Eerste Project: Knipperende LED
- Wat is een LED?
- Het ‘Blink’ voorbeeldprogramma in de Arduino IDE
- Uploaden van je eerste programma naar de Arduino
- Analyseren van de code

#### Oefeningen:
- Verander de knippersnelheid van de LED
- Voeg een tweede LED toe en laat deze afwisselend knipperen

---

## Week 2: Werken met Invoer en Uitvoer

### 2.1 Digitaal en Analoog Invoer/Output
- Verschil tussen digitale en analoge signalen
- Digitaal lezen en schrijven (`digitalRead()` en `digitalWrite()`)
- Analoog lezen en schrijven (`analogRead()` en `analogWrite()`)

### 2.2 Werken met Knoppen
- Wat is een pull-up en pull-down weerstand?
- Lezen van een knoptoestand en reageren op invoer

### 2.3 Project: LED aansturen met een knop
- LED aan- en uitschakelen met behulp van een drukknop
- Analyseren van debounce-problemen en oplossingen

#### Oefeningen:
- Implementeer een LED-dimmer met een potentiometer
- Gebruik een LDR-sensor om de helderheid van de LED te regelen

---

## Week 3: Control Structures, Selecties en Iteraties

### 3.1 Control Structures

#### Selecties (Voorwaardelijke logica)
- **`if`-statement:**
  - Een `if`-statement voert code uit als een bepaalde voorwaarde waar is. Bijvoorbeeld:
    ```c
    if (temperatuur > 25) {
        digitalWrite(ledPin, HIGH); // Zet LED aan als temperatuur groter is dan 25 graden
    }
    ```
- **`else if` en `else`:**
  - Gebruik `else if` en `else` om alternatieve acties te definiëren als de eerste voorwaarde niet waar is.
    ```c
    if (temperatuur > 25) {
        digitalWrite(ledPin, HIGH);
    } else {
        digitalWrite(ledPin, LOW);
    }
    ```

### 3.2 Iteraties (Lussen)
- **`for`-lus:**
  - Wordt gebruikt om een blok code meerdere keren uit te voeren, met een controle over het aantal herhalingen. Bijvoorbeeld:
    ```c
    for (int i = 0; i < 10; i++) {
        digitalWrite(ledPin, HIGH);
        delay(500);
        digitalWrite(ledPin, LOW);
        delay(500);
    }
    ```
- **`while`-lus:**
  - Voert code uit zolang een bepaalde voorwaarde waar is. Bijvoorbeeld:
    ```c
    while (digitalRead(knopPin) == LOW) {
        digitalWrite(ledPin, HIGH);
    }
    ```
- **`do...while`-lus:**
  - Vergelijkbaar met de `while`-lus, maar de code wordt minstens één keer uitgevoerd, ongeacht de conditie:
    ```c
    do {
        digitalWrite(ledPin, HIGH);
    } while (digitalRead(knopPin) == LOW);
    ```

### 3.3 Functies
- **Wat zijn functies en waarom gebruiken we ze?**
  - Functies zijn herbruikbare blokken code die een specifieke taak uitvoeren. Ze maken je code overzichtelijker en makkelijker te onderhouden.
- **Functies definiëren en oproepen:**
  - Een eenvoudige functie:
    ```c
    void zetLEDaan() {
        digitalWrite(ledPin, HIGH);
    }
    ```

- **Overdracht van parameters en het teruggeven van waarden:**
  - Een functie met parameters:
    ```c
    void knipperLED(int keer) {
        for (int i = 0; i < keer; i++) {
            digitalWrite(ledPin, HIGH);
            delay(500);
            digitalWrite(ledPin, LOW);
            delay(500);
        }
    }
    ```

### 3.4 Project: Verkeerslicht Simulatie
- Simuleer een verkeerslicht met behulp van LED’s
- Implementeer timers met `delay()` en `millis()`

#### Oefeningen:
- Pas de verkeerslichtsimulatie aan om een voetgangersknop toe te voegen
- Implementeer een nachtmodescenario met knipperende oranje LED’s

---

## Week 4: Werken met Sensoren en Seriële Communicatie

### 4.1 Introductie tot Sensoren
- Wat zijn sensoren en hoe werken ze met Arduino?
- Voorbeelden van sensoren: Temperatuursensoren, afstandssensoren

### 4.2 Lezen van Sensordata
- Interface met een temperatuursensor (bijv. LM35)
- Data lezen en verwerken

### 4.3 Seriële Communicatie
- Wat is seriële communicatie?
- Seriële monitor in de Arduino IDE gebruiken
- Verzenden en ontvangen van data via de seriële poort

### 4.4 Project: Seriële Weerstation
- Bouw een eenvoudig weerstation dat temperatuur en vochtigheid weergeeft op de seriële monitor
- Analyseer en log de data op je computer

#### Oefeningen:
- Voeg een lichtsensor toe om lichtintensiteit te meten
- Verstuur data naar een extern apparaat via seriële communicatie

---

## Week 5: Geavanceerde Onderwerpen en Projecten

### 5.1 Werken met Bibliotheken
- Wat zijn bibliotheken en hoe gebruik je ze?
- Installeren en gebruiken van externe bibliotheken (bijv. voor LCD-displays, motoren)

### 5.2 Geavanceerde I/O
- PWM (Pulse Width Modulation) en zijn toepassingen
- Aansturen van een servo- of DC-motor

### 5.3 Project: Een Automatisch Deursysteem
- Gebruik een ultrasone sensor om afstand te meten
- Aansturen van een servo om een deur automatisch te openen en sluiten

#### Oefeningen:
- Voeg een LCD-scherm toe om de gemeten afstand weer te geven
- Breid het project uit om handmatige bediening mogelijk te maken via een knop

---

## Week 6: Eigen Project en Afronding

### 6.1 Ontwikkel je Eigen Project
- Brainstorm over mogelijke projecten
- Plan je project: onderdelen, schema, functies
- Implementeer je project stap voor stap

### 6.2 Presentatie en Feedback
- Demonstreer je project aan de klas of online
- Feedbacksessie: wat ging goed, wat kan beter?

### 6.3 Afronding en Verdere Stappen
- Overzicht van wat je hebt geleerd
- Inleiding tot geavanceerde onderwerpen: communicatieprotocollen (I2C, SPI), draadloze communicatie (Bluetooth, WiFi)
- Suggesties voor verdere studie en projecten

---

## Benodigde Materialen
- Arduino (bij voorkeur Arduino Uno)
- Breadboard en verbindingsdraden
- LED's, weerstanden, drukknoppen, potentiometers
- Sensoren: temperatuursensor, LDR, ultrasone sensor
- Servo- of DC-motor (optioneel)
- USB-kabel om Arduino te verbinden met de computer
- Computer met Arduino IDE geïnstalleerd

---

## Evaluatie en Certificering
- Evaluatie op basis

 van wekelijkse oefeningen en het eindproject
- Certificaat van voltooiing na succesvolle afronding van de cursus

---

Deze cursus biedt een stevige basis om door te stromen naar meer geavanceerde Arduino-projecten en om de vaardigheden die je leert toe te passen in de echte wereld. Veel succes en vooral veel plezier met het ontdekken van de wereld van Arduino en elektronica!
