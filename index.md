![Headstone Image](https://raw.githubusercontent.com/BlueStampEng/BSE_Template_Portfolio/de8633f62b5da2234992a0178a6a72fd6df7e7e1/branding/BlueStamp-Logo.svg)
# Sunscreen Reminder Hat with UV Detector
This project reminds you to reapply sunscreen with a wearable circuit and UV index sensor all sown into a hat. The UV/visible light sensor detects if you are outside by seeing if the UV Index is greater than the set threshold. When someone is under direct sunlight, the sensor tells the mainboard that the threshold was crossed, to which the mainboard tells the buzzer to beep.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
|Trisha R | Dougherty Valley High School | Mechanical Engineering/Product Design | Incoming Sophomore

# About Me
Hi, my name is Trisha R, an aspiring Mechanical/Design Engineer who has been working on this project over the past three weeks. Although there were a lot of challenges along the way, I really enjoyed this project. Here is my portfolio!

<img src="https://user-images.githubusercontent.com/108947902/180490727-096718fb-a1f0-487e-8421-9173307e2145.jpeg" width="231" height="362" />

# Project Images
<img src="https://user-images.githubusercontent.com/108947902/180499029-b4b4f145-1562-45cd-ada2-c4af3dee09cf.jpg" />
<img src="https://user-images.githubusercontent.com/108947902/180499166-b2925b36-e370-49f8-9e35-cb016e52844f.jpg" />

  
# Final Milestone
My final milestone was sewing the components(the mainboard, piezo buzzer, UV Sensor, and 9V battery) onto the hat. I had to hold them in place so that when the battery was plugged into it's holder, it would not weigh down the rest of the devices. I also had to change the reapply interval in the code to 60 seconds, so the battery would not be exposed to direct sunlight for too long. In the end, I realized that a modification I would like to make in the future would be to build a battery holder with CAD, which would cover the battery and decrease the risk of it overheating. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/wUGRUNPWMo4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Second Milestone
My second milestone was soldering my UV sensor, buzzer, and battery connector to the mainboard. This made all my connections permanent and enabled all of them to work together. After they were all joined, I needed a separate code to have them all interact with each other. Once I found this code, I tweaked the reapply intervals to suit my needs. Some issues I fixed were the UV sensor not working because of the excess solder on the bottom of the sensor. I learned how to properly apply solder and clean it up to minimize residue.

<iframe width="560" height="315" src="https://www.youtube.com/embed/yx8pPPZKOJ8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# First Milestone
  

My first milestone was getting my UV/Visible light sensor to display UV, visible light, and IR levels to the serial monitor. I was able to do this by connecting my UV sensor to the mainboard(Adafruit Flora) and then inputting code that told the sensor to display its results to the serial monitor. I was also able to separately get my buzzer to play the Super Mario theme. I was able to do this by connecting my buzzer to the same mainboard and inputting code that had the tune and time intervals for the song.

<iframe width="560" height="315" src="https://www.youtube.com/embed/2a0s0enZTdU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Materials Used and Costs

| Item | Price | Link to Item | 
| ------------- | ------------- | ------------- |
| Adafruit Flora Mainboard | $14.95 | https://www.adafruit.com/product/659 |
| UV Sensor | $9.95 | https://www.adafruit.com/product/1777 |
| Piezo Buzzer | $1.50 | https://www.adafruit.com/product/160 |
| 9V Battery Clip | $2.95 | https://www.adafruit.com/product/80 |
| Alkaline 9V Battery | $1.50 | https://www.adafruit.com/product/1321 |
| Wire Stripper | $16.06 | https://www.amazon.com/Multi-Purpose-Stripper-Klein-Tools-1011/dp/B0000302WM/ref=asc_df_B0000302WM?tag=bingshoppinga-20&linkCode=df0&hvadid=80401843598485&hvnetw=o&hvqmt=e&hvbmt=be&hvdev=c&hvlocint=&hvlocphy=&hvtargid=pla-4584001419748637&psc=1 |
| Soldering Iron Kit | $19.99 | https://www.amazon.com/ANBES-Soldering-Iron-Kit-Electronics/dp/B06XZ31W3M/ref=asc_df_B06XZ31W3M?tag=bingshoppinga-20&linkCode=df0&hvadid=80195681205767&hvnetw=o&hvqmt=e&hvbmt=be&hvdev=c&hvlocint=&hvlocphy=&hvtargid=pla-4583795260585419&psc=1 |
| Mini Sewing Kit | $1.99 | https://www.hobbylobby.com/Fabric-Sewing/Sewing-Quilting-Notions/Sewing-Tools/Mini-Sewing-Kit/p/80932925?msclkid=df8cf73dc6d81958748e95e722c02395&utm_source=bing&utm_medium=cpc&utm_campaign=Shopping-Catch%20All&utm_term=4579809530712055&utm_content=Fabric%20Sewing-Sewing%20Quilting%20Notions |
| Wire Kit | $15.88 | https://www.amazon.com/CBAZYTM-Stranded-Gauge-colors-Electrical/dp/B0791FNV7W/ref=asc_df_B0791FNV7W?tag=bingshoppinga-20&linkCode=df0&hvadid=79989522876896&hvnetw=o&hvqmt=e&hvbmt=be&hvdev=c&hvlocint=&hvlocphy=&hvtargid=pla-4583589101730777&psc=1 |


# Code Used For Final Project
```cp
</*************************************************** 
  Sunscreen reminder hat using the Si1145 UV/IR/Visible Light Sensor
  visit https://learn.adafruit.com/sunscreen-reminder-hat for full tutorial
  
  contains Super Mario Bros theme composed for piezo by Tiago Gala: http://therandombit.wordpress.com/2011/11/21/arduino-piezo-speaker-super-mario/
  
  Written by Becky Stern for Adafruit Industries.  
  BSD license, all text above must be included in any redistribution
 ****************************************************/
 
#include <Wire.h>
#include "Adafruit_SI1145.h"

Adafruit_SI1145 uv = Adafruit_SI1145();

//tones for reminder tune
#define toneC    1911
#define toneC1    1804
#define toneD    1703
#define toneEb    1607
#define toneE    1517
#define toneF    1432
#define toneF1    1352
#define toneG    1276
#define toneAb    1204
#define toneA    1136
#define toneBb    1073
#define toneB    1012
#define tonec       955
#define tonec1      902
#define toned       851
#define toneeb      803
#define tonee       758
#define tonef       716
#define tonef1      676
#define toneg       638
#define toneab      602
#define tonea       568
#define tonebb      536
#define toneb       506
#define tonep       0 
int speaker = 1; // piezo wired to FLORA TX


uint32_t sinceTime;
uint32_t markerTime;
boolean shouldChime = false;
float UVindex;
float UVthreshold = 0.05;
uint32_t reapplyInterval = 10000; // 15 minutes = 900000 milliseconds. One hour = 3600000 milliseconds. Two hours = 7200000 milliseconds

void setup() {
  pinMode(speaker, OUTPUT);
  Serial.begin(9600);
  Serial.println("Adafruit SI1145 test");
  if (! uv.begin()) {
    Serial.println("Didn't find Si1145");
    while (1);
  }
  Serial.println("OK!");
}

void loop() {
  Serial.println("===================");
  UVindex = uv.readUV(); 
  UVindex /= 100.0; // the index is multiplied by 100 so to get the integer index, divide by 100!  
  Serial.print("UV: ");  Serial.println(UVindex);
  Serial.print("Seconds until next alert: ");  Serial.println((reapplyInterval-sinceTime)/1000);
  delay(1000);
  
  sinceTime = millis()-markerTime;
  
  if (UVindex > UVthreshold && shouldChime){ //only chime when we are currently outside
    chime();
    Serial.println("===================");
    Serial.println("CHIME");
    shouldChime = false;
    resetTimer();
  }
  if (sinceTime > reapplyInterval) { //check to see if we've exceeded the time limit
    shouldChime = true;
    resetTimer; 
  }
  
}

void resetTimer(){
  markerTime = millis();
  sinceTime = 0;
}

void chime(){
int melody[] = {tonec, toneG, toneE, toneA, toneB, toneBb, toneA, toneG, tonee, toneg, tonea, tonef, toneg, tonee, tonec, toned, toneB};
int rhythm[] = {18, 18, 18, 12, 12, 6, 12, 8, 8, 8, 12, 6, 12, 12, 6, 6, 6};
long vel = 20000;

for (int i=0; i<17; i++) {
    int note = melody[i];
    int tempo = rhythm[i];
 
    long tvalue = tempo * vel;
 
    //tocar(note, tvalue);
    long tempo_progress = 0;
  while (tempo_progress < tvalue) {
    digitalWrite(speaker, HIGH);
    delayMicroseconds(note / 2);
 
    digitalWrite(speaker, LOW);
    delayMicroseconds(note/2);	 
    tempo_progress += note;
  }
 
    delayMicroseconds(1000);
  }

}
>
```
