# Vaccine Temperature Alert System

This project consists of an ESP32 firmware for monitoring temperature and a React Dashboard for real-time visualization.

## Hardware Requirements
- **ESP32 Development Board**
- **GY-SHT31-D** Temperature & Humidity Sensor
- **Active Buzzer**
- Jumper Wires

## Wiring
| SHT31 Pin | ESP32 Pin |
|-----------|-----------|
| VIN       | 3.3V      |
| GND       | GND       |
| SDA       | GPIO 21   |
| SCL       | GPIO 22   |

| Buzzer Pin | ESP32 Pin |
|------------|-----------|
| POS (+)    | GPIO 26   |
| NEG (-)    | GND       |

## Firmware Setup (Arduino IDE)
1. Open `firmware/main.ino` in Arduino IDE.
2. Install the following libraries via Library Manager:
   - `Adafruit SHT31`
   - `Firebase ESP Client` (by Mobizt)
3. Edit `main.ino` with your credentials:
   - WiFi SSID & Password
   - Firebase API Key & URL
   - WhatsApp CallMeBot API Key
4. Upload to ESP32.

## Dashboard Setup
1. Navigate to the `dashboard` folder.
2. Run `npm install` to install dependencies.
3. Edit `src/firebase.ts` and add your Firebase Project configuration.
4. Run `npm run dev` to start the local server.
5. Build for production with `npm run build`.

## Features
- **Real-time Monitoring**: Live temperature and humidity updates.
- **Alerts**:
    - **Local**: Buzzer sounds when temp is outside 2-8°C range.
    - **Remote**: WhatsApp message sent via CallMeBot.
    - **UI**: Dashboard shows visual alarm.
- **Data Logging**: Historical data logged to Firebase Realtime Database.
