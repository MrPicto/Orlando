# Invent a device relevant to your daily life

#### Function
When it is dark, the unit automatically turns on the lights and then closes the door tether. Staying at home is much more pleasant and safe.


#### Principle
Servo rotation angle varies with light intensity
When the light is low, the LED lights up, and the servo rotates to 90 degrees.

#### Coding

```
#include<Servo.h>
int LED=2;
Servo myservo;
int analogpin = A0;

void setup() {
  // put your setup code here, to run once:
  myservo.attach(9);
  pinMode(LED,OUTPUT);
  Serial.begin(9600);
  

}

void loop() {
  // put your main code here, to run repeatedly:
  int val=analogRead(analogpin);
  if(val>500){
    digitalWrite(LED,HIGH);
  }
  else
  {
    digitalWrite(LED,LOW);
    }
int num=map(val,0,1023,0,180);
Serial.println(num);
myservo.write(num);
delay(15);
}
```

#### Circuit diagram

https://user-images.githubusercontent.com/92038037/143781800-5fa7367d-0f4e-461d-b00b-49cc22d08505.mov

#### Practical operation

<img width="1102" alt="截屏2021-11-28 下午6 38 42" src="https://user-images.githubusercontent.com/92038037/143781980-3c71757a-7301-4475-ae64-7db042f9d791.png">

<img width="1108" alt="截屏2021-11-28 下午6 38 56" src="https://user-images.githubusercontent.com/92038037/143781984-15b9f454-e886-43cb-a6b5-5dabadef195e.png">

