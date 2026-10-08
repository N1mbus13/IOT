### Aim

To simulate an IR sensor–based servo motor control system using Arduino Uno in Tinkercad.

  

### Connections

- **Slide Switch (IR):** One end → `5V`, Middle → `D2`, Other end → `GND`
    
      
    
- **Servo (SG90):** Red → `5V`, Black/Brown → `GND`, Yellow/Orange → `D9`
    
      
    

### Procedure

1. Place Arduino Uno, a slide switch, and a servo motor in Tinkercad and wire them as listed.
    
      
    
2. Paste the C++ code into the **Code** panel (Text mode).
    
      
    
3. Click **Start Simulation**.
    
      
    
4. Slide the switch to test: `HIGH` rotates the servo to **90°**; `LOW` resets it to **0°**.
    
      
    

### Code

C++

```
#include <Servo.h>

const int sensorPin = 2;
const int servoPin = 9;
Servo myServo;

void setup() {
  pinMode(sensorPin, INPUT);
  myServo.attach(servoPin);
  myServo.write(0);
}

void loop() {
  if (digitalRead(sensorPin) == HIGH) {
    myServo.write(90);
  } else {
    myServo.write(0);
  }
  delay(15);
}
```

### Result

The servo motor rotates to **90°** when the switch is ON (object detected) and returns to **0°** when OFF.