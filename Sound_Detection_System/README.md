# Sound Detection System

## Overview

This project implements a sound detection system using a Sound Sensor Module and Arduino Uno. The sensor continuously monitors ambient sound levels and detects sudden sound events such as claps, knocks, or loud noises.

When sound is detected, the Arduino activates an LED indicator for a short duration, providing visual feedback of the detected event.

The project demonstrates digital sensor interfacing, event detection, and real-time response using embedded systems.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| Sound Sensor Module (KY-038) | Sound detection sensor |
| LED | Visual alert indicator |
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
| Sound Sensor DO | D5 |
| LED Anode (+) | D6 |
| LED Cathode (-) | GND |
| Sound Sensor VCC | 5V |
| Sound Sensor GND | GND |

---

## Arduino Code

```cpp
void setup() {
  pinMode(6,OUTPUT);
  pinMode(5,INPUT);
  Serial.begin(9600);
}

void loop() {
  int x = digitalRead(5);
  Serial.println(x);

  if(x==1)
  {
    digitalWrite(6,HIGH);
    delay(2000);
  }
  else
  {
    digitalWrite(6,LOW);
  }
}
```

---

## Working Principle

The sound sensor continuously monitors sound intensity in the surrounding environment. When the detected sound exceeds the preset threshold level, the sensor outputs a HIGH signal.

The Arduino reads this signal through digital pin D5 and turns ON the LED connected to pin D6. The LED remains illuminated for two seconds, providing a clear visual indication that a sound event has been detected.

---

## Procedure

### Step 1
Connect the sound sensor module and LED to Arduino Uno according to the circuit connections.

### Step 2
Upload the Arduino sketch using Arduino IDE.

### Step 3
Power the Arduino Uno board.

### Step 4
Open the Serial Monitor at 9600 baud rate.

### Step 5
Generate a sound near the sensor, such as a clap or tap.

### Step 6
Observe the LED response and serial monitor output.

---

## Output

### No Sound Detected

- LED OFF
- Sensor output remains LOW

### Sound Detected

- LED ON for 2 seconds
- Sensor output becomes HIGH

---

## Demonstration

🎥 [Watch Demo Video](./soundsensorvideo.mp4)

---

## Applications

- Noise Monitoring Systems
- Sound Activated Devices
- Security Systems
- Smart Home Automation
- Acoustic Event Detection
- Industrial Monitoring

---

## Skills Demonstrated

- Digital Sensor Interfacing
- Arduino Programming
- Event-Based Detection
- Embedded System Development
- Real-Time Monitoring
- Hardware-Software Integration
