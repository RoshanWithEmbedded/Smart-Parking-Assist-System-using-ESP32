# 🅿️ Smart Parking Assist System using ESP32

[![Platform](https://img.shields.io/badge/platform-ESP32-blue.svg)](https://www.espressif.com/en/products/socs/esp32)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Arduino IDE](https://img.shields.io/badge/Arduino-IDE-00979D.svg)](https://www.arduino.cc/en/software)
[![Hardware](https://img.shields.io/badge/hardware-Ultrasonic%20%2B%20RGB-red.svg)]()

A real-time parking assistance system using ESP32, HC-SR04 ultrasonic sensor, and RGB LED. Provides distance-based visual and audio feedback to help drivers park safely.

## 📋 Table of Contents

- [Features](#-features)
- [Hardware Required](#-hardware-required)
- [Pin Connections](#-pin-connections)
- [Distance Zones](#-distance-zones)

- [Installation](#-installation)
- [Working Principle](#-working-principle)
- [Troubleshooting](#-troubleshooting)
- [Customization](#-customization)
- [Performance Specifications](#-performance-specifications)
- [Applications](#-applications)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)
- [Contact](#-contact)

## ✨ Features

- **Real-time distance measurement** using HC-SR04 ultrasonic sensor (2cm - 400cm range)
- **Single RGB LED indicator** - Clean, professional visual feedback
- **Multi-zone alerts** with different colors for different distances
- **Audible warnings** with variable beep frequency
- **Stable readings** through 5-sample averaging algorithm
- **Instant response** - No WiFi/cloud dependency (<100ms latency)
- **Low power consumption** (~80mA active, can be optimized for battery)
- **Plug & play** - No internet or external services required

## 🛠️ Hardware Required

| Component | Quantity | Purpose | Approx. Cost |
|-----------|----------|---------|---------------|
| ESP32 Development Board | 1 | Main controller | 400 Rs |
| Ultrasonic Sensor (HC-SR04) | 1 | Distance measurement | 250 Rs |
| RGB LED (Common Cathode) | 1 | Visual indicator | 5 Rs |
| 100Ω Resistors | 5 | Current limiting for RGB LED | 2 Rs each |
| Buzzer (5V) | 1 | Audio alert | 50 Rs |
| Breadboard | 1 | Prototyping | 120 Rs |
| Jumper Wires | 10-15 | Connections | 40 Rs |
| USB Cable | 1 | Power & programming | 150 Rs |

**Total Cost:** ~1000 Rs

### Optional Components

- 5V Power supply (2A) for standalone operation
- Enclosure box for permanent installation
- Additional 100Ω resistors (spares)

## 🔌 Pin Connections

### Complete Wiring Table

| Component | Pin/Side | ESP32 GPIO | Resistor | Notes |
|-----------|----------|-----------|----------|-------|
| **HC-SR04** | VCC | 5V | - | Power |
| | GND | GND | - | Ground |
| | TRIG | GPIO 23 | - | Trigger output |
| | ECHO | GPIO 22 | - | Echo input |
| **RGB LED** | Red Anode | GPIO 21 | 100Ω | To GND via resistor |
| | Green Anode | GPIO 19 | 100Ω | To GND via resistor |
| | Blue Anode | GPIO 18 | 100Ω | To GND via resistor |
| | Common Cathode | GND | - | Longest pin |
| **Buzzer** | Positive (+) | GPIO 5 | - | Signal input |
| | Negative (-) | GND | - | Ground |

### ⚠️ Important Notes

- **RGB LED Common Cathode:** Longest pin connects to GND
- **For Common Anode RGB LED:** Connect longest pin to 3.3V and invert logic (HIGH = OFF, LOW = ON)
- **Resistors:** Always use current-limiting resistors with LEDs to prevent damage

## 🚥 Distance Zones

| Distance Range | LED Color | Buzzer Pattern | Action Required |
|----------------|-----------|----------------|-----------------|
| > 30 cm | OFF | Silent | Safe distance, approach freely |
| 20-30 cm | 🟢 GREEN | 1 beep/sec (500ms) | Getting closer, park carefully |
| 10-20 cm | 🔵 BLUE | 2 beeps/sec (250ms) | Warning zone, slow down |
| < 10 cm | 🔴 RED | 5 beeps/sec (100ms) | DANGER! STOP immediately |



🚀 Installation Steps

### Step 1: Install Arduino IDE
Download Arduino IDE from: https://www.arduino.cc/en/software

### Step 2: Install ESP32 Board
1. Go to: **File → Preferences**
2. Add the following URL to "Additional Boards Manager URLs":
   https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

3. Go to: **Tools → Board → Boards Manager**
4. Search for: **ESP32 by Espressif Systems**
5. Click **Install**

### Step 3: Upload Code
1. Select Board → **ESP32 Dev Module**
2. Select the correct **COM Port**
3. Click **Upload**

---

📈 Applications

- Smart car reverse parking
- Obstacle detection system
- Garage wall distance alert
- Robot obstacle sensing
- Industrial safety monitoring

---

🚀 Future Improvements

- OLED display for live distance
- Blynk mobile monitoring
- PWM buzzer tone control
- Automotive reverse parking support
- Voice alert system

---

👨‍💻 Author

**Roshan Chavan**  
Embedded Systems Engineer  
Interested in Embedded Systems, IoT, ARM, RTOS, Linux

🔗 LinkedIn: [[roshan-chavan](https://linkedin.com/in/roshan-chavan)](https://www.linkedin.com/in/roshan-chavan-256835194/)

---

⭐ Support

If you found this project useful, please give it a **Star** ⭐ on GitHub.

---

*Built with ❤️ using ESP32*
