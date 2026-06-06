# Smart Parking Simulator

A Digital Logic Design based Smart Parking System using:

- Arduino Nano
- 7404 NOT Gate IC
- 7408 AND Gate IC
- HW-201 IR Sensors
- HC-SR04 Ultrasonic Sensor
- SG90 Servo Motor

---

# Project Overview

This project automates parking slot monitoring and entry barrier control using hardware logic ICs and embedded systems.

The system:
- Detects parking occupancy
- Determines if parking is FULL using hardware logic
- Detects vehicles at the gate
- Opens the barrier automatically
- Activates a buzzer when parking is full

---

# Components Used

- Arduino Nano
- 4 × HW-201 IR Sensors
- HC-SR04 Ultrasonic Sensor
- 7404 Hex NOT Gate IC
- 7408 Quad AND Gate IC
- SG90 Servo Motor
- 5V Active Buzzer
- Breadboard
- Jumper Wires

---

# Hardware Logic

## FULL Parking Logic

FULL = S1' · S2' · S3' · S4'

Where:
- S1' = inverted Slot 1 signal
- S2' = inverted Slot 2 signal
- S3' = inverted Slot 3 signal
- S4' = inverted Slot 4 signal

The 7404 IC performs inversion.

The 7408 IC performs AND operations.

---

# Entry Gate Logic

OPEN = CAR · NOT(FULL)

Meaning:
- Gate opens only when:
  - car is detected
  - and parking is NOT full

---

# System Working

1. IR sensors monitor parking slots.
2. Arduino forwards raw signals to 7404.
3. 7404 inverts the signals.
4. 7408 computes FULL parking condition.
5. Ultrasonic sensor detects a vehicle at the gate.
6. Servo motor opens barrier if parking is available.
7. Buzzer activates when parking is full and a car arrives.

---

# Pin Connections

## IR Sensors

| Sensor | Arduino Pin |
|---|---|
| Slot 1 | A0 |
| Slot 2 | A1 |
| Slot 3 | A2 |
| Slot 4 | A3 |

---

## Arduino → 7404

| Arduino Pin | 7404 Pin |
|---|---|
| D2 | Pin 1 |
| D3 | Pin 3 |
| D4 | Pin 5 |
| D5 | Pin 9 |

---

## Ultrasonic Sensor

| HC-SR04 | Arduino |
|---|---|
| TRIG | D8 |
| ECHO | D7 |

---

## Outputs

| Device | Arduino Pin |
|---|---|
| Servo | D9 |
| Buzzer | D10 |

---

## FULL Signal

| From | To |
|---|---|
| 7408 Pin 8 | Arduino D11 |

---

# Project Structure

```text
Smart-Parking-System/
│
├── code/
│   └── smart_parking.ino
│
├── circuit/
│   └── circuit_diagram.png
│
├── report/
│   └── Detailed_Project_Report.docx
│
├── images/
│   └── setup.jpg
│
├── README.md
│
└── LICENSE
```

---

# Applications

- Smart parking systems
- University parking management
- Shopping mall parking
- Automated entry systems
- Smart city projects

---

# Future Improvements

- IoT monitoring
- Mobile application
- LCD display
- Online slot reservation
- Cloud integration

---


