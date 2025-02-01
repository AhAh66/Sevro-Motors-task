# Sevro-Motors-task
#  - Servo Motor Control

## Project Description

This project aims to program **6 servo motors** to execute specific tasks using an **Arduino board**. The project requires running the motors using the **Sweep** example for **2 seconds**, then setting all motors to **90 degrees**.

---

## Requirements

### Hardware:
- **Arduino Uno** board
- **6 Servo Motors**
- External power source (**5V battery or suitable power supply**)
- Jumper wires
- **Breadboard** for connections

### Software:
- **Arduino IDE** for writing and uploading the code



---

## Code Implementation

```cpp
#include <Servo.h>

Servo servo1, servo2, servo3, servo4, servo5, servo6;
const int servoPins[] = {3, 4, 5, 6, 7, 8};

void setup() {
    servo1.attach(servoPins[0]);
    servo2.attach(servoPins[1]);
    servo3.attach(servoPins[2]);
    servo4.attach(servoPins[3]);
    servo5.attach(servoPins[4]);
    servo6.attach(servoPins[5]);
    
    // Set all servos to 90 degrees at startup
    moveAllServos(90);
    delay(1000);
}

void loop() {
    // Run Sweep example for 2 seconds
    for (int angle = 0; angle <= 180; angle += 1) {
        moveAllServos(angle);
        delay(10);
    }
    for (int angle = 180; angle >= 0; angle -= 1) {
        moveAllServos(angle);
        delay(10);
    }
    delay(2000);
    
    // Set all servos to 90 degrees
    moveAllServos(90);
    while (true); // Stop the program after achieving the task
}

void moveAllServos(int angle) {
    servo1.write(angle);
    servo2.write(angle);
    servo3.write(angle);
    servo4.write(angle);
    servo5.write(angle);
    servo6.write(angle);
}
```
Project Link on Wokwi

[View Project on Wokwi](https://wokwi.com/projects/374644935912458241)
---

## Expected Output
1. All servos move from **0° to 180°** and back to **0°** for **2 seconds**.
2. After completion, all servos are set to **90°**.

---


https://github.com/user-attachments/assets/608ce18a-d1f5-43cd-bd99-9d972d4990af




## References
- [Arduino Servo Library](https://www.arduino.cc/en/Reference/Servo)
- [Servo Motor Projects](https://create.arduino.cc/projecthub)

