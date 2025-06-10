# Arduino IR Remote DC Motor Controller 🚀  
[![Arduino](https://img.shields.io/badge/Arduino-Uno-00979D?logo=arduino)](https://www.arduino.cc/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<img src="Screenshot%202025-06-10%20220440.png" alt="Circuit Diagram" width="500">

## Project Overview
This project controls a DC motor using an IR remote with Arduino Uno. Key features:
- 🎛️ Speed control (0-255 PWM range)
- 🔄 Direction control (forward/reverse)
- ⏹️ Emergency stop function
- 📶 Real-time serial monitoring

## Components
| Component | Quantity | Notes |
|-----------|----------|-------|
| Arduino Uno | 1 | ATmega328P-based |
| L298N Motor Driver | 1 | With screw terminals |
| 3-12V DC Motor | 1 | Standard brushed motor |
| IR Receiver (VS1838B) | 1 | 3-pin (VCC, GND, OUT) |
| IR Remote | 1 | Any NEC-compatible (TV/DVD) |
| LM2596 Buck Converter | 1 | For voltage regulation |
| 3.7V LiPo Battery | 1 | 1100mAh or higher |
| Breadboard/Jumper Wires | - | For connections |

## Circuit Connections
| Arduino Pin | L298N Pin | IR Receiver | Function |
|-------------|-----------|-------------|----------|
| D6          | ENA       |             | Motor A PWM |
| D5          | IN1       |             | Motor A Forward |
| D4          | IN2       |             | Motor A Reverse |
| D7          | -         | OUT         | IR Signal |
| 5V          | -         | VCC         | IR Power |
| GND         | GND       | GND         | Common Ground |

**Power Setup:**  
- Arduino powered via USB  
- L298N powered by LiPo battery (regulated to 7V via LM2596)  
- **Important:** L298N 12V input NOT connected to Arduino
