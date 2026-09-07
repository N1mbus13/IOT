### Experiment 2: IR Sensor with LED

**Aim:**  
To detect an object using an IR sensor and automatically control an LED.

**Components:**  
Arduino UNO, IR sensor, LED, 220Ω resistor, breadboard, wires, USB cable.

**Connections:**

- IR VCC → 5V
    
- IR GND → GND
    
- IR OUT → Pin 2
    
- LED → Pin 13 → 220Ω resistor → GND
    

**Theory:**  
An IR sensor detects objects by transmitting and receiving infrared light. The Arduino reads the sensor output using `digitalRead()`. When an object is detected, the LED turns ON; otherwise, it remains OFF.

**Code:**

```cpp
int ir = 2, led = 13;

void setup() {
  pinMode(ir, INPUT);
  pinMode(led, OUTPUT);
}

void loop() {
  if (digitalRead(ir))
    digitalWrite(led, HIGH);
  else
    digitalWrite(led, LOW);
}
```

**Procedure:**

1. Connect the IR sensor and LED as specified.
    
2. Connect Arduino to the computer.
    
3. Upload the program.
    
4. Place an object in front of the IR sensor.
    
5. Observe the LED turn ON.
    
6. Remove the object and observe the LED turn OFF.
    

**Observation:**  
LED turns ON when an object is detected and OFF when no object is present.

**Result:**  
The IR sensor successfully detects objects and automatically controls the LED.