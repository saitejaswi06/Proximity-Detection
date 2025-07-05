# 📏 Proximity Detection using Ultrasonic Sensor & Arduino Uno

> A real-time proximity sensing system using an **HC-SR04 ultrasonic sensor**, interfaced with an **Arduino Uno**, capable of measuring distances and triggering visual/audio indicators for nearby obstacles.

---

## 🎯 Objective

Design and implement a system to detect nearby objects using ultrasonic sensing and measure their distance. Trigger LEDs and/or buzzers based on the detected proximity to simulate obstacle detection in automation and robotics.

---

## ⚙️ Technologies Used

| Category               | Tools & Components               |
|------------------------|----------------------------------|
| Microcontroller         | Arduino Uno                      |
| Sensor                  | HC-SR04 Ultrasonic Sensor        |
| Programming             | Arduino IDE (Embedded C++)       |
| Output                  | Serial Monitor, LED, Buzzer      |
| Simulation (optional)   | Proteus, TinkerCAD, Wokwi        |

---

## 🔩 Hardware Components

| Component               | Purpose                             |
|-------------------------|-------------------------------------|
| Arduino Uno              | Core microcontroller board         |
| HC-SR04                  | Distance measurement sensor       |
| Red/Yellow/Green LEDs    | Proximity indicators               |
| Buzzer (optional)        | Alert for very close objects       |
| Resistors (220Ω - 1kΩ)   | Current limiting for LEDs          |
| Breadboard + Jumper Wires| Circuit prototyping               |
| Power Supply             | 5V from USB or external battery   |

---

## ⚙️ Working Principle

The **HC-SR04** sensor emits an ultrasonic pulse from the **TRIG** pin and listens for the echo reflected back to the **ECHO** pin. The time difference between transmission and reception is used to calculate distance:

distance (cm) = (pulse duration in microseconds) × (0.034 cm/µs) ÷ 2
---

## 🛠️ Implementation Steps

### Sensor-Controller Wiring:
| HC-SR04 Pin | Arduino Pin |
|-------------|-------------|
| VCC         | 5V          |
| GND         | GND         |
| TRIG        | Pin 9       |
| ECHO        | Pin 10      |

### LED Indicator Example:
| Condition           | Action               |
|---------------------|----------------------|
| > 30 cm             | No indicator         |
| 15 – 30 cm          | Yellow LED ON        |
| < 15 cm             | Red LED ON, buzzer ON|

---

## 🔬 Software Workflow

1. Initialize sensor and output pins.
2. Trigger a 10 µs pulse on the **TRIG** pin.
3. Use `pulseIn()` to measure echo pulse duration on the **ECHO** pin.
4. Calculate distance from pulse duration.
5. Output the distance to the Serial Monitor.
6. Activate LEDs or buzzer based on proximity thresholds.

## ✅ Features

- Accurate real-time distance measurement (~±0.5 cm error).
- Configurable distance thresholds.
- Compact and beginner-friendly design.
- Visual (**LED**) and audio (**buzzer**) feedback.

---

## 🔧 Future Improvements

- Add an **LCD/OLED display** for real-time distance readouts.
- Use wireless modules (**Bluetooth / Wi-Fi**) to transmit distance data.
- Expand to **multi-sensor obstacle detection** for autonomous robots.
- Implement **noise filtering** (e.g., moving average) for stable readings.

---

## 🛡️ Summary

This project is an introductory embedded system demonstrating **ultrasonic sensing**, **digital I/O control**, and **basic automation concepts**.  
It serves as a foundational project for **collision avoidance** and **proximity warning systems** in robotics and IoT applications.
