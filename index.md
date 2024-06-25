<div style="text-align: center;">
  <h1>Wrist Rehabilitation Device</h1>
</div>
My Wrist Rehabilitation Device uses sensors to monitor the angle of the wrist and beeps when the wrist bends too far. It uses an arduino, a gyroscope and accelerometer, and a flex sensor. It has a Bluetooth module which allows it to transmit data to the user's computer without the arduino being plugged in. This could be used to prevent and help with carpal tunnel syndrome, or other wrist pains caused by bad posture. 



| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Mikul R | Saratoga High School | Mechanical Engineering | Incoming Sophomore |


<p> </p>
<div style="text-align: center;">
  <img src="headshot.jpg" alt="me!" width="600">
</div>
<!--
<div style="text-align: center;">
	<h1>Final Milestone</h1>
</div>
--
<div style="text-align: center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/QK945fm57Vw?si=AxlBLNpQ3TZcoUxB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
<div style="text-align: center;">
  <h1>Second Milestone</h1>
</div>
--
<div style="text-align: center;">
  <h3>Milestone 2 Schematic</h3>
</div>
<div style="text-align: center;">
  <img src="Milestone 2 Schematic.png" alt="Schematic" width="600">
</div>
--
For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE
-->
<div style="text-align: center;">
  <h1>Third Milestone</h1>
</div>
<div style="text-align: center;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/uWUC-9JCDNA?si=ks31A9qE4YFSu6tZ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
<p>My wrist sleeve uses a combination of its accelerometer and flex sensor values to determine whether a wrist position is in a bad position and whether to rotate it up or down to get to the correct position. 
</p>
<div style="text-align: center;">
  <img src="unnamed (2).jpg" alt="Picture of Wrist Sleeve with all components" width="680">
</div>
<p>The piezo buzzer beeps as the 4.5” flex sensor or the accelerometer, which is part of a module which additionally includes a gyroscope and magnetometer are past certain values. I decided to only use the accelerometer out of these 3 because the gyroscope, which measures angular velocity, and the magnetometer, which measures magnetic fields acting similar to a compass, didn’t show variability in their values as I moved the module which meant they wouldn’t be very helpful. With the accelerometer which measures acceleration however, I was able to recognize a significant difference as I moved the module
</p>
<p>The Hc-05 bluetooth module allows for serial bluetooth connection from the arduino to the computer which allows for the arduino to transmit data without being directly plugged into the computer. The bluetooth module has a RX and TX pin which connects to the other in the arduino. This is because because the labels are relative to the device itself. This means that one device's TX line transmits to the other device's RX line, and vice versa.
</p>
<p>The proto board allowed for the circuit to easily be transferred from the breadboard because each individual hole is connected by copper in the same pattern as a breadboard where each row is conductive. Below, the breadboard is on the left while the proto board is on the right.
</p>
<div style="text-align: center;">
	<img width="400" alt="image" src="https://github.com/MikulRana/Wrist-Rehabilitation-Device/assets/76714516/625c56c2-07f4-4f4e-92d7-b51b73d4359c">
</div>
<p>One challenge I faced was that as I sewed the proto board onto the sleeve, the leftover wire poked through it and make wearing the sleeve very uncomfortable. To fix this, I had to trim the excess wire and add some neoprene padding. 
</p>
<p>Another challenge I faced was at the end of the project when I thought I finished, the pins on my flex sensor broke off. To fix this, I had to attach pin headers to the flex sensor which was hard because the pin headers were hard to hold in place because of how small they are. Eventually I soldered the pins onto the sensor and onto the proto board and my flex sensor started working like normal.</p>
<p>Next I will add some modifications to my project, including a mechanism which would amplify weaker movements, allowing for easier wrist movement for people with wrist impairing disabilities. 
</p>
<div style="text-align: center;">
  <h1>Second Milestone</h1>
</div>
<div style="text-align: center;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/uWUC-9JCDNA?si=ks31A9qE4YFSu6tZ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
<div style="text-align: center;">
  <h3>Milestone 2 Schematic</h3>
</div>
<div style="text-align: center;">
  <img src="Milestone 2 Schematic.png" alt="Schematic" width="600">
</div>
<p>  I first added the LSM6DS3 + LIS3MDL module to my circuit, which includes a gyroscope, accelerometer, and magnetometer. Out of these 3 sensors, I had to determine which one of those would best be suited for the purpose of my wrist device. I originally thought the gyroscope would be the best to use, but as I printed the values, I realized the accelerometer values were the ones changing as I turned the module, so I decided to use those. The accelerometer measures the acceleration of the module as the name suggests while the gyroscope measures the rate of rotation, or angular velocity, of an object. Since the movement is relatively slow, the measured angular velocity might have been below the sensitivity threshold of the gyroscope, causing it to report small values which weren’t very helpful. The accelerometer was able to quantify the movement of the module to bigger numbers which would help more in this context. In the snippets of the serial monitor below, you can compare the outputs of the accelerometer and the gyroscope to see that the accelerometer values displayed more. 
</p>
```c++
			x	  y		  z
		Accel 0.1878 	 1.3196 	 10.1683 	m/s^2 
		Accel 0.0108 	 0.9870 	 9.9805 	m/s^2 
		Accel -0.2130 	 -0.2429 	 10.1061 	m/s^2 
		Accel -1.3304 	 -0.0778 	 10.0223 	m/s^2 
		Accel -2.5137 	 -0.1687 	 9.8644 	m/s^2 
		Accel -2.8869 	 -0.1376 	 9.8309 	m/s^2 
		Accel -3.6203 	 -0.0299 	 9.4397 	m/s^2 
		Accel -4.7677 	 -0.0287 	 9.0078 	m/s^2 
		Accel -3.9852 	 0.1101 	 9.2554 	m/s^2 
		Accel 0.0359 	 0.0359 	 10.4136 	m/s^2 
		Accel -1.7420 	 0.5073 	 10.2233 	m/s^2 

```
```c++
			x	  y		  z
		Gyro 0.0269 	 -0.0061 	 -0.0037 	radians/s 
		Gyro 0.1222 	 0.0648 	 0.0208 	radians/s 
		Gyro -0.1100 	 0.0696 	 -0.0977 	radians/s 
		Gyro 0.1356 	 0.2443 	 0.0269 	radians/s 
		Gyro 0.0660 	 0.0159 	 0.0428 	radians/s 
		Gyro -0.0220 	 0.0220 	 0.0342 	radians/s 
		Gyro 0.0281 	 -0.0269 	 0.0110 	radians/s 
		Gyro -0.2957 	 -0.8015 	 0.1356 	radians/s 

```
<p>Above we can see that none of the values have noticable differences</p>
<p>  I also added a piezo buzzer. Piezo buzzers work by applying an alternating voltage to a piezoelectric ceramic material, which causes the material to vibrate rapidly and produce sound waves. A piezo buzzer needs a resistor to reset the voltage when the switch is open, which is why I added a 100 ohm resistor to the circuit. 
</p>

<p>  The Bluetooth module is called the HC-05, and I was using it to wirelessly transmit data from the arduino to my computer. 2 of the pins on the module, the RX and TX, are the serial communication pins. These have to be connected to the opposite pin on the arduino, so the RX has to go to the TX port and the TX has to go to the RX port. This is because the labels refer to the device itself, not the other device it's connected to.
</p>

<p>  One challenge I faced was with the Bluetooth module where it wasn’t connecting to my computer and the arduino. I realized in my settings, I had to turn on advanced Bluetooth search so that the HC-05 module showed up because the default mode only displays common devices like headphones, printers, etc. 
</p>
<p>  Another challenge was connecting the accelerometer module to the breadboard because the breadboard pins it came with weren’t conducting the power well and the gyroscope wasn’t consistently on. To fix this, I tried to put the wires through the module itself into the breadboard, but even that didn't work. I concluded that there was probably a faulty connection within the breadboard, so I put the module on its own with the jumper wires touching the connection holes.
</p>

<p>  The next steps of my project are to solder the components onto a pcb board instead of the breadboard so it could be put on the wrist sleeve, and connect everything to the wrist sleeve. After everything, I will test and debug to make sure my project is finished successfully. </p>

<div style="text-align: center;">
  <h1>First Milestone</h1>
</div>
<div style="text-align: center;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/4qdVO-jCbHY?si=K4MMR2H-8GmGsBDG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
<p>  My first step forward was to work on the flex sensor portion of my schematic as well as coding the flex sensor to print out its values and figure out when the angle is a bad angle. The ideal wrist angle is 20 degrees or less, but since the flex sensor has some variability, I set the limit to 18 degrees. This was challenging because a flex sensor is actually a resistor, so the output of the sensor is a resistance value. Because of this, there had to be an algorithm which converts the resistance recorded to an angle.</p>
![Headstone Image](FlexSensorSchematic.png)
<p>  One challenge I faced was not seeing values in the output tab. Initially, I thought there was an issue with my code and referenced online sources, but my code appeared correct. I then realized I needed to open the Serial Monitor in Arduino IDE, as the output tab is for code outputs, while the Serial Monitor displays data transmitted from the Arduino.
</p>
<p>  Another problem was that the angle values read -35 degrees when the wrist was straight, instead of 0 degrees. I discovered the resistance value I defined for the resistor in my circuit was incorrect. After researching the resistor's possible resistance range and using a multimeter, I determined the exact value. I also used the color-coded bands on the resistor to confirm the precise resistance</p>
<p>  The next step for me is to wire up the remaining components like the accelerometer, gyroscope, and buzzer. I will also try to connect the Bluetooth module and send sensor data to the computer through that. </p>

<p>  Below is my code that I have completed so far. So far it calculates the angle of the flex sensor, while also setting a limit to the angle:</p>
```c++
const int FLEX_PIN = A0; // Pin connected to voltage divider output

const float VCC = 4.98; // Measured voltage of Ardunio 5V line
const float R_DIV = 10000.0; // Measured resistance of resistor
const float STRAIGHT_RESISTANCE = 15000.0; // resistance when straight
const float BEND_RESISTANCE = 70000.0; // resistance at 90 deg
void setup() {
  Serial.begin(9600);
  pinMode(FLEX_PIN, INPUT);
}
void loop() {
  // Read the ADC, and calculate voltage and resistance from it
  int flexADC = analogRead(FLEX_PIN);
  float flexV = flexADC * VCC / 1023.0;
  float flexR = R_DIV * (VCC / flexV - 1.0);
  // Use the calculated resistance to estimate the sensor's bend angle:
  float angle = map(flexR, STRAIGHT_RESISTANCE, BEND_RESISTANCE,
                   0, 90.0);
  Serial.println("Bend: " + (String(angle)) + " degrees");
  Serial.println();
  if ((angle) > 15) {
    Serial.println("BAD");
  }
  delay(1000);

}

```


<p>Below is what is displayed in the serial monitor in Arduino IDE from the above code. When the degree values become greater than or equal to 15, then the code displays "BAD", but later this will translate to a beep</p>
<img src="datasc.png" alt="data shown in the serial monitor" width="600">

![Headstone Image](datasc.png)

<div style="text-align: center;">
	<h1>Final Schematic</h1>
</div>

![image](https://github.com/MikulRana/Wrist-Rehabilitation-Device/assets/76714516/ece26785-a63a-4cec-962c-fd3eee20ec1a)


<div style="text-align: center;">
	<h1>Final Code</h1>
</div>

```c++
#include <Adafruit_LSM6DS3TRC.h>
Adafruit_LSM6DS3TRC lsm6ds;
#include <SoftwareSerial.h>
SoftwareSerial Bluetooth(3, 4);
#include <Adafruit_LIS3MDL.h>
Adafruit_LIS3MDL lis3mdl;

#include <Arduino.h>
#include <Wire.h>

const int FLEX_PIN = A0; // Pin connected to voltage divider output
const int buzzer = 9; //buzzer to arduino pin 9
const float VCC = 5; // Measured voltage of Ardunio 5V line
const float R_DIV = 14000.0; // Measured resistance of resistor

const float STRAIGHT_RESISTANCE = 30000.0; // resistance when straight
const float BEND_RESISTANCE = 70000.0; // resistance at 90 deg

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  bool lsm6ds_success, lis3mdl_success;

  // hardware I2C mode, can pass in address & alt Wire

  lsm6ds_success = lsm6ds.begin_I2C();
  lis3mdl_success = lis3mdl.begin_I2C();
  Serial.print("Accelerometer range set to: ");
  switch (lsm6ds.getAccelRange()) {
  case LSM6DS_ACCEL_RANGE_2_G:
    Serial.println("+-2G");
    break;
  case LSM6DS_ACCEL_RANGE_4_G:
    Serial.println("+-4G");
    break;
  case LSM6DS_ACCEL_RANGE_8_G:
    Serial.println("+-8G");
    break;
  case LSM6DS_ACCEL_RANGE_16_G:
    Serial.println("+-16G");
    break;
  }

  // lsm6ds.setAccelDataRate(LSM6DS_RATE_12_5_HZ);
  Serial.print("Accelerometer data rate set to: ");
  switch (lsm6ds.getAccelDataRate()) {
  case LSM6DS_RATE_SHUTDOWN:
    Serial.println("0 Hz");
    break;
  case LSM6DS_RATE_12_5_HZ:
    Serial.println("12.5 Hz");
    break;
  case LSM6DS_RATE_26_HZ:
    Serial.println("26 Hz");
    break;
  case LSM6DS_RATE_52_HZ:
    Serial.println("52 Hz");
    break;
  case LSM6DS_RATE_104_HZ:
    Serial.println("104 Hz");
    break;
  case LSM6DS_RATE_208_HZ:
    Serial.println("208 Hz");
    break;
  case LSM6DS_RATE_416_HZ:
    Serial.println("416 Hz");
    break;
  case LSM6DS_RATE_833_HZ:
    Serial.println("833 Hz");
    break;
  case LSM6DS_RATE_1_66K_HZ:
    Serial.println("1.66 KHz");
    break;
  case LSM6DS_RATE_3_33K_HZ:
    Serial.println("3.33 KHz");
    break;
  case LSM6DS_RATE_6_66K_HZ:
    Serial.println("6.66 KHz");
    break;
  }
  pinMode(FLEX_PIN, INPUT);
  pinMode(buzzer, OUTPUT); // Set buzzer - pin 9 as an output
}

void loop() {
  sensors_event_t accel, gyro, mag, temp;
  lsm6ds.getEvent(&accel, &gyro, &temp);
  lis3mdl.getEvent(&mag);

  int flexADC = analogRead(FLEX_PIN);
  float flexV = flexADC * VCC / 1023.0;
  float flexR = R_DIV * (VCC / flexV - 1.0);
  float angle = map(flexR, STRAIGHT_RESISTANCE, BEND_RESISTANCE, 0, 90.0);

  bool goodForm = (accel.acceleration.x <= 2.5) && ((angle < 15 ) && (angle > -5));
  bool badFormUp = (accel.acceleration.x > 2.5) || (angle >= 15);
  bool badFormDown = (angle <= -5);

  Serial.print("Accelerometer X Value: ");
  Serial.println(accel.acceleration.x, 4);
  Serial.print("Bend: ");
  Serial.print(angle);
  Serial.println(" degrees");

  if (goodForm) {
    Serial.println("Good form");
    noTone(buzzer);
  } else {
    Serial.println("Bad form");
    if (badFormUp) {
      Serial.println("Turn wrist up");
    }
    if (badFormDown) {
      Serial.println("Turn wrist down");
    }
    tone(buzzer, 8000);
  }

  delay(1000);
}

```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino Uno Rev3 | Microcontroller which everything connects to and contains all the code | $27.60 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| HC-05 Bluetooth Module | Wireless communication with the computer | $10.39 | <a href="https://www.amazon.com/HiLetgo-Wireless-Bluetooth-Transceiver-Arduino/dp/B071YJG8DR/"> Link </a> |
| Adafruit LSM6DS3TR-C + LIS3MDL - Precision 9 DoF IMU | Gyroscope, Accelerometer, and Magnetometer | $19.95 | <a href="https://www.adafruit.com/product/5543?gad_source=1&gclid=Cj0KCQjw4MSzBhC8ARIsAPFOuyW3bKrwhMSo2VoSfvSt319uDnnbDld4MoYm0IzXAV2mbivYMjEGez4aApeGEALw_wcB"> Link </a> |
| Flex Sensor (4.5") | Measures tilt of wrist in degrees | $17.95 | <a href="https://www.sparkfun.com/products/8606"> Link </a> |




# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)


<div style="text-align: center;">
  <h1>Starter Project - Calculator</h1>
</div>
<div style="text-align: center;">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/wXEsTbNK6yc?si=MvtolE11zvuNi826" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
<p>My starter project was the calculator, and I chose this project because it seemed like a fun project and it required a lot of soldering which I wanted to practice. The calculator has 17 buttons with 4 functions: 1) addition, 2) subtraction, 3) multiplication, and 4) division. Another button on the calculator, the On/Clear button, turns on the calculator, and while the calculator is on, if pressed again, the numbers displayed on the LED (Light Emitting Diode) display are cleared. All these buttons are soldered down along with a 7 segment 6 digit LED digital display tube. Each digit is formed by 7 different LED segments, which individually light up and turn off to display different numbers. The component near the top of the calculator is an Integrated Circuit which has an Arithmetic Logic Unit (ALU), a digital circuit used to perform arithmetic and logic operations.</p>
<p>One challenge I faced was that the LED display only was showing 2 and wasn't allowing me to press any other buttons. After debugging, I found out that the button was stuck on the frame, and after I release it, the calculator worked perfectly. From this project, I improved my soldering skills while also learning how to debug properly. I will apply everything I learned so far on my main project, the Wrist Rehabilitation Monitor.</p>
