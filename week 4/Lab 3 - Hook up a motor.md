# Lab 3 - Hook up a motor 

## Coding
```
// C++ code

const int switchPin = 2;
const int motorPin = 9;
int switchState = 0;

void setup()
{
  pinMode(motorPin, OUTPUT);
  pinMode(switchPin,INPUT);
}

void loop()
{
  switchState= digitalRead(switchPin);
  
  if(switchState == HIGH){
  digitalWrite(motorPin,HIGH);
    
  }else{
    digitalWrite(motorPin,LOW);
  }
  
}
```

## circuit


https://user-images.githubusercontent.com/92038037/143787971-44aea9db-eeb0-41ca-aad8-998be854d777.mov

