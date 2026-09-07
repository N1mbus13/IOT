### Experiment 1: LED ON/OFF using Serial Input

**Aim:**  
To control an LED using commands received through serial communication.

**Components:**  
Arduino UNO, LED, 220Ω resistor, breadboard, wires, USB cable.

**Connections:**  
LED → Pin 13 → 220Ω resistor → GND.

**Theory:**  
Arduino can receive commands from a computer through Serial communication. `Serial.read()` reads the input. If the input is `1`, the LED turns ON; if it is `0`, the LED turns OFF.

**Code:**

```cpp
int led = 13;

void setup() {
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  if (Serial.available()) {
    char c = Serial.read();
    if (c == '1') digitalWrite(led, HIGH);
    if (c == '0') digitalWrite(led, LOW);
  }
}
```

**Procedure:**

1. Connect the LED to pin 13 through a 220Ω resistor.
    
2. Connect Arduino UNO to the computer.
    
3. Upload the program.
    
4. Open Serial Monitor at **9600 baud**.
    
5. Send `1` to turn ON and `0` to turn OFF.
    

**Observation:**  
LED turns ON when `1` is sent and OFF when `0` is sent.

**Result:**  
The LED was successfully controlled using serial communication.