# expressing emotions Plants

Many people now have plants. Because of the COVID-19, most of the activities of people are concentrated in the home.  Plants can add to the enjoyment of the house. But people don't know the preferences of plants and how to rinse them, sometimes over-watering or forgetting to water them leads to the death of the plant.  But a plant is a static being. It should have its preferences and emotions too! Let people know when it needs water. So I designed this plant installation to feel the plant's happiness and sadness and react to it. To make people think that there is a quiet little life in their lives.

## scenario
<img width="301" alt="截屏2021-12-01 下午5 36 47" src="https://user-images.githubusercontent.com/92038037/144284845-7618eca8-115e-42b3-9dd2-097d13677c61.png">

## components
<img width="445" alt="截屏2021-12-01 下午5 37 26" src="https://user-images.githubusercontent.com/92038037/144285031-e2af80aa-99d9-4fd1-80ea-9f29a2696cad.png">

## The code
```
#include <Adafruit_NeoPixel.h>
#include <Servo.h>           
#define PIN 3  //灯 3号
#define NUMPIXELS  12
Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRB + NEO_KHZ800);

Servo servo1; 
int shock=4;//震动电机 4
int raindrop=5;//雨滴传感器 5号
int tonepin=11;  
#define Do 262    
#define Re 294  
#define Mi 330  
#define Fa 349  
#define Sol 392  
#define La 440  
#define Si 494  
#define Do_h 523  
#define Re_h 587  
#define Mi_h 659  
#define Fa_h 698  
#define Sol_h 784  
#define La_h 880  
#define Si_h 988

void setup() 
{ 
      pixels.begin();             
      Serial.begin(9600);     
      pinMode(shock,OUTPUT);   
      pinMode(raindrop,INPUT);  
       servo1.attach(9);   //舵机9
       servo1.write(0);  

       
 } 
 int humidity,Raindrop;
 int flag=0;
 int rain_flag=0;
 int humidity_flag=0;
 void loop() 
 {  
  
  humidity = analogRead(A0); //湿度模拟值
  Raindrop = digitalRead(raindrop);//雨滴传感器
  Serial.print(humidity);//打印值
  Serial.println(Raindrop);
  
     if(Raindrop==0&&rain_flag<3)      //下雨
     { 
          Led_W();         
        for(int i=0;i<3;i++) 
       { digitalWrite(shock, HIGH);
        delay(100);
         digitalWrite(shock, LOW); }
          rain_flag++;   
        }
        
    else {
      rain_flag=0; 
      if(humidity>200&&humidity_flag==0)   
        { 
          for(int i=0;i<3;i++){
        servo1.write(90);/
        Led_R();         
        humidity_flag=1;
        for(int i=0;i<3;i++) 
         { digitalWrite(shock, HIGH);
            delay(100);
            digitalWrite(shock, LOW); }
         }  
         }  
     else if(humidity<200&&humidity_flag==1)   
      {
        for(int i=0;i<2;i++){
         servo1.write(0); 
         Led_G();         
         humidity_flag=0;
         }
        }
 }
 }



 void  Led_W()           
{
  for (int i=0; i < 12; i++) {
    int a;
     a++;
     voice(a);
     if(a>5)a=0;
 pixels.setPixelColor(i-1, pixels.Color(0, 0, 0)); 
 pixels.setPixelColor(i, pixels.Color(255, 255, 255)); 
 pixels.show();
 delay(200);
  }
  }

  
void Led_R()            //红灯闪烁
{
  int a=0;
     a++;
     voice1(a);
     if(a>5)a=0;
  for (int i=0; i < 12; i++) {
 pixels.setPixelColor(i, pixels.Color(255, 100, 0));
  }
  pixels.show();
  delay(200);
   for (int i=0; i < 12; i++) {
 pixels.setPixelColor(i, pixels.Color(0, 0, 0));
  }
  pixels.show();
  delay(200);
  }

  
void Led_G()                //绿色呼吸
{
  for (int i=0; i < 12; i++) {
 pixels.setPixelColor(i, pixels.Color(0, 255, 100));
  }pixels.show();
  int a=0;
   for(int i=10;i<255;i+=50) 
   {
     a++;
     voice(a);
     if(a>5)a=0;
    pixels.setBrightness(i);  
     pixels.show();
   delay(200);}
     for(int i=255;i>0;i-=50) 
   {     a++;
     voice(a);
     if(a>5)a=0;
  pixels.setBrightness(i);  
     pixels.show();
     delay(200);}
}



void voice(int x)//开心声调
{
int length;
int scale[]={Sol,Sol,La,Sol,Do_h};        
float durt[]={0.5,0.5,1,1,1}; 
 length=sizeof(scale)/sizeof(scale[0]);   

  tone(tonepin,scale[x]);
    delay(500*durt[x]);  
    delay(100*durt[x]);
    noTone(tonepin);
  }
void voice1(int x)//悲伤声调
{
int length;
int scale1[]={Re,Do,La,Do,Re};    
float durt1[]={0.5,0.5,1,1,1}; 
 length=sizeof(scale1)/sizeof(scale1[0]);  

  tone(tonepin,scale1[x]);
    delay(500*durt1[x]);   
    delay(100*durt1[x]);
    noTone(tonepin);
  }
  ```
  <img width="546" alt="截屏2021-12-01 下午5 38 01" src="https://user-images.githubusercontent.com/92038037/144285341-fdcdb6ff-ed8a-44c2-ade5-62b0b70d16b5.png">

## The process

### Modeling
![Uploading 截屏2021-12-01 下午4.23.43.png…]()

### 3D print

### Soldering
![Uploading 截屏2021-12-01 下午4.17.49.png…]()

### components
  ![Uploading 截屏2021-12-01 下午4.18.28.png…]()
  
### test
![Uploading 截屏2021-12-01 下午4.17.23.png…]()

### Assembling
![Uploading 截屏2021-12-01 下午4.39.39.png…]()

### final
![Uploading 截屏2021-12-01 下午4.40.37.png…]()



