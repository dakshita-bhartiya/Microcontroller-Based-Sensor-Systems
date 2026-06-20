# PIR-Based Motion Detection and Alert System

## Overview

This project implements a motion detection and alert system using a PIR (Passive Infrared) Sensor, Arduino Uno, LED, and Buzzer. The PIR sensor continuously monitors its surroundings for movement. When motion is detected, the Arduino activates both the LED and buzzer to provide visual and audible alerts.

The project demonstrates digital sensor interfacing, motion sensing, event-driven programming, and real-time alert generation in embedded systems.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| PIR Motion Sensor Module (HC-SR501) | Human motion detection sensor |
| LED | Visual alert indicator |
| Active Buzzer | Audible alert device |
| Breadboard | Prototyping platform |
| Jumper Wires | Electrical connections |

---

## Software Requirements

- Arduino IDE
- Arduino Uno Board Package

---

## Circuit Connections

| Device | Arduino Pin |
|----------|----------|
| PIR Sensor OUT | D10 |
| PIR Sensor VCC | 5V |
| PIR Sensor GND | GND |
| LED Anode (+) | D3 |
| LED Cathode (-) | GND |
| Active Buzzer (+) | D5 |
| Active Buzzer (-) | GND |

---

## Arduino Code

```cpp
void setup()
{
  pinMode(3, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(10, INPUT);
  Serial.begin(9600);
}

void loop()
{
  int x = digitalRead(10);
  Serial.println(x);

  if(x == 1)
  {
    digitalWrite(3, HIGH);
    digitalWrite(5, HIGH);
  }
  else
  {
    digitalWrite(3, LOW);
    digitalWrite(5, LOW);
  }
}
```

---

## Working Principle

The PIR sensor detects changes in infrared radiation caused by the movement of humans or animals within its detection range. When motion is detected, the sensor outputs a HIGH signal.

The Arduino reads this signal through digital pin D10 and activates both the LED and buzzer. When no motion is detected, both indicators remain OFF.

---

## Procedure

### Step 1
Connect the PIR sensor, LED, and buzzer to Arduino Uno according to the circuit connections.

### Step 2
Upload the Arduino sketch using Arduino IDE.

### Step 3
Power the Arduino Uno board.

### Step 4
Allow the PIR sensor to stabilize for a few seconds after power-up.

### Step 5
Move within the sensor's detection range.

### Step 6
Observe the LED and buzzer activation when motion is detected.

### Step 7
Monitor the sensor output through the Serial Monitor.

---

## Output

### No Motion Detected

- LED OFF
- Buzzer OFF
- Serial Monitor displays LOW state

### Motion Detected

- LED ON
- Buzzer ON
- Serial Monitor displays HIGH state

---

## Demonstration

🎥 [Watch Demo Video](./pirwithledandbuzzer.mp4)

---

## Applications

- Intruder Detection Systems
- Smart Home Automation
- Security Alarm Systems
- Occupancy Detection
- Automatic Lighting Systems
- Motion-Based Monitoring Solutions

---

## Skills Demonstrated

- PIR Sensor Interfacing
- Digital Input Processing
- Arduino Programming
- Event-Driven System Design
- Real-Time Motion Detection
- Alert System Development
- Embedded System Prototyping
