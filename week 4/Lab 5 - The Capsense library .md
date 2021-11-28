# Lab 5 - The Capsense library 

## Coding

```
#include <CapacitiveSensor.h>


CapacitiveSensor   cs_4_2 = CapacitiveSensor(4,2);        // 10M resistor between pins 4 & 2, pin 2 is sensor pin, add a wire and or foil if desired

void setup()                    
{
   Serial.begin(9600);
}

void loop()                    
{
    long start = millis();
    long total1 =  cs_4_2.capacitiveSensor(30);
 

    Serial.print(millis() - start);        // check on performance in milliseconds
    Serial.print("\t");                    // tab character for debug windown spacing

    Serial.print(total1);                  // print sensor output 1
    Serial.print("\t");
    Serial.print(total2);                  // print sensor output 2
    Serial.print("\t");

    delay(1000);                             // arbitrary delay to limit data to serial port 
}

```
<img width="625" alt="Lab 05" src="https://user-images.githubusercontent.com/92038037/143788805-36fe231f-4cf0-4fe2-9655-f8a0df961cc1.png">


## Result

The value becomes larger when the finger is placed on it. The value is usually greater than 10000

https://user-images.githubusercontent.com/92038037/143788724-423fcfc5-25ee-456f-bb93-f940e9f5e53f.MOV


