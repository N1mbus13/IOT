### Experiment 4: Soil Moisture Sensor

**Aim:**  
To detect soil moisture using a sensor and Arduino in Tinkercad.

**Components:**  
Arduino UNO, soil moisture sensor, connecting wires, Tinkercad.

**Connections:**  
VCC → 5V, GND → GND, AO → A0.

**Theory:**  
The sensor gives an analog value based on soil moisture. Arduino reads it using `analogRead()` and classifies the soil as **DRY, MOIST, or WET**.

**Code:**

```cpp
int m=A0;

void setup(){
 Serial.begin(9600);
}

void loop(){
 int v=analogRead(m);
 Serial.println(v);

 if(v<350) Serial.println("DRY");
 else if(v<700) Serial.println("MOIST");
 else Serial.println("WET");

 delay(1000);
}
```

**Procedure:**  
Connect the sensor in Tinkercad, enter the code, start simulation, and observe the moisture value and condition in Serial Monitor.

**Observation:**  
The displayed soil condition changes according to the moisture level.

**Result:**  
Soil moisture was successfully detected using Arduino and a virtual moisture sensor.