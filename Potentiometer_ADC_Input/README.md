# Potentiometer-Based ADC Level Indicator

## Overview

This project demonstrates Analog-to-Digital Conversion (ADC) using a potentiometer and Arduino Uno. The potentiometer provides a variable analog input to the Arduino, allowing different output levels to be generated based on the knob position.

Four LEDs are used to indicate different ranges of the potentiometer value. As the potentiometer is rotated, additional LEDs turn ON, creating a simple level indicator system.

The project demonstrates analog signal acquisition, ADC processing, threshold-based control, and real-time output indication in embedded systems.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| Potentiometer | Variable analog input device |
| LED (4 Units) | Multi-level output indicators |
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
| Potentiometer Output | A0 |
| LED 1 | D2 |
| LED 2 | D4 |
| LED 3 | D5 |
| LED 4 | D7 |
| Potentiometer VCC | 5V |
| Potentiometer GND | GND |

---

## Arduino Code

```cpp
void setup()
{
  pinMode(A0, INPUT);
  pinMode(2,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(7,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  int x = analogRead(A0);
  Serial.println(x);

  if (x > 0 && x < 200)
  {
    digitalWrite(2, HIGH);
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(7, LOW);
  }
  else if (x > 200 && x < 600)
  {
    digitalWrite(2, HIGH);
    digitalWrite(4, HIGH);
    digitalWrite(5, LOW);
    digitalWrite(7, LOW);
  }
  else if (x > 600 && x < 950)
  {
    digitalWrite(2, HIGH);
    digitalWrite(4, HIGH);
    digitalWrite(5, HIGH);
    digitalWrite(7, LOW);
  }
  else
  {
    digitalWrite(2, HIGH);
    digitalWrite(4, HIGH);
    digitalWrite(5, HIGH);
    digitalWrite(7, HIGH);
  }
}
```

---

## Working Principle

The potentiometer generates a variable analog voltage which is read by the Arduino through analog pin A0. The Arduino converts this analog voltage into a digital value ranging from 0 to 1023 using its built-in ADC.

Depending on the measured value, the Arduino activates different combinations of LEDs to represent increasing input levels.

As the potentiometer knob is rotated, the ADC value changes and additional LEDs illuminate to indicate the current range.

---

## Procedure

### Step 1
Connect the potentiometer and LEDs to Arduino Uno according to the circuit connections.

### Step 2
Upload the Arduino sketch using Arduino IDE.

### Step 3
Power the Arduino Uno board.

### Step 4
Open the Serial Monitor at 9600 baud rate.

### Step 5
Rotate the potentiometer knob slowly.

### Step 6
Observe the ADC values in the Serial Monitor.

### Step 7
Observe the LED level indication corresponding to the potentiometer position.

---

## Output

### Low Input Level

- LED 1 ON

### Medium Input Level

- LED 1 and LED 2 ON

### High Input Level

- LED 1, LED 2, and LED 3 ON

### Maximum Input Level

- All Four LEDs ON

---

## Demonstration

🎥 Demo video will be added soon.

---

## Applications

- ADC Demonstration Systems
- Signal Level Indicators
- Sensor Calibration Systems
- Analog Input Testing
- Embedded Systems Education
- Human-Machine Interface Prototyping

---

## Skills Demonstrated

- Analog Sensor Interfacing
- ADC (Analog-to-Digital Conversion)
- Threshold-Based Control
- Arduino Programming
- Multi-Level Output Indication
- Real-Time Data Monitoring
- Embedded System Development
