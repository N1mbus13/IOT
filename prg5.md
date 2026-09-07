### Experiment 5: Servo Motor

**Aim:**  
To control a servo motor using Arduino in Tinkercad.

**Components:**  
Arduino UNO, SG90 servo motor, connecting wires, Tinkercad.

**Connections:**  
Red → 5V, Brown/Black → GND, Yellow/Orange → Pin 9.

**Theory:**  
A servo motor allows precise angular movement, usually from **0° to 180°**. The Arduino controls its position using the `Servo.h` library and `write()` function.

**Code:**

```cpp
#include <Servo.h>
Servo s;

void setup(){
  s.attach(9);
}

void loop(){
  for(int i=0;i<=180;i+=10){
    s.write(i); delay(100);
  }
  for(int i=180;i>=0;i-=10){
    s.write(i); delay(100);
  }
}
```

**Procedure:**  
Connect the servo, enter the code in Tinkercad, start simulation, and observe it rotate from **0° to 180° and back**.

**Observation:**  
0° → Left, 90° → Center, 180° → Right.

**Result:**  
The servo motor was successfully controlled to rotate to different angles using Arduino.