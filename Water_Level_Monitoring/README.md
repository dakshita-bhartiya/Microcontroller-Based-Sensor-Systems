# Water Level Monitoring System with I2C LCD Display

## Overview

This project implements a real-time water level monitoring system using a Water Level Sensor, I2C LCD Display, and Arduino Uno. The sensor continuously measures the water level and displays the corresponding percentage value on a 16x2 I2C LCD screen.

The project demonstrates analog sensor interfacing, analog-to-digital conversion (ADC), data mapping, and real-time display of sensor data using I2C communication.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| Water Level Sensor | Analog water level sensing module |
| 16x2 I2C LCD Display | Real-time data display module |
| Breadboard | Prototyping platform |
| Jumper Wires | Electrical connections |

---

## Software Requirements

- Arduino IDE
- Arduino Uno Board Package
- LiquidCrystal_I2C Library

---

## Circuit Connections

| Device | Arduino Pin |
|----------|----------|
| Water Level Sensor Signal Pin | A0 |
| Water Level Sensor VCC | 5V |
| Water Level Sensor GND | GND |
| I2C LCD SDA | A4 |
| I2C LCD SCL | A5 |
| I2C LCD VCC | 5V |
| I2C LCD GND | GND |

---

## Arduino Code

```cpp
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x3f, 16, 2);

void setup()
{
  lcd.init();
  lcd.backlight();

  pinMode(A0, INPUT);
  Serial.begin(9600);
}

void loop()
{
  int x = analogRead(A0);

  int s = map(x, 0, 1023, 100, 0);

  lcd.setCursor(3, 1);
  lcd.print(s);
  lcd.print("%");

  Serial.println(x);
}
```

---

## Working Principle

The water level sensor generates an analog voltage proportional to the amount of water in contact with its sensing tracks. The Arduino reads this analog value through pin A0 and converts it into a percentage value using the map() function.

The calculated water level percentage is displayed on the 16x2 I2C LCD screen in real time.

---

## Procedure

### Step 1
Connect the water level sensor and I2C LCD module to Arduino Uno according to the circuit connections.

### Step 2
Install the LiquidCrystal_I2C library in Arduino IDE if not already installed.

### Step 3
Upload the Arduino sketch to the Arduino Uno.

### Step 4
Power the circuit.

### Step 5
Place the water level sensor in water.

### Step 6
Observe the water level percentage displayed on the LCD screen.

### Step 7
Monitor the sensor readings through the Serial Monitor if required.

---

## Output

### Low Water Level

- Lower percentage displayed on LCD
- Lower analog sensor reading

### High Water Level

- Higher percentage displayed on LCD
- Higher analog sensor reading

---

## Demonstration

🎥 [Watch Demo Video](./lcdwithwatersensor.mp4)

---

## Applications

- Water Tank Monitoring
- Smart Irrigation Systems
- Industrial Liquid Level Monitoring
- Reservoir Monitoring
- Home Automation Systems
- Water Management Solutions

---

## Skills Demonstrated

- Analog Sensor Interfacing
- ADC (Analog-to-Digital Conversion)
- I2C Communication
- LCD Interfacing
- Arduino Programming
- Real-Time Data Monitoring
- Embedded System Development
