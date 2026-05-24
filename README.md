# SCOUT
S.C.O.U.T. is a smart, autonomous 4WD obstacle-avoidance robot. Powered by an Arduino Uno and an L298N motor driver, it utilizes ultrasonic echolocation and 180-degree servo scanning to dynamically map and evade barriers in real-time.

**Spatial Calculation & Obstacle Understanding Terrain-vehicle**

![Arduino](https://img.shields.io/badge/-Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> An Arduino-based 4WD autonomous rover featuring dynamic spatial scanning. S.C.O.U.T. utilizes a servo-mounted ultrasonic sensor and a "Sense-Plan-Act" algorithm to detect obstacles, compare directional clearances, and navigate complex environments without human intervention.

---

##  Key Features

* **Dynamic Servo Scanning:** Unlike standard robots with "tunnel vision," S.C.O.U.T. stops and physically sweeps its sensor 180 degrees (Left, Center, Right) to calculate the best escape route.
* **Acoustic Echolocation:** Uses high-frequency sound waves (HC-SR04) instead of standard Infrared (IR) sensors, making the robot completely immune to sunlight blindness and optical interference.
* **Sense-Plan-Act Architecture:** Mathematical comparison of spatial variables (`leftDist > rightDist`) to execute precise zero-point turns.
* **High-Torque 4WD:** Driven by an L298N motor controller and powered by high-discharge 18650 lithium-ion cells for robust terrain traversal.

---

##  Hardware Bill of Materials (BOM)

| Component | Quantity | Role in System |
| :--- | :---: | :--- |
| **Arduino Uno R3** | 1 | The main microcontroller ("Brain"). |
| **L298N Motor Driver** | 1 | Dual H-Bridge for controlling 4 DC motors via PWM. |
| **HC-SR04 Sensor** | 1 | Ultrasonic distance measurement. |
| **SG90 Micro Servo** | 1 | Actuator for the 180° sensor sweep. |
| **DC Gear Motors & Wheels**| 4 | Locomotion (wired in parallel for Left/Right drive). |
| **18650 Battery Pack (7.4V)**| 1 | High-current power supply for motors. |

---

##  Pin Mapping & Wiring Guide

### Arduino Logic Connections
* **Ultrasonic Sensor:** `TRIG` -> `A0` | `ECHO` -> `A1`
* **Servo Motor:** `Signal` -> `Pin 9`
* **L298N (Left Motors):** `ENA` -> `Pin 5` | `IN1` -> `Pin 6` | `IN2` -> `Pin 4`
* **L298N (Right Motors):** `ENB` -> `Pin 3` | `IN3` -> `Pin 8` | `IN4` -> `Pin 7`

> **⚠️ Important Note on Power:** The L298N is powered directly by the 12V terminal from the 18650 batteries. The Arduino is powered via the 5V output terminal of the L298N. **The GND of the battery, L298N, and Arduino MUST be connected together.**

---

##  Installation & Usage

1. Clone this repository to your local machine:
   ```bash
   git clone [https://github.com/Aleena-fatima2025/SCOUT.git](https://github.com/Aleena-fatima2025/SCOUT.git)
