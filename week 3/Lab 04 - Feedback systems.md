# Lab 04: Feedback systems

## Principle
This is one where the darker the surrounding light, the more the light comes on.
A system is formed to check the brightness of the surroundings. The brightness of the light also affects the sensing of the light sensitivity. If the surroundings are daylight, the LEDs will also go out. Such a feedback system keeps the surroundings at a brighter stage.

## Coding
```
int analogpin=A0;
int led[]={2,3,4,5};
int val = 0;

void setup()
{
  for(int i=0;i<4;i++)
  {
    pinMode(led[i], OUTPUT);
  }
  Serial.begin(9600);
}

void loop()
{
  val=analogRead(analogpin);
  Serial.println(val);
  int num= map(val,0,1023,0,4);
  Serial.println(num);
  for(int x=0;x<4;x++)
  {
  if(x<num)
  {
  digitalWrite(led[x],HIGH);
  }
    else
    {
      digitalWrite(led[x],LOW);
    }
  }
}
```

## Circuit diagram
![光线越暗亮的灯越多](https://user-images.githubusercontent.com/92038037/143786893-8f66d943-ba02-4a22-9d80-3e80843c6ff4.png)

## Running results

https://user-images.githubusercontent.com/92038037/143786896-3c54fa00-ffdf-4022-8f56-5be12057a846.mov

