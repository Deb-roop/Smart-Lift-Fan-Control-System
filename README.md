# 🚀 Smart Lift Fan Control System (Arduino Project)

This project implements a **Smart Lift Fan Control System** using an Arduino Uno. It intelligently controls a **DC fan** based on **temperature** and **motion detection**, displaying relevant information on a **16x2 LCD**. The system is built using basic components and logic, suitable for automation in lift (elevator) environments.

---

## 🎯 Objective

- Automatically turn **fan ON/OFF** based on temperature and human presence
- Show **real-time temperature** and **fan status** on an LCD
- Provide a **3-minute delay timer** to keep the fan running briefly after detecting a person

---

## 🧰 Components Used

| Label | Quantity | Component                      |
|-------|----------|--------------------------------|
| U1    | 1        | Arduino Uno R3                 |
| U4    | 1        | LCD 16x2                       |
| R1    | 1        | 1 kΩ Resistor (for contrast)   |
| U2    | 1        | TMP36 Temperature Sensor       |
| PIR1  | 1        | PIR Motion Sensor              |
| U3    | 1        | H-Bridge Motor Driver (L298N)  |
| M1/M2 | 2        | DC Motors (Fan simulation)     |
| P1    | 1        | 4.4V, 0.2A Power Supply         |

---

## 📌 Pin Configuration

| Arduino Pin | Connected To             | Function                     |
|-------------|--------------------------|------------------------------|
| A0          | TMP36 (U2)               | Reads temperature            |
| A1          | PIR Sensor (PIR1)        | Detects motion               |
| 2           | Motor Driver IN1 (U3)    | Motor direction control      |
| 3           | Motor Driver IN2 (U3)    | Motor direction control      |
| 6           | Motor Driver EN (U3)     | Enables motor (fan)          |
| 8–13        | LCD RS, EN, D4–D7        | LCD display control          |

---

## 🔄 Fan Control Logic

| Condition                         | Fan Status |
|----------------------------------|------------|
| Temperature < 20°C               | OFF        |
| Temperature > 30°C               | ON         |
| 20°C ≤ Temp ≤ 30°C + Motion      | ON (3 mins)|
| No motion in mid temp range      | OFF        |

---

## 📟 LCD Output

Displays real-time information:
```
Fan Status: ON / OFF
Temp: XX°C
```

---

## 💡 How It Works

1. The **TMP36 sensor** reads ambient lift temperature.
2. The **PIR sensor** checks for human presence.
3. Based on logic:
   - If **temperature > 30°C**, the fan stays **ON**
   - If **temperature < 20°C**, the fan stays **OFF**
   - If in **20–30°C range**, the fan runs for 3 minutes **only** if motion is detected
4. The **LCD** displays live status of the fan and temperature
5. The **H-Bridge Motor Driver** controls the DC motor acting as the fan

---

## 🧪 Simulation and Testing

This project can be simulated using [Tinkercad Circuits](https://www.tinkercad.com/) or implemented on real hardware.

Make sure your power supply is sufficient for the DC motor, and include a **flyback diode** across the motor terminals if not using a motor driver with built-in protection.

---

## 📁 Project Structure

- `smart_lift_fan.ino` — Arduino source code
- `README.md` — Project description and 'Smart-Lift-Control_(Final).pptx' documentation
-  `circuit_diagram.png` — Wiring layout

---

## 📸 Circuit Diagram

<img width="1182" height="680" alt="Screenshot 2025-07-16 130006" src="https://github.com/user-attachments/assets/7daa8fbd-3a65-499a-9b8c-f510fa1b6b7f" />


---

## ✅ License

This project is licensed under the **MIT License**.  
Feel free to use, modify, and share it for educational or personal use.

---

Built with ❤️ using Arduino and simple sensors for smarter, energy-efficient automation.
