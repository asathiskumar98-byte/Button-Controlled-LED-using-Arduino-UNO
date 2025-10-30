# 🔘 Button Controlled LED using Arduino UNO

A simple digital input-output project where an LED is controlled by a push button.  
When the button is pressed, the LED turns **ON**; when released, it turns **OFF** — the perfect beginner exercise to understand digital logic and I/O pins on Arduino.

---

## 🧠 Overview

This project demonstrates how to:
- Read a **digital input** (button state)
- Control a **digital output** (LED)
- Use **if-else logic** in Arduino programming

---

## ⚙️ Hardware Requirements

- Arduino UNO  
- Push Button  
- LED  
- 220Ω resistor (for LED)  
- 10kΩ pull-down resistor (for button)  
- Breadboard and jumper wires  

---

## 🔌 Circuit Connections

| Component | Arduino Pin | Description |
|------------|--------------|--------------|
| Button | D8 | Input pin to detect press |
| LED | D7 | Output pin to control LED |
| Button GND | GND | Common ground |
| LED GND | GND (via 220Ω resistor) | Current limiting resistor for LED |

🧩 **Logic:**  
- When the button is pressed → Pin 8 reads HIGH → LED ON  
- When the button is released → Pin 8 reads LOW → LED OFF  

---

## 💻 Arduino Code

```cpp
const int button = 8;
const int led = 7;

unsigned char button_state;

void setup()
{
  pinMode(button, INPUT);
  pinMode(led, OUTPUT);
}

void loop()
{
  button_state = digitalRead(button);

  if(button_state == HIGH)
  {
    digitalWrite(led, HIGH);
  }
  else
  {
    digitalWrite(led, LOW);
  }
}
```
🚀 How It Works
The push button sends a digital HIGH signal to pin 8 when pressed.

The Arduino reads this signal using digitalRead().

Based on the input, the LED is turned ON or OFF using digitalWrite().

🧰 Software Tools
Arduino IDE (v2.0 or later)

Arduino UNO Board Drivers

📸 Output Behavior
Button State	LED State
Pressed (HIGH)	ON
Released (LOW)	OFF
