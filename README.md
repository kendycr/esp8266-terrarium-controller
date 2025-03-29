# ESP8266 Terrarium Controller 🦎

Een geavanceerde terrarium controller gebaseerd op de ESP8266 microcontroller met real-time monitoring en Firebase integratie.

## 📝 Beschrijving

Dit project biedt een complete oplossing voor het monitoren en beheren van een terrarium met twee zones (links en rechts). Het systeem meet temperatuur en luchtvochtigheid, stuurt verwarmingselementen aan en biedt real-time data logging naar Firebase.

## ✨ Functies

- **Dual-zone monitoring**:
  - 2x DHT22 sensoren voor temperatuur en luchtvochtigheid
  - 2x DS18B20 sensoren voor nauwkeurige temperatuurmeting
  - Gescheiden controle voor linker en rechter zone

- **Intelligente temperatuurregeling**:
  - Automatische verwarming per zone
  - RGB LED statusIndicatie
  - 3 verschillende modi voor verschillende scenario's

- **Real-time monitoring**:
  - 20x4 I2C LCD display
  - Firebase integratie voor data logging
  - Minuutlijkse data-uploads

- **Gebruikersinterface**:
  - Modusschakelaar via drukknop
  - LCD weergave van alle sensorwaarden
  - LED kleurcodering voor temperatuurstatus

## 🛠️ Hardware Benodigdheden

- ESP8266 ontwikkelbord (bijv. NodeMCU, Wemos D1 Mini)
- 2x DHT22 temperatuur- en luchtvochtigheidssensor
- 2x DS18B20 temperatuursensor
- 20x4 I2C LCD display
- 2x Relais module
- 2x RGB LED
- Drukknop
- 4.7kΩ pull-up weerstanden voor DS18B20
- Breadboard en jumper draden

## 📊 Pinout Configuratie

```
ESP8266 Pinout:
- D3: DHT22 Links
- D4: DHT22 Rechts
- D5: DS18B20 Links
- D6: DS18B20 Rechts
- D7: Relais Links
- D8: Relais Rechts
- D9-D11: RGB LED 1
- D12-D14: RGB LED 2
- D0: Mode knop
```

## 🔧 Installatie

1. **Hardware Setup**:
   - Sluit alle componenten aan volgens het pinout schema
   - Zorg voor correcte pull-up weerstanden bij de DS18B20 sensoren

2. **Software Vereisten**:
   - Arduino IDE
   - ESP8266 board package
   - Benodigde bibliotheken:
     - Wire
     - LiquidCrystal_I2C
     - DHT
     - OneWire
     - DallasTemperature
     - ESP8266WiFi
     - Firebase_ESP_Client
     - NTPClient
     - WiFiUdp

3. **Firebase Setup**:
   - Maak een Firebase project aan
   - Configureer Realtime Database
   - Kopieer de API key en Database URL

4. **Configuratie**:
   - Vul WiFi credentials in
   - Vul Firebase credentials in
   - Pas indien nodig de temperatuurwaarden aan voor uw specifieke terrarium

## 🌡️ Gebruiksmodi

1. **Mode 1 (Standaard)**:
   - Links: 24-27°C
   - Rechts: 30-32°C
   - Ideale luchtvochtigheid: 50-60%

2. **Mode 2 (Koeler)**:
   - Links: 22-24°C
   - Rechts: 27-30°C
   - Ideale luchtvochtigheid: 50-60%

3. **Mode 3 (Vervelling)**:
   - Links: 24-27°C
   - Rechts: 30-32°C
   - Verhoogde luchtvochtigheid: 70-80%

## 📱 Firebase Integratie

De controller uploadt elke minuut de volgende gegevens naar Firebase:
- Timestamp
- DHT22 temperatuurmetingen (L/R)
- DS18B20 temperatuurmetingen (L/R)
- Luchtvochtigheidsniveaus (L/R)
- Actieve modus

## 🔍 Probleemoplossing

- **LCD toont geen data**: Controleer I2C adres en aansluitingen
- **Sensor leest niet**: Controleer pull-up weerstanden en bedrading
- **WiFi verbindt niet**: Controleer credentials en signaalsterkte
- **Firebase upload faalt**: Controleer internetverbinding en Firebase configuratie

## 🔄 Updates

- v1.0.0: Initiële release
- v1.0.1: Firebase integratie toegevoegd
- v1.0.2: Upload interval aangepast naar 1 minuut

## 📄 Licentie

Dit project is gelicenseerd onder de MIT License - zie het LICENSE bestand voor details.

## ✍️ Auteur

[Uw Naam] - Initiële werk - [GitHub Profile]

## 🤝 Bijdragen

Bijdragen zijn welkom! Open een issue of pull request voor suggesties en verbeteringen.