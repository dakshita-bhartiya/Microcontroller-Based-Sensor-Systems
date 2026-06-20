# LDR-Based Light Monitoring System

## Overview

This project implements a light monitoring system using an LDR (Light Dependent Resistor) and Arduino Uno. The LDR continuously measures ambient light intensity and allows the system to respond to changes in lighting conditions.

An LED is used as a visual indicator. The LED state changes depending on the amount of light detected by the LDR, demonstrating analog sensor interfacing and threshold-based decision making.

The project demonstrates real-time environmental sensing and analog signal processing in embedded systems.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| LDR (Photoresistor) | Light intensity sensing component |
| LED | Visual status indicator |
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
| LDR Output | A2 |
| LED Anode (+) | D6 |
| LED Cathode (-) | GND |
| LDR VCC | 5V |
| LDR GND | GND |

---

## Arduino Code

```cpp
void setup()
{
  pinMode(A2,INPUT);
  pinMode(6,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  int x = analogRead(A2);
  Serial.println(x);

  if(x > 400)
  {
    digitalWrite(6,HIGH);
  }
  else
  {
    digitalWrite(6,LOW);
  }
}
```

---

## Working Principle

The LDR changes its electrical resistance according to the amount of incident light. The Arduino reads the corresponding analog voltage through pin A2 and compares it against a predefined threshold value.

Based on the measured light intensity, the LED is turned ON or OFF. During testing, exposing the LDR to a mobile flashlight caused the LED to turn OFF, indicating a change in the sensed light level.

---

## Procedure

### Step 1
Connect the LDR sensor and LED to Arduino Uno according to the circuit connections.

### Step 2
Upload the Arduino sketch using Arduino IDE.

### Step 3
Power the Arduino Uno board.

### Step 4
Open the Serial Monitor at 9600 baud rate.

### Step 5
Observe the LED response under normal room lighting.

### Step 6
Shine a flashlight or mobile flash on the LDR sensor.

### Step 7
Observe the change in LED state and sensor readings.

---

## Output

### Normal Lighting Condition

- Analog light value displayed on Serial Monitor
- LED status depends on threshold condition

### Bright Light Detected

- LDR reading changes
- LED state changes according to programmed logic

---

## Demonstration

🎥 [Watch Demo Video](./ldrwithled.mp4)
---

## Applications

- Automatic Lighting Systems
- Smart Street Lighting
- Ambient Light Monitoring
- Energy Management Systems
- Light-Based Automation
- Environmental Sensing

---

## Skills Demonstrated

- Analog Sensor Interfacing
- Arduino Programming
- ADC (Analog-to-Digital Conversion)
- Threshold-Based Control
- Environmental Monitoring
- Embedded System Development
- Real-Time Data Acquisition
