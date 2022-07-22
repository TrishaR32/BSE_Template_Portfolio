# Sunscreen Reminder Hat with UV Detector
This project reminds you to reapply sunscreen with a wearable circuit and UV index sensor all sown into a hat. The UV/visible light sensor detects if you are outside by seeing if the UV Index is greater than the set threshold. When someone is under direct sunlight, the sensor tells the mainboard that the threshold was crossed, to which the mainboard tells the buzzer to beep.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
|Trisha R | Dougherty Valley High School | Mechanical Engineering/Product Design | Incoming Sophomore

![Headstone Image](https://github.com/BlueStampEng/BSE_Template_Portfolio/blob/4655d8c4b2f1d0fa5912511d0b39542520b9f88e/branding/BlueStamp-Engineering-Logo-White.png)
  
# Final Milestone
My final milestone was sewing the components(the mainboard, piezo buzzer, UV Sensor, and 9V battery) onto the hat. I had to hold them in place so that when the battery was plugged into it's holder, it would not weigh down the rest of the devices. I also had to change the reapply interval in the code to 60 seconds, so the battery would not be exposed to direct sunlight for too long. In the end, I realized that a modification I would like to make in the future would be to build a battery holder with CAD, which would cover the battery and decrease the risk of it overheating. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/wUGRUNPWMo4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Second Milestone
My second milestone was soldering my UV sensor, buzzer, and battery connector to the mainboard. This made all my connections permanent and enabled all of them to work together. After they were all joined, I needed a separate code to have them all interact with each other. Once I found this code, I tweaked the reapply intervals to suit my needs. Some issues I fixed were the UV sensor not working because of the excess solder on the bottom of the sensor. I learned how to properly apply solder and clean it up to minimize residue.

<iframe width="560" height="315" src="https://www.youtube.com/embed/yx8pPPZKOJ8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# First Milestone
  

My first milestone was getting my UV/Visible light sensor to display UV, visible light, and IR levels to the serial monitor. I was able to do this by connecting my UV sensor to the mainboard(Adafruit Flora) and then inputting code that told the sensor to display its results to the serial monitor. I was also able to separately get my buzzer to play the Super Mario theme. I was able to do this by connecting my buzzer to the same mainboard and inputting code that had the tune and time intervals for the song.

<iframe width="560" height="315" src="https://www.youtube.com/embed/2a0s0enZTdU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
