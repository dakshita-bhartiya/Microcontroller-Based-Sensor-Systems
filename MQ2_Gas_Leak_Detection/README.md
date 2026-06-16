# MQ-2 Based Gas Leak Detection and Alert System

## Overview

This project implements a gas leak detection and alert system using the MQ-2 gas sensor module and Arduino Uno. The system continuously monitors the environment for combustible gases and smoke. When the gas concentration exceeds the predefined threshold, an LED and buzzer are activated to provide immediate visual and audible alerts.

---

## Hardware Components Used

| Component | Technical Name |
|------------|------------|
| Microcontroller | Arduino Uno (ATmega328P) |
| Gas Sensor Module | MQ-2 Gas Sensor Module |
| Audible Alert Device | Active Buzzer |
| Visual Indicator | LED |
| Current Limiting Resistor | 220Ω Resistor |
| Prototyping Board | Breadboard |
| Connecting Wires | Jumper Wires |

---

## Software Requirements

- Arduino IDE
- Arduino Uno Board Package

---

## Circuit Connections

| Device | Arduino Pin |
|----------|----------|
| MQ-2 DO Pin | D8 |
| LED | D6 |
| Buzzer | D7 |
| MQ-2 VCC | 5V |
| MQ-2 GND | GND |

---

---

## Arduino Code

```cpp
void setup() {
  pinMode(7,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(8,INPUT);
  Serial.begin(9600);
}

void loop() {
  int x = digitalRead(8);
  Serial.println(x);

  if (x == 0)
  {
    digitalWrite(6,HIGH);
    digitalWrite(7,HIGH);
  }
  else
  {
    digitalWrite(6,LOW);
    digitalWrite(7,LOW);
  }
}
```

## Working Principle

The MQ-2 gas sensor continuously monitors the surrounding air. When the gas concentration exceeds the threshold set on the sensor module, the digital output changes state. The Arduino reads this output and activates the LED and buzzer to warn the user of a potential gas leak.

---

## Procedure

### Step 1
Assemble the circuit according to the circuit diagram.

### Step 2
Upload the Arduino sketch using Arduino IDE.

### Step 3
Open the Serial Monitor at 9600 baud rate.

### Step 4
Power the circuit and allow the MQ-2 sensor to stabilize.

### Step 5
Introduce smoke or combustible gas near the sensor.

### Step 6
Observe the activation of the LED and buzzer when gas is detected.

---

## Output

### Normal Condition
- LED OFF
- Buzzer OFF

### Gas Leak Detected
- LED ON
- Buzzer ON

---

## Demonstration




### Working Video


▶ [Watch Project Demo](VideoMQ2demo.mp4)


---

## Applications

- LPG Leakage Detection
- Kitchen Safety Systems
- Industrial Safety Monitoring
- Fire and Smoke Detection
- Smart Home Safety Solutions

---

## Learning Outcomes

- Digital Sensor Interfacing
- Arduino Programming
- Embedded System Development
- Real-Time Event Detection
- Alert and Monitoring Systems
