# Lab 01 - PWM

use PWM to fade an LED
```
int led1 = 9; 
int led2 = 8; // the PWM pin the LED is attached to
int brightness1 = 0;    // how bright the LED is
int fadeAmount1 = 10; 
int brightness2 = 5;    
int fadeAmount2 = 10;// how many points to fade the LED by

// the setup routine runs once when you press reset:
void setup() {
  // declare pin 9 to be an output:
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // set the brightness of pin 9:
  analogWrite(led1, brightness1);

  // change the brightness for next time through the loop:
  brightness1 = brightness1 + fadeAmount1;

  // reverse the direction of the fading at the ends of the fade:
  if (brightness1 <= 0 || brightness1 >= 255) {
    fadeAmount1 = -fadeAmount1;
  }
  // wait for 30 milliseconds to see the dimming effect
  delay(30);
  
  analogWrite(led2, brightness2);
  brightness2 = brightness2 + fadeAmount2;
  if (brightness2 <= 5 || brightness2 >= 255) {
    fadeAmount2 = -fadeAmount2;
  }
   delay(60);
}
```

<img width="1678" alt="Lab 01-PWM" src="https://user-images.githubusercontent.com/92038037/143786504-01930e53-accd-4c51-9af7-aaa4c75ff8bb.png">


https://user-images.githubusercontent.com/92038037/143786506-06f7a3d9-dd84-4038-843b-43a9c47989b5.mov



