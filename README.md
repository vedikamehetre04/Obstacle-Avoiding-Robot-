# 🤖 Obstacle-Avoiding Line Follower Robot

> An Arduino-based robot that follows a line, detects obstacles, avoids them, and returns to the original path.

![Platform](https://img.shields.io/badge/platform-Arduino%20Uno-teal) ![Sensor](https://img.shields.io/badge/sensor-HC--SR04%20%7C%20IR-orange) ![Status](https://img.shields.io/badge/status-active-brightgreen)

---

## 📖 Overview

This robot uses **infrared sensors** for line tracking and an **ultrasonic sensor (HC-SR04)** mounted on a **servo motor** to detect and avoid obstacles. When an obstacle is found on the path, the robot calculates the safest direction to go around it and returns to the line automatically.

> ⚠️ **Note:** Tune all `delay()` values in the code to match your battery voltage and sensor quality — these directly affect turning accuracy and movement timing.

---

## 🔧 Hardware Requirements

| Qty | Component |
|---|---|
| x1 | Arduino Uno |
| x2 | Infrared Sensor *(x3–x5 for better line tracking accuracy)* |
| x1 | Ultrasonic Sensor HC-SR04 |
| x1 | Servo Motor SG90 *(for scanning safest path — optional)* |
| x1 | Motor Driver L298N |
| x2 | DC Motor 12V |
| x2 | Wheel |
| x1 | Chassis *(or DIY)* |
| x1 | Sensor Shield v5.0 *(optional — for cleaner cable management)* |
| x1 | 9V Battery / 2x 18650 2000mAh / 4x AA 1.5V Duracell |
| x1 | Battery clip / box with switch |
| x1 | Switch *(if battery box has no switch)* |
| ~20–30 | Male-Male Jumper Wires |
| ~20–30 | Male-Female Jumper Wires |

> 🔩 **Line Follower Only:** Remove the ultrasonic sensor and servo — all other components remain the same.

---

## 📂 Repository Contents

```
obstacle-avoiding-robot/
├── src/
│   └── robot.ino          # Main Arduino sketch
├── libraries/             # Required libraries
├── circuit_diagram.png    # Wiring schematic
└── README.md
```

---

## 🛠️ Setup

### 1. Wiring
- IR sensors → Arduino digital pins (line tracking)
- HC-SR04 (Trig/Echo) → Arduino digital pins
- SG90 Servo → Arduino PWM pin
- L298N Motor Driver → Arduino digital pins + motors

Refer to `circuit_diagram.png` for the full wiring diagram.

### 2. Libraries
Install via Arduino IDE Library Manager or copy from the `/libraries` folder:
- `Servo.h` *(built-in)*
- `NewPing` *(for HC-SR04)*

### 3. Upload
1. Open `src/robot.ino` in Arduino IDE
2. Select **Arduino Uno** board and correct COM port
3. Upload the sketch

---

## ⚙️ Tuning

Adjust these parameters in `robot.ino` based on your battery and sensors:

```cpp
#define OBSTACLE_DISTANCE   20    // cm — triggers obstacle avoidance
#define TURN_DELAY          300   // ms — tune for accurate 90° turns
#define SERVO_LEFT          45    // degrees — servo scan left
#define SERVO_RIGHT         135   // degrees — servo scan right
```



