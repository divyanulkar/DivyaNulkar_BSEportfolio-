
# Knee Health Device 

This device is built to help aid in recovery and monitor knee health after trauma like surgery or injury. This project work through three main components. The first component is the flex sensor which is strapped down across the knee cap. The flex sensor is connected to a buzzer which is set on a timer sequence meaning that every 5 seconds or so the buzzer will start snd will not turn off until the flex sensor has bent 5 times. This is good for recovery because when the knee has experienced trauma it tends to swell or bruise up and stagnation makes these conditions worse, so through this it can promote movement. Next is the heat sensor which has skin contact and is monitoring body temp so that when the body temp reaches a couple degrees above average body temp a LED will turn on signaling to the user that it is time to cool the knee down. Lastly the project includes a separate manual circuit of vibration motors. These motors are grouped in the major muscles around the knee cap and provide gentle massage which is good for circulation and drainage of swelling. 


| Divya N | Notre Dame San Jose | bio engineering | Incoming Sophmore |


<img width="501" height="667" alt="Screenshot 2026-07-29 at 11 46 27 AM"   src="https://github.com/user-attachments/assets/8c03f82d-464f-411d-bbee-49c52c573bbf" />

  
# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/kUO8kjBzOEY?si=Z-N3mdU5uKEAukQ_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Flex Sensor 
- I made the code for my flex sensor more complicated by making it so that when the buzzer starts it will no not turn off until the flex sensor is bent over its threshold angle 5 times.
- Once the movement is made the buzzer will turn off and the loop will restart
- When I was coding this I had to create an average system where the data will be grouped by 5 data points and take the average and work off of the averages. I had to do this because with the data was recording so fast that the computer couldn't process it and it was making the program freeze and not work properly. 
- This is good for the period of recovery after trauma because it promotes movement. When a part of our body has experienced trauma it tends to swell or stiffen up and by promoting movement this device works to help prevent these conditions from progressing. 

### vibration motors 
- I added a vibration motors system that is on a completely separate manual circuit. 
- For the vibration motors I hand sewed 17 pockets into the inside of the knee sleeve grouped around the major muscles like the quad and hamstring. 
- These motors work to provide gentle massage which is good for recovery
- These motors are wired up to a battery pack and a switch making them completely manual
- I wired the 17 vibration motors using parallel wiring. This was tricky because the vibration motors wring are really tiny and break very easily. 

### Other Changes 
- I used Onshape to create a casing for my perf board and wires and printed it using a 3d printer.
<img width="371" height="258" alt="Screenshot 2026-07-14 at 10 36 34 AM" src="https://github.com/user-attachments/assets/89293021-ce4a-4963-b5af-6c58e7efe66e" />
- I sewed all the components onto the knee sleeve including the perf board and the flex sensor. 
Some of my biggest triumphs at Bluestamp were earning how to code and use CAD from scratch and being able to create my very own project and being able to figure everything out mostly by myself. Some of the challenges I faced were learning how to code and debug from the ground up since I had no background knowledge. I hope to learn more in depth details about the concepts and materials I learned to use. 

# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/KhlVvR0ihYA?si=B1reRM3LcVzIZag9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In my second milestone I mainly added a mechanism that works through a heat sensor to sense when the knee gets above normal body temperature.

### Heat Sensor
- The heat sensor will be set with a threshold of a couple degrees above average body temperature so that when it senses the heat of the skin surrounding the knee go above this threshold it will trigger an LED to turn on which tells the user that they should start icing the knee or working to bring it back to body temp or below.
- Once the heat sensor senses that the temperature has been brought back to normal the LED will turn off. 
- This will work to sense irritation or swelling.
 
I also transfered all of my wiring onto a seperate perf board from the breadboard so that it will be easier to attach and more streamlined when on the knee sleeve. Some of the challenges that I have faced is that the wiring on the baord is more sensitive than on the breadboard so some of the connections that I had on the breadboard that were previously working wouldnt work on the breadboard and I had to desolder a bunch of wiring that got messy or wasn't necessary, otherwise this mostly solved the previous problems I had with the breadboard. Before my final milestone I hope to make some of my code more complex, add vibration motors, and create a casing for the components so it isn't easily damaged when used. 

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/WVMoodIAWxw?si=KPYxJxQyxa5LbJWe" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

My project is a Knee Rehab Device that is aimed for the time after knee surgery to help that period go smoother and speed recovery. In my first milestone I mostly worked on the flex sensor components of my project. 

### Flex Sensor
- I first used TinkerCAD to create a layout of how I would wire up the buzzer with the flex sensor and through TinkerCAD I was able to use a combination of block and text code to program the flex sensor and buzzer to create a system where the buzzer will start on a timer sequence, having it turn on every 5 seconds and only turn off when the flex sensor is bent over the original angle or threshold angle. Once the buzzer turns off the loop will restart.
- In use this will correspond to the user having to bend their knee to turn off the buzzer
- A problem I had with this was that the range of data sets from the flex sensor were completely different in TinkerCAD versus the Arduino C++ so I had to debug that and create a new threshold.  

So far the main challenge I have faced is the coding and making sure that the grammar is correct and I hope to combat this challenge by just learning more about coding and familiarizing myself with it. Additionally the other problem that I have been facing is that in this milestone I have the wiring and sensors connected to a breadboard, therefore it is quite clunky and the wires are getting messed up and the wires fall out really easily so they can get lost. I am going to combat this issue by transferring all of the wiring onto a separate board through soldering which will be easier to attach to the finalized project. To complete my project I need to add heat sensors, vibration sensors, and an outer casing. 

# Schematics 
<img width="577" height="681" alt="Screenshot 2026-07-29 at 10 05 54 AM" src="https://github.com/user-attachments/assets/b671c95b-e2f9-47fe-896b-d0c6ac60d434" />
This is a tinker clad diagram of my Arduino wiring for the flex sensor and the temperature sensor. The one above is the original wiring for the temperature and flex sensor and the bottom one is the revised flex sensor that is currently in my project.
<img width="1034" height="370" alt="Screenshot 2026-07-29 at 10 04 53 AM" src="https://github.com/user-attachments/assets/597c1054-d8f0-4467-a24a-5e34abf1a7b1" />
This is the flow chart for the revised flex sensor wiring.
<img width="948" height="354" alt="Screenshot 2026-07-29 at 10 05 38 AM" src="https://github.com/user-attachments/assets/18ac9546-f0de-408d-a1ae-0c65a2152132" />
This is the temperature pin wiring and the old flex sensor wiring. 

# Code

```cpp
// C++ code

// pin numbers
int const BUZZER = 8;
int const LED = 6;
int const FLEX = A0;
int const TEMP = A1;
int const THRESHOLD_ANGLE = 1300;

/* defining and initializing variables */
int sensor = 0; //value of the flex sensor
float temperature = 0; //value of the temperature sensor
int secondsPassed = 0; //reg seconds

int buzzer = 0; //will either be high or low

int bendsCount = 0; //counts the number of bends

int sensorAverage[5]; //will hold 5 values in the list
float temperatureAverage[5]; //also holds 5 values bc numbers are hard

unsigned long startTime;

bool prevBend = false;

bool currentlyBending = false;


void setup() {
  pinMode(FLEX, INPUT);
  pinMode(BUZZER, OUTPUT);
  pinMode(TEMP, INPUT);
  pinMode(LED, OUTPUT);
  Serial.begin(9600);
  // reset count and timer
  bendsCount = 0;
  secondsPassed = 0;
  startTime = millis();

  //put the buzzer and LED at low to begin
  digitalWrite(BUZZER, LOW);
  digitalWrite(LED, LOW);

  //Serial.println("done setup");
}

void loop() {

  //average the values for all sensors
  for(int i = 0; i < 5; i++){
    sensorAverage[i] = analogRead(FLEX); // read input from flex sensor
    temperatureAverage[i] = analogRead(TEMP); //read input from temp sensor
    sensor += sensorAverage[i]; // add the thing for the average
    temperature += temperatureAverage[i];
  }

  //average all this 
  sensor = sensor / 5;
  temperature = temperature / 5;
  Serial.print("sensor average: ");
  Serial.println(sensor);
  Serial.print("temp average: ");
  Serial.println(temperature);

  //check temp value
  if (temperature > 5){
    digitalWrite(LED, HIGH);
  } else {
    digitalWrite(LED, LOW);
  }

  //if sensor has passed the threshold angle then the sensor is being marked as moving
  if (sensor < THRESHOLD_ANGLE) {
    currentlyBending = true;
  } else {  // otherwise mark as currently not bending
    currentlyBending = false;
  }
  // if the sensor first starts bending the bends count will increase by 1
  if (currentlyBending == true && prevBend == false) {
    bendsCount = bendsCount + 1;
    Serial.println("detected bend");
    Serial.print("bendsCount =");
    Serial.println(bendsCount);
  }
  // if bends count is between 0 and 5 then the buzzer will turn on
  if (bendsCount < 5 && bendsCount > 0) {
    digitalWrite(BUZZER, HIGH);
    // if the bends count it at 5 it will rest to 0 after
  } else if (bendsCount == 5) {
    digitalWrite(BUZZER, LOW);
    bendsCount = 0;
    startTime = millis();  // reset timer
  }
  // if bends count is at 0 then the buzzer will turn off and the delay will begin
  else if (bendsCount == 0) {
    Serial.println(millis());
  }

  // every 2 seconds that the counter is idle at 0 the buzzer will go off
  if (millis() - startTime >= 2000) {
    digitalWrite(BUZZER, HIGH);
  }

  prevBend = currentlyBending;  // updating new bend values
  sensor = 0; // reset the sensor values
  temperature = 0;
  delay(500);
}
```

# Bill of Materials 

| **Part** | **Note** | **Price ( all parts from class inventory)** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino ESP 32 | to run the coding programs and functions | **N/A**| <a href="https://www.amazon.com/Arduino-ABX00083-Bluetooth-MicroPython-Compatible/dp/B0C947BHK5/ref=sr_1_3?crid=2ZT7FG77UAXIQ&dib=eyJ2IjoiMSJ9.GzP-GvhsR81ftjmV7C-hRYZKKdZl_4SwzDvNEsHgVcLoYJVFDWc5T2POXGlffBrcPYmtAKaYjdgqurHsVfxbejPZ0xununAKwPtPorv1Or_D3IEWNb8D-5KM1CpmDzKoQPMT4qYf0p2Q9quOijB5SemdqrOituGGzBzKImNQPfUkn7_xOSk96e3QSpkerS6wMMqatvZvzJK4J90q4IR9azkBiTayVDki47DS-cQIkRY.U0pLrz3XV0lYptfI82i4Yier_YyResIeZ_ockh8klX0&dib_tag=se&keywords=arduino%2BESP%2B32&qid=1784915785&sprefix=arduino%2Besp%2B32%2Caps%2C228&sr=8-3&th=1"> Link </a> |
| vibration motors | for the massage components | $20 | <a href="https://www.amazon.com/tatoko-Vibration-Button-Type-Vibrating-Appliances/dp/B07Q1ZV4MJ/ref=sr_1_1?crid=2CPDD952MEU2O&dib=eyJ2IjoiMSJ9.HTvxIg-MEPtwsJO9b-7sgN6GmQvrrwp-PXhlhdd9rW0NQFVadk9GZdpkDgs9Z8fbMha-NHdmLuDBKvFUrv3ZC07foD-ax1tcBnGqvT0-7HVIH-JWSSxJ-BBjePp8eHd4mT3zxTFvQnpq1xCYdifyQsnYFLi8JhvMCPQ4T7CdbsOuu7fHvXI6vFtVY_R9QxTyjoj22T1mZCpmakLgP9P1u2gBnElGKAVFmbte89REbRZP3nbpaw7z44noLSc9qzmIR5Q4s-EkKEAxJd08x6tjbAef7KqT2vzoJS8iW9z__E8.OumuizteFDQnV_KpBceEzciXogwx7UtMg5hhdgUFokM&dib_tag=se&keywords=vibration+motors&qid=1784915844&sprefix=vibration+motor%2Caps%2C227&sr=8-1"> Link </a> |
| perf board | to hold and connect the wiring and sensors | **N/A**| <a href= "https://www.amazon.com/EPLZON-Solder-able-Breadboard-Electronics-Compatible/dp/B09WZXHMDG/ref=sxin_19_pa_sp_search_thematic_sspa?content-id=amzn1.sym.292df443-b323-44ae-8b40-9a666975b8b5%3Aamzn1.sym.292df443-b323-44ae-8b40-9a666975b8b5&crid=K1RY218PMUCH&cv_ct_cx=perf%2Bboard%2Bpcb&keywords=perf%2Bboard%2Bpcb&pd_rd_i=B09WZXHMDG&pd_rd_r=107d8575-967a-449f-b88c-05cf8dc0f3e4&pd_rd_w=mcXGb&pd_rd_wg=C8LIY&pf_rd_p=292df443-b323-44ae-8b40-9a666975b8b5&pf_rd_r=R6RQTE3KPK1SB66QVDVK&qid=1784915913&sbo=RZvfv%2F%2FHxDF%2BO5021pAnSA%3D%3D&sprefix=perf%2Bb%2Caps%2C249&sr=1-3-6024b2a3-78e4-4fed-8fed-e1613be3bcce-spons&aref=UwSlgOeuGu&sp_csd=d2lkZ2V0TmFtZT1zcF9zZWFyY2hfdGhlbWF0aWM&th=1"> Link </a> |
| piezo buzzer | used as an alarm to alert the user to move their knee | **N/A**| <a href= "https://www.amazon.com/Passive-Resistance-Electronic-Magnetic-Continuous/dp/B0F1KFHSNK/ref=sr_1_1_sspa?crid=3IDL8TSAR9I18&dib=eyJ2IjoiMSJ9.Kc1lRhz-FXgslMSBkHup92TrgatbcmKjHDhGHIPi0nlIRxWJnk3IHuBUBZn6kKomqyARpia0L45US77lRk9dW4ktN0YjHZZUStb8R9VE44QVqCQesoObH3gnzE1RBrxcvhzmurVva1oPec6IU2uQxL1uP44Vun6blZihLjJZMB2QaCqF-qhnh0EGg08La3efOzx8AuL5kMLpx7udrPv-vwdH0tzRCDbcJeigYTJkOh8.VcWHiWjbG9vl0ADXt4IAsks02zcVEgR14hSQWhBDn-8&dib_tag=se&keywords=piezo%2Bbuzzer&qid=1785168354&sprefix=piezo%2Bbu%2Caps%2C226&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1"> Link </a> |
| heat sensor | to detect when the skin exceeds body temp | **N/A** | **Link** |
| LED | to connect to the heat sensor to alert user | **N/A** | **Link** |
| knee sleeve  | to hold all components | **N/A** | <a href= "https://www.amazon.com/knee-braces-pain-joint-sleeves/dp/B08JGP1WYM/ref=sr_1_1_sspa?crid=2NZL6OW6DXCK0&dib=eyJ2IjoiMSJ9.R6xK_GZsR19k7bE0V-hrMVKpqOUuHxED3YoOy0NV7y0VFzynb8pcFPXcVKVHuAWWjCdXj_HfXWiAxw8yvyRspaSktbqm1sPTTV0rAFElyJ-HkNQD5REbhzAAYi11Io5OCmk_lCoptzcbaOzHBr5pJGB-Riy1Es4wwJNhGZYa4jMv2SE6xwJ10RkVbCX6qFadvCiVSmZjNy3tY5mwXHQTTB9GXGb4gmCYWA9nEy8PzG9ig478u7azt55EPr_MxalshA8CTI-GSfQt-rcRMZdycIzyLJekTkhQ9objXxrKvqg.Q6Fo_n7d3Ok0Cwe04Dmf5p285MqVNVPhZAutOpkcGFc&dib_tag=se&keywords=knee%2Bsleeve&qid=1785341071&sprefix=knee%2Bsleev%2Caps%2C214&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1"> Link </a>|
| flex sensor  | to record angles of knee bending | **N/A** | <a href= "https://www.amazon.com/Spectra-Symbol-Flex-Sensor-Variant/dp/B0D3FFWJZ9/ref=sr_1_2_sspa?crid=2YWQFG81RA8YQ&dib=eyJ2IjoiMSJ9.-xk5jWy9x9kEwqQM3ljrc09AjNjWfFZRHtnmFuVn6YenWtquzl26_jQjLDDJTAiP4ac-7T8FJIax2YS_sYIHd-PS4eXz2okzgh4Hq2gdmqoTkfGE9vrKGSfvHlK40sEWDcmzMJyHIL346Avnac09MNGgYJR7L-9IZRK1vOcxRlNJ3S_vsq_85iwrki6KjKqFYrNrC7cDuD3CO1p2eB-GlQ4wjJya4OqJCJmg8wQYQBE.2usDj0pbAUrVsQ3aeBj90yeiLSK8ou6l6kaNgwcZXWI&dib_tag=se&keywords=flex+sensor&qid=1785340994&sprefix=flex+sensor%2Caps%2C207&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1"> Link </a>|

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [TinkerCAD](https://www.tinkercad.com/dashboard)
- [Arduino Platform downloading support] (https://support.arduino.cc/hc/en-us/articles/360019833020-Download-and-install-Arduino-IDE)
- [onshape](https://www.onshape.com/en/)

To watch the BSE tutorial on how to create a portfolio, click here.
