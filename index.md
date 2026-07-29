# Knee Rehab Device 
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails!

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Divya N | Notre Dame San Jose | bio engineering | Incoming Sophmore

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/kUO8kjBzOEY?si=Z-N3mdU5uKEAukQ_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Since my previous milestone I have added multiple new things. For example I added a vibration motor system with multiple motors sewn into the inside of the knee sleeve and connected to a manual switch. I also created a casing for my perf board using CAD and sewed everything into the knee sleeve. furthermore I was also able to make the code for my flex sensor more complicated to make it so that the timer will trigger the buzzer to start and not turn off until the knee has been bent 5 times, triggering a sequence of movement. Some of my biggest triumphs at Bluestamp were earning how to code and use CAD from scratch and being able to create my very own project and being able to figure everything out mostly by myself. some of the challenges I faced were learning how to code and debug from the ground up since I had no background knowledge. I hope to learn more in depth details about the concepts and materials I learned to use. 

# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/KhlVvR0ihYA?si=B1reRM3LcVzIZag9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In my second milestone I mainly added a mechanism that works through a heat sensor to sense when the knee gets above normal body temperature so in practical sense the sensor will be able to detect heat from probable swelling or irritation. Once the mechanism senses heat above it set constraits (average body temperature) it will trigger an LED that will turn on until the mechanism senses that the body temperature has gone back to the normal range. I also transfered all of my wiring onto a seperate perf board from the breadboard so that it will be easier to attach and more streamlined when on the knee sleeve. Some of the challenges that I have faced is that the wiring on the baord is more sensitive than on the breadboard so some of the connections that I had on the breadboard that were previously working wouldnt work on the breadboard and I had to desolder a bunch of wiring that got messy or wasn't necessary, otherwise this mostly solved the previous problems I had with the breadboard. Before my final milestone I hope to make some of my code more complex, add vibration motors, and create a casing for the components so it isn't easily damaged when used. 

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/WVMoodIAWxw?si=KPYxJxQyxa5LbJWe" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

My project is a knee rehab device that is aimed for the time after knee surgery to help that period go smoother and speed recovery. In my first mileston I built a mechanism that works on a timer that will go off on a set schedule, starting a buzzer that will not turn off until the flex sesor that is wired to it is bent over the original angle. In other words the timer will keep going until the person bends their knee, moving the flex sensor and turning off the buzzer. So far the main challenge I have faced is the coding and making sure that the grammer is correct and I hope to combat this challenge by just learning more about codng and familiarising myself with it. addiitonally the other problem that i have been facing is that in this milestone i have the wiring and sensors connected to a breadboard, therefore it is quite clunky and the wires are getting messed up and the wires fall out really easilly so they can get lost. i am going to combat this issue by transfering all of the wiring onto a seprate board through soldering which will be easier to attach to the finialized project. To complete my project I need to add heat sensors, vibration sensors, and an outer casing. 

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```// C++ code

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
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price ( all parts from class inventory)** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino ESP 32 | to run the coding programs and functions | | <a https://www.amazon.com/Arduino-ABX00083-Bluetooth-MicroPython-Compatible/dp/B0C947BHK5/ref=sr_1_3?crid=2ZT7FG77UAXIQ&dib=eyJ2IjoiMSJ9.GzP-GvhsR81ftjmV7C-hRYZKKdZl_4SwzDvNEsHgVcLoYJVFDWc5T2POXGlffBrcPYmtAKaYjdgqurHsVfxbejPZ0xununAKwPtPorv1Or_D3IEWNb8D-5KM1CpmDzKoQPMT4qYf0p2Q9quOijB5SemdqrOituGGzBzKImNQPfUkn7_xOSk96e3QSpkerS6wMMqatvZvzJK4J90q4IR9azkBiTayVDki47DS-cQIkRY.U0pLrz3XV0lYptfI82i4Yier_YyResIeZ_ockh8klX0&dib_tag=se&keywords=arduino%2BESP%2B32&qid=1784915785&sprefix=arduino%2Besp%2B32%2Caps%2C228&sr=8-3&th=1> Link </a> |
| vibration motors | for the massage components | $20 | <a https://www.amazon.com/tatoko-Vibration-Button-Type-Vibrating-Appliances/dp/B07Q1ZV4MJ/ref=sr_1_1?crid=2CPDD952MEU2O&dib=eyJ2IjoiMSJ9.HTvxIg-MEPtwsJO9b-7sgN6GmQvrrwp-PXhlhdd9rW0NQFVadk9GZdpkDgs9Z8fbMha-NHdmLuDBKvFUrv3ZC07foD-ax1tcBnGqvT0-7HVIH-JWSSxJ-BBjePp8eHd4mT3zxTFvQnpq1xCYdifyQsnYFLi8JhvMCPQ4T7CdbsOuu7fHvXI6vFtVY_R9QxTyjoj22T1mZCpmakLgP9P1u2gBnElGKAVFmbte89REbRZP3nbpaw7z44noLSc9qzmIR5Q4s-EkKEAxJd08x6tjbAef7KqT2vzoJS8iW9z__E8.OumuizteFDQnV_KpBceEzciXogwx7UtMg5hhdgUFokM&dib_tag=se&keywords=vibration+motors&qid=1784915844&sprefix=vibration+motor%2Caps%2C227&sr=8-1> Link </a> |
| perf board | to hold and connect the wiring and sensors | | <a https://www.amazon.com/EPLZON-Solder-able-Breadboard-Electronics-Compatible/dp/B09WZXHMDG/ref=sxin_19_pa_sp_search_thematic_sspa?content-id=amzn1.sym.292df443-b323-44ae-8b40-9a666975b8b5%3Aamzn1.sym.292df443-b323-44ae-8b40-9a666975b8b5&crid=K1RY218PMUCH&cv_ct_cx=perf%2Bboard%2Bpcb&keywords=perf%2Bboard%2Bpcb&pd_rd_i=B09WZXHMDG&pd_rd_r=107d8575-967a-449f-b88c-05cf8dc0f3e4&pd_rd_w=mcXGb&pd_rd_wg=C8LIY&pf_rd_p=292df443-b323-44ae-8b40-9a666975b8b5&pf_rd_r=R6RQTE3KPK1SB66QVDVK&qid=1784915913&sbo=RZvfv%2F%2FHxDF%2BO5021pAnSA%3D%3D&sprefix=perf%2Bb%2Caps%2C249&sr=1-3-6024b2a3-78e4-4fed-8fed-e1613be3bcce-spons&aref=UwSlgOeuGu&sp_csd=d2lkZ2V0TmFtZT1zcF9zZWFyY2hfdGhlbWF0aWM&th=1> Link </a> |
| piezo buzzer | used as an alarm to alert the user to move their knee | | https://www.amazon.com/Passive-Resistance-Electronic-Magnetic-Continuous/dp/B0F1KFHSNK/ref=sr_1_1_sspa?crid=3IDL8TSAR9I18&dib=eyJ2IjoiMSJ9.Kc1lRhz-FXgslMSBkHup92TrgatbcmKjHDhGHIPi0nlIRxWJnk3IHuBUBZn6kKomqyARpia0L45US77lRk9dW4ktN0YjHZZUStb8R9VE44QVqCQesoObH3gnzE1RBrxcvhzmurVva1oPec6IU2uQxL1uP44Vun6blZihLjJZMB2QaCqF-qhnh0EGg08La3efOzx8AuL5kMLpx7udrPv-vwdH0tzRCDbcJeigYTJkOh8.VcWHiWjbG9vl0ADXt4IAsks02zcVEgR14hSQWhBDn-8&dib_tag=se&keywords=piezo%2Bbuzzer&qid=1785168354&sprefix=piezo%2Bbu%2Caps%2C226&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1 |
| heat sensor | to detect when the skin exceeds body temp | **Price** | **Link** |
| LED | to connect to the heat sensor to alert user | **Price** | **Link** |
| knee sleeve  | to hold all components | **Price** | https://www.amazon.com/knee-braces-pain-joint-sleeves/dp/B08JGP1WYM/ref=sr_1_1_sspa?crid=2NZL6OW6DXCK0&dib=eyJ2IjoiMSJ9.R6xK_GZsR19k7bE0V-hrMVKpqOUuHxED3YoOy0NV7y0VFzynb8pcFPXcVKVHuAWWjCdXj_HfXWiAxw8yvyRspaSktbqm1sPTTV0rAFElyJ-HkNQD5REbhzAAYi11Io5OCmk_lCoptzcbaOzHBr5pJGB-Riy1Es4wwJNhGZYa4jMv2SE6xwJ10RkVbCX6qFadvCiVSmZjNy3tY5mwXHQTTB9GXGb4gmCYWA9nEy8PzG9ig478u7azt55EPr_MxalshA8CTI-GSfQt-rcRMZdycIzyLJekTkhQ9objXxrKvqg.Q6Fo_n7d3Ok0Cwe04Dmf5p285MqVNVPhZAutOpkcGFc&dib_tag=se&keywords=knee%2Bsleeve&qid=1785341071&sprefix=knee%2Bsleev%2Caps%2C214&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1|
| flex sensor  | to record angles of knee bending | **Price** | https://www.amazon.com/Spectra-Symbol-Flex-Sensor-Variant/dp/B0D3FFWJZ9/ref=sr_1_2_sspa?crid=2YWQFG81RA8YQ&dib=eyJ2IjoiMSJ9.-xk5jWy9x9kEwqQM3ljrc09AjNjWfFZRHtnmFuVn6YenWtquzl26_jQjLDDJTAiP4ac-7T8FJIax2YS_sYIHd-PS4eXz2okzgh4Hq2gdmqoTkfGE9vrKGSfvHlK40sEWDcmzMJyHIL346Avnac09MNGgYJR7L-9IZRK1vOcxRlNJ3S_vsq_85iwrki6KjKqFYrNrC7cDuD3CO1p2eB-GlQ4wjJya4OqJCJmg8wQYQBE.2usDj0pbAUrVsQ3aeBj90yeiLSK8ou6l6kaNgwcZXWI&dib_tag=se&keywords=flex+sensor&qid=1785340994&sprefix=flex+sensor%2Caps%2C207&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1|

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
