# LCD Sequential Message Display Using Arduino Uno

## Overview

This project demonstrates sequential message display using a 16x2 I2C LCD module and Arduino Uno. Multiple messages are displayed one after another with a fixed time delay between transitions.

The project utilizes the LCD clear function to remove the current message before displaying the next one, creating a simple information presentation system.

This project demonstrates display management, timed message sequencing, and I2C-based LCD communication in embedded systems.

---

## Hardware Components Used

| Component | Description |
|------------|------------|
| Arduino Uno | ATmega328P-based microcontroller board |
| 16x2 I2C LCD Module | Character display module with I2C interface |
| Jumper Wires | Electrical connections |
| Breadboard | Prototyping platform |

---

## Software Requirements

- Arduino IDE
- Arduino Uno Board Package
- LiquidCrystal_I2C Library

---

## Circuit Connections

| Device | Arduino Pin |
|----------|----------|
| LCD SDA | A4 |
| LCD SCL | A5 |
| LCD VCC | 5V |
| LCD GND | GND |

---

## Arduino Code

```cpp
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x3f, 16, 2);

void setup() {
  lcd.init();
  lcd.backlight();

  lcd.print("name of college:-");
  delay(2000);

  lcd.clear();
  lcd.print("CCOEW");
  delay(2000);

  lcd.clear();
  lcd.print("NAME:-");
  delay(2000);

  lcd.clear();
  lcd.print("Dakshita");
  delay(2000);

  lcd.clear();
}

void loop() {

}
```

---

## Working Principle

The Arduino initializes the I2C LCD module and displays a predefined sequence of messages. After each message is displayed for two seconds, the LCD screen is cleared using the `lcd.clear()` function before displaying the next message.

This creates a simple sequential information display system where multiple pieces of information can be presented using a limited display area.

---

## Procedure

### Step 1
Connect the I2C LCD module to Arduino Uno according to the circuit connections.

### Step 2
Install the LiquidCrystal_I2C library in Arduino IDE.

### Step 3
Upload the Arduino sketch to Arduino Uno.

### Step 4
Power the circuit.

### Step 5
Observe the LCD display as messages change automatically every two seconds.

---

## Output Sequence

### Screen 1

```text
name of college:-
```

### Screen 2

```text
CCOEW
```

### Screen 3

```text
NAME:-
```

### Screen 4

```text
Dakshita
```

---

## Demonstration

📷 Project image/video will be added soon.

---

## Applications

- Information Display Systems
- Digital Notice Boards
- User Interface Prototyping
- Educational Embedded Projects
- Automated Information Presentation
- Embedded Display Systems

---

## Skills Demonstrated

- I2C Communication
- LCD Interfacing
- Display Management
- Sequential Message Display
- Embedded System Programming
- Human-Machine Interface (HMI)
- Arduino Programming
