# Arduino Irrigation System

An Arduino-based irrigation system that automatically manages watering based on soil moisture levels.

## Features
- Reads soil moisture using an analog sensor.
- Controls an LED (or a relay for a water pump) to indicate or trigger irrigation.
- Easy to use and modify.

## How It Works
1. The soil moisture is measured using an analog sensor connected to pin `A0`.
2. If the moisture level falls below a set threshold (`400`), the system activates the LED (or water pump) connected to pin `12`.
3. The system logs the moisture levels via Serial Monitor for real-time monitoring.

## Hardware Requirements
- Arduino Uno (or compatible board)
- Soil moisture sensor
- LED (or relay module for controlling water pump)
- Jumper wires
- Breadboard

## Wiring Diagram
![WhatsApp Image 2025-01-28 at 16 33 44_f42c40e2](https://github.com/user-attachments/assets/7016080c-a506-4dfd-b9c3-d280caa437a6)



## Code
The Arduino sketch is provided in `irrigation_system.ino`. Upload the code using the Arduino IDE.

```c
int a1 = 0;

void setup() 
{
  Serial.begin(9600);
  pinMode(12, OUTPUT);
  digitalWrite(12, HIGH);  // Turn the LED on initially
}

void loop() 
{
  a1 = analogRead(A0);
  Serial.println(a1);
  if (a1 < 400) 
  {
    digitalWrite(12, HIGH);  // Turn the LED on
  } 
  else 
  {
    digitalWrite(12, LOW);   // Turn the LED off
  }
  delay(200);
}
