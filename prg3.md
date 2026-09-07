### Experiment 3: Ultrasonic Distance Measurement

**Aim:**  
To measure object distance using an HC-SR04 ultrasonic sensor.

**Components:**  
Arduino UNO, HC-SR04, breadboard, wires, USB cable.

**Connections:**  
VCC → 5V, GND → GND, Trig → 9, Echo → 10.

**Theory:**  
The sensor sends ultrasonic waves and measures the echo time. Distance is calculated as:  
**Distance = (Time × 0.034) / 2**

**Code:**

```cpp
int t=9,e=10;
void setup(){
 pinMode(t,OUTPUT); pinMode(e,INPUT);
 Serial.begin(9600);
}
void loop(){
 digitalWrite(t,LOW); delayMicroseconds(2);
 digitalWrite(t,HIGH); delayMicroseconds(10);
 digitalWrite(t,LOW);
 long x=pulseIn(e,HIGH);
 Serial.println(x*.034/2);
 delay(200);
}
```

**Procedure:**  
Connect the sensor, upload the code, open Serial Monitor at 9600 baud, and place objects at different distances.

**Observation:**  
Distance changes on the Serial Monitor as the object moves.

**Result:**  
Distance was successfully measured using the HC-SR04 sensor.