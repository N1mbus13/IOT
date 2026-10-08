### Aim

To read temperature using a TMP36 sensor and switch ON an LED/Fan above 30°C in Tinkercad.

  

### Connections

- **TMP36:** Left → `5V`, Middle → `A0`, Right → `GND`
    
      
    
- **LED:** Anode → `D8`, Cathode → `GND` (via 220 Ω resistor)
    
      
    

### Procedure

1. Wire the TMP36 and LED to the Arduino as listed.
    
      
    
2. Paste the C++ code into the Tinkercad **Code** panel (Text mode).
    
      
    
3. Click **Start Simulation**.
    
      
    
4. Adjust the TMP36 slider to verify: LED is **OFF** below 30°C and turns **ON** at or above 30°C.
    
      
    

### Code

C++

```
const int sensorPin = A0;
const int outputPin = 8;

void setup() {
  pinMode(outputPin, OUTPUT);
}

void loop() {
  float voltage = analogRead(sensorPin) * (5.0 / 1024.0);
  float tempC = (voltage - 0.5) * 100.0;

  if (tempC >= 30.0) {
    digitalWrite(outputPin, HIGH);
  } else {
    digitalWrite(outputPin, LOW);
  }
  delay(500);
}
```

### Result

The LED successfully turns **ON** when the sensor temperature reaches or exceeds 30°C and turns **OFF** when it drops below 30°C.