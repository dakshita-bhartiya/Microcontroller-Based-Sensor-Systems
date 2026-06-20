# Infrared Flame Detection and Alert System

## Overview

This project implements a flame detection and alert system using the KY-026 Flame Sensor Module and Arduino Uno. The sensor continuously monitors the surrounding environment for the presence of a flame by detecting infrared radiation emitted from fire sources. When a flame is detected, the system activates an LED as a visual alert indicator.

The project demonstrates digital sensor interfacing, event-driven monitoring, and real-time safety detection techniques used in embedded systems.

---

## Hardware Components Used

| Component                  | Description                            |
| -------------------------- | -------------------------------------- |
| Arduino Uno                | ATmega328P-based microcontroller board |
| KY-026 Flame Sensor Module | Infrared flame detection sensor        |
| LED                        | Visual alert indicator                 |
| Breadboard                 | Prototyping platform                   |
| Jumper Wires               | Electrical connections                 |

---

## Software Requirements

* Arduino IDE
* Arduino Uno Board Package

---

## Circuit Connections

| Device                     | Arduino Pin |
| -------------------------- | ----------- |
| KY-026 Digital Output (DO) | D7          |
| LED Anode (+)              | D8          |
| LED Cathode (-)            | GND         |
| KY-026 VCC                 | 5V          |
| KY-026 GND                 | GND         |

---

## Arduino Code

```cpp
void setup() {
  pinMode(7, INPUT);    // Flame Sensor
  pinMode(8, OUTPUT);   // LED
  Serial.begin(9600);
}

void loop() {
  int x = digitalRead(7);
  Serial.println(x);

  if (x == 1)
  {
    digitalWrite(8, HIGH);
  }
  else
  {
    digitalWrite(8, LOW);
  }
}
```

---

## Working Principle

The KY-026 flame sensor continuously monitors infrared radiation emitted by flame sources. When a flame is detected within the sensing range, the sensor's digital output changes state. The Arduino reads this output and activates the LED to provide a visual indication of flame detection.

When no flame is present, the LED remains OFF.

---

## Procedure

### Step 1

Connect the KY-026 flame sensor module and LED according to the circuit connections.

### Step 2

Upload the Arduino sketch using Arduino IDE.

### Step 3

Power the Arduino Uno board.

### Step 4

Open the Serial Monitor at 9600 baud rate.

### Step 5

Bring a flame source such as a lighter or candle near the sensor.

### Step 6

Observe the LED response and serial monitor output.

---

## Output

### No Flame Detected

* LED OFF
* Serial Monitor displays sensor status

### Flame Detected

* LED ON
* Flame detection event indicated

---

## Demonstration
🎥 [Watch Demo Video](flamesensorwithledvideo.mp4)




---

## Applications

* Fire Detection Systems
* Industrial Safety Monitoring
* Flame Presence Detection
* Laboratory Safety Systems
* Early Warning Systems
* Smart Safety Applications

---

## Skills Demonstrated

* Digital Sensor Interfacing
* Arduino Programming
* Embedded System Development
* Event-Driven Detection
* Real-Time Monitoring
* Safety System Prototyping
