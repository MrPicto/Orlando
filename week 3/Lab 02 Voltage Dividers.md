# Lab 02 Voltage Dividers

Hook up the circuit in the slides with the light dependent resistor.

### Coding
```
const int Green = 9;
const int Blue = 10;
const int Red = 11;


#define FADESPEED 5

void setup() {
  pinMode(Red, OUTPUT);
  pinMode(Green, OUTPUT);
  pinMode(Blue, OUTPUT);
}

void loop() {
  int r, g, b;

  for (r = 0; r < 256; r++) { 
    analogWrite(Red, r);
    delay(FADESPEED);
  } 
  for (b = 255; b > 0; b--) { 
    analogWrite(Blue, b);
    delay(FADESPEED);
  } 
  for (g = 0; g < 256; g++) { 
    analogWrite(Green, g);
    delay(FADESPEED);
  } 
  for (r = 255; r > 0; r--) { 
    analogWrite(Red, r);
    delay(FADESPEED);
  } 
  for (b = 0; b < 256; b++) { 
    analogWrite(Blue, b);
    delay(FADESPEED);
  } 
  for (g = 255; g > 0; g--) { 
    analogWrite(Green, g);
    delay(FADESPEED);
  } 
}
```
<img width="689" alt="Lab 02 Voltage Dividers" src="https://user-images.githubusercontent.com/92038037/143786648-30055395-3305-4bab-aaff-ac72765af76e.png">


https://user-images.githubusercontent.com/92038037/143786654-d00f0f5a-4b21-4562-863d-22be11fba1b1.mov

