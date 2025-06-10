# Arduino IR Remote Car Control 🚗🔧

This project allows controlling a two-motor car using an IR remote with an Arduino Uno. It uses the **L298N motor driver** and receives commands through an IR receiver to adjust speed and direction.

## Project Overview

This project is designed to control the movement of a DC motor-powered car using an infrared remote. The speed and direction can be controlled remotely with simple button presses.

### Circuit Design & Simulation

The following image shows the breadboard setup for the project. It includes connections for the Arduino, IR receiver, motor driver, and DC motors.

![Arduino IR Car Breadboard](https://github.com/Aliza-f4/Arduino_IR_Remote/raw/main/Screenshot%202025-06-10-220440.png)

You can also find the Fritzing simulation file in the repository, which is used for circuit assembly and testing.

> **Note:** To visualize the complete setup, open the `pj1.fzz` file in Fritzing.

---

## Hardware Requirements

- **1 x Arduino Uno** (or similar ATmega328P-based board)
- **1 x L298N Dual H-Bridge Motor Driver**
- **1 x IR Receiver (KY-022 or compatible)**
- **2 x DC Motors (6-12V)**
- **1 x 7-12V Power Supply** for the motors
- **IR Remote** (any NEC-compatible remote)

---

## Pin Configuration

| **Arduino Pin** | **L298N Pin** | **Description**        |
|-----------------|---------------|------------------------|
| D6              | ENA           | PWM for motor A speed  |
| D5              | IN1           | Motor A forward        |
| D4              | IN2           | Motor A backward       |
| —               | 12V & GND     | Motor power supply     |

| **Arduino Pin** | **IR Receiver Pin** |
|-----------------|---------------------|
| D7              | OUT                 |
| 5V              | VCC                 |
| GND             | GND                 |

---

## Installation & Setup

1. Install the **IRremote** library using the Arduino Library Manager.
2. Open the `Arduino_IR_Remote.ino` file in the Arduino IDE.
3. Update the IR key values for your remote using the `IRrecvDump` tool if necessary. For example, replace the key definitions as follows:

```cpp
#define KEY_2  0xFF18E7  // Forward
#define KEY_8  0xFF42BD  // Backward
#define KEY_5  0xFF38C7  // Stop
#define KEY_4  0xFF10EF  // Speed decrease
#define KEY_6  0xFF5AA5  // Speed increase
