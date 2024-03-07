# EXPERIMENT-NO--05-Distance measurement using Ultrasonic sensor

## AIM: 

To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 


![image](https://user-images.githubusercontent.com/36288975/166430594-5adb4ca9-5a42-4781-a7e6-7236b3766a85.png)

###FIGURE 02:
![WhatsApp Image 2024-03-07 at 11 36 06_fe9ce854](https://github.com/Jeecikasrina23013947/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/148515300/0418b8ba-4852-4d89-b9b3-d29d79ef944a)

![WhatsApp Image 2024-03-07 at 11 35 51_080179ad](https://github.com/Jeecikasrina23013947/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/148515300/3782808d-ac01-4d1d-a1e3-d8a95274c974)



### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 

```
const int trigPin = 10;
const int echoPin = 9;
int led1 = 11;//red
int led2 = 12;//green
long duration;
float distance=0;
void setup()
{
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(trigPin,OUTPUT);
  pinMode(echoPin , INPUT);
  Serial.begin(9600);
}

void loop()
{
  digitalWrite(trigPin,LOW);
  delay(20);
  digitalWrite(trigPin,HIGH);
  delay(20);
  digitalWrite(trigPin,LOW);
  duration = pulseIn(echoPin,HIGH);
  distance = duration * 0.034/2;
  Serial.print("Distance = ");
  Serial.print(distance);
  Serial.println(" cm");
  
  if(distance >20){
    digitalWrite(led2,LOW);
  	digitalWrite(led1,HIGH);
    delay(300);
    digitalWrite(led1,LOW);
    delay(300);
  }
  else{
    digitalWrite(led1,LOW);
  	digitalWrite(led2,HIGH);
    delay(300);
    digitalWrite(led2,LOW);
    delay(300);
  }
  
}

```



### Distance vs measurement table 

![WhatsApp Image 2024-03-07 at 11 30 49_9f2dcc8e](https://github.com/Jeecikasrina23013947/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/148515300/4a3e5a29-b7ba-40e1-88ec-8733ea46f97b)


![robo 4](https://github.com/Jeecikasrina23013947/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/148515300/7e4faa9a-58b0-4149-8bd4-a2eed2404e3f)
			
			Average error = sum/ number of readings 
 

### RESULTS

An ultrasonic pair and measure the distance in centimeters,calculate the error are executed successfully

 
