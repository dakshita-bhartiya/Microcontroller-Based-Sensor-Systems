# Touch Sensor Interface with LED Indicator

## Overview

This project implements a touch-based sensing system using a Touch Sensor Module and Arduino Uno. The touch sensor detects physical contact and sends a digital signal to the Arduino. Upon detecting a touch event, the Arduino activates an LED indicator.

The project demonstrates digital input sensing, human-machine interaction, and event-driven embedded system design.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| Touch Sensor Module (TTP223) | Capacitive touch sensing module |
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
| Touch Sensor OUT | D7 |
| Touch Sensor VCC | 5V |
| Touch Sensor GND | GND |
| LED Anode (+) | D8 |
| LED Cathode (-) | GND |

---

## Arduino Code

```cpp
void setup() {
  pinMode(7, INPUT);
  pinMode(8, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int x = digitalRead(7);
  Serial.println(x);

  if(x == 1)
  {
    digitalWrite(8, HIGH);
    delay(1000);
  }
  else
  {
    digitalWrite(8, LOW);
  }
}
```

---

## Working Principle

The touch sensor continuously monitors for physical contact on its sensing surface. When touched, the sensor generates a HIGH digital signal which is read by the Arduino through digital pin D7.

The Arduino then activates the LED connected to pin D8, providing visual feedback for the touch event. The LED remains ON briefly before returning to its normal state.

---

## Procedure

### Step 1
Connect the touch sensor module and LED to Arduino Uno according to the circuit connections.

### Step 2
Upload the Arduino sketch using Arduino IDE.

### Step 3
Power the Arduino Uno board.

### Step 4
Open the Serial Monitor at 9600 baud rate.

### Step 5
Touch the sensing surface of the touch sensor module.

### Step 6
Observe the LED response and serial monitor output.

---

## Output

### No Touch Detected

- LED OFF
- Sensor output remains LOW

### Touch Detected

- LED ON
- Sensor output becomes HIGH
- Touch event displayed on Serial Monitor

---

## Demonstration
🎥 [Watch Demo Video](https://github.com/dakshita-bhartiya/Microcontroller-Based-Sensor-Systems/blob/main/Touch_Sensor_Interface/touchsensnorwithled.mp4)
---

## Applications

- Touch-Based Control Systems
- Human Machine Interfaces (HMI)
- Smart Home Automation
- Interactive Electronic Devices
- Access Control Systems
- Consumer Electronics

---

## Skills Demonstrated

- Capacitive Touch Sensor Interfacing
- Arduino Programming
- Digital Input Processing
- Human-Machine Interaction
- Embedded System Development
- Real-Time Event Detection
- Hardware-Software Integration
