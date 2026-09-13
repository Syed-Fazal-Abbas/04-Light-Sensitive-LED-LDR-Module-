# 04-Light-Sensitive-LED-LDR-Module-
An Arduino-based Light-Sensitive LED (LDR Module)
# Project 4: Light-Sensitive LED (LDR Module)

## Description
This is my fourth embedded systems project where I used an LDR 
(Light Dependent Resistor) module with Arduino Uno to automatically 
turn an LED ON in the dark and OFF when there's light — similar to 
how automatic streetlights work.

## Hardware Used
- Board: Arduino Uno
- LDR Module (digital output type)
- LED
- Resistor: 220 ohm (for LED)
- Breadboard
- Jumper wires



## How It Works
The LDR module is connected to digital pin 2, and the LED is 
connected to pin 9. The LDR module continuously outputs a digital 
signal based on light conditions. When it gets dark, the LDR sends 
a HIGH signal, which turns the LED ON. When there's enough light, 
it sends LOW, and the LED turns OFF. The sensor readings are also 
printed on the Serial Monitor for testing/debugging.

## Code

```cpp
// Pin Definitions
const int ldrPin = 2; 
const int ledPin = 9;

void setup() { 
  pinMode(ldrPin, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() { 
  int ldrState = digitalRead(ldrPin); 
  Serial.println(ldrState);
  
  if (ldrState == HIGH) { 
    digitalWrite(ledPin, HIGH); 
  } else {
    digitalWrite(ledPin, LOW);
  }

  delay(100); 
}
```

## Demo Video
[https://youtu.be/a2671XZhK1E?si=tKx_UNihbLAuwmll]

## What I Learned
- Working with sensor modules (LDR) as digital inputs
- Using Serial Monitor for debugging and reading live sensor data
- Building an automatic, light-responsive system
- Real-world application: automatic streetlight/night light logic
