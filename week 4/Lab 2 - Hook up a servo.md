# Lab 2 - Hook up a servo. 

Hook up a servo and make it move using pwm.

## Coding
```
// Include the Servo library 
#include <Servo.h> 
// Declare the Servo pin 
int servoPin = 3; 
// Create a servo object 
Servo Servo1; 
void setup() { 
   // We need to attach the servo to the used pin number 
   Servo1.attach(servoPin); 
}
void loop(){ 
   // Make servo go to 0 degrees 
   Servo1.write(0); 
   delay(500); 
   // Make servo go to 90 degrees 
   Servo1.write(90); 
   delay(1000); 
   // Make servo go to 180 degrees 
   Servo1.write(180); 
   delay(1500); 
}
```

## Circuit


https://user-images.githubusercontent.com/92038037/143787686-44d0c250-c6cd-4206-b525-e3ab597ac97d.mov




## Extended Operations



https://user-images.githubusercontent.com/92038037/143787758-f8d117ac-8feb-47c9-b4c7-e3b4b066982a.MOV



https://user-images.githubusercontent.com/92038037/143787772-1f5c3ae3-e54a-446e-b103-8363bbd432a5.MOV


