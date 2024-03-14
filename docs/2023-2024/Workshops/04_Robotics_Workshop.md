![Shape46](RackMultipart20240211-1-8xy322_html_c969fc200ee27390.gif)

**WORKSHOP MANUAL**

**BASICS OF ARDUINO**

Arduino programs are written in the Arduino Integrated Development Environment (IDE). Arduino IDE is a special software running on your system that allows you to write sketches (synonym for program in Arduino language) for different Arduino boards. The Arduino programming language is based on a very simple hardware programming language called processing, which is similar to the C language. After the sketch is written in the Arduino IDE, it should be uploaded on the Arduino board for execution.

![Shape1](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape2](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)The first step in programming the Arduino board is downloading and installing the Arduino IDE. The open-source Arduino IDE runs on Windows, Mac OS X, and Linux. Download the Arduino software (depending on your OS) from the official website and follow the instructions to install.

**STEPS TO WORK IN ARDUINO IDE:**

Step 1 − Download Arduino IDE Software.

You can get different versions of Arduino IDE from the[Download page](https://www.arduino.cc/en/Main/Software) on the Arduino Official website.

Step 2 − Power up your board using standard USB cable

The Arduino Uno, Mega, Duemilanove and Arduino Nano automatically draw power from either, the USB connection to the computer or an external power supply. Connect the Arduino board to your computer using the USB cable. The green power LED (labeled PWR) should glow.Arduino needs 5V power supply.

![](RackMultipart20240211-1-8xy322_html_67dcc6f2d708ea34.jpg)

Step 3 − Launch Arduino IDE.

After your Arduino IDE software is downloaded, you need to unzip the folder.

Inside the folder, you can find the application icon with an infinity label (application.exe). Double-click the icon to start the IDE.

![Shape3](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape4](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif) ![](RackMultipart20240211-1-8xy322_html_e8918fe336c5aa2d.jpg)

Step 4 To create a new project, select File → New.

![](RackMultipart20240211-1-8xy322_html_34afa99748d1935b.jpg)

Step 6 − Select your Arduino board.

![Shape5](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape6](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)To avoid any error while uploading your program to the board, you must select the correct Arduino board name, which matches with the board connected to your computer.

Go to Tools → Board and select your board.

![](RackMultipart20240211-1-8xy322_html_543d613df7803d81.jpg)

Step 7 − Select your serial port.

Select the serial device of the Arduino board. Go to Tools → Serial Port menu. This is likely to be COM3 or higher (COM1 and COM2 are usually reserved for hardware serial ports). To find out, you can disconnect your Arduino board and reopen the menu, the entry that disappears should be of the Arduino board.

Reconnect the board and select that serial port.

![Shape7](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape8](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif) ![](RackMultipart20240211-1-8xy322_html_8701f2fe2a78ca3a.jpg)

**Step 8 − Upload the program to your board.**

Before explaining how we can upload our program to the board, we must demonstrate the function of each symbol appearing in the Arduino IDE toolbar.

![](RackMultipart20240211-1-8xy322_html_31c05e9631c816ee.jpg)

1. − Used to check if there is any compilation error.
2. − Used to upload a program to the Arduino board.
3. − Shortcut used to create a new sketch.
4. − Used to directly open one of the example sketch.
5. − Used to save your sketch.
6. − Serial monitor used to receive serial data from the board and send the serial data to the board.

![Shape9](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape10](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)Now, simply click the "Upload" button in the environment. Wait a few seconds; you will see the RX and TX LEDs on the board, flashing. If the upload is successful, the message "Done uploading" will appear in the status bar.

Once the installation is done you can start creating a blank program which is

called as 'sketch' in Arduino. The structure of Arduino program is pretty simple.

Arduino programs have a minimum of 2 blocks, Preparation and Execution block.

Each block has a set of statements enclosed in curly braces:

void setup( )

{

statements-1;

.

.

.

statement-n;

} void loop ( )

{ statement-1;

.

.

.

![Shape11](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape12](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)statement-n;

}

Here, setup ( ) is the preparation block and loop ( ) is an execution block.The setup function is the first to execute when the program is executed, and this function is called only once. The setup function is used to initialize the pin modes and start serial communication. After the setup ( ) function is executed, the execution block runs next. The execution block hosts statements like reading inputs, triggering outputs, checking conditions etc.

In the above example loop ( ) function is a part of execution block. As the name suggests, the loop( ) function executes the set of statements (enclosed in curly braces) repeatedly.

**INTRODUCTION TO TINKERCAD**

1. Create a Tinkercad Account and Create a New Project

![](RackMultipart20240211-1-8xy322_html_da4fc1bd05c0c72d.png)

![Shape13](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape14](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)

1. Click join now and follow online instructions to create an account. Select Create a personal account.

**Create New Circuit project**

![](RackMultipart20240211-1-8xy322_html_55e8ed3933028400.png)

1. Select the Circuits option and _Create new_ Circuit.

![](RackMultipart20240211-1-8xy322_html_d6cfce62744f3c6f.png)

1. ![Shape15](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape16](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)This space is where we will place all the components. The components can be moved around, edited, and wired together.
2. This section holds all the components. Scroll down to access component types
3. Use this tab to rotate, delete, undo or redo. It also helps users to create and name labels for components.
4. This option helps you program Arduino, use serial monitor, start real time simulation, export code, and share your projects.

**Building the Circuit**

1. Place all the components as in the image above by selecting them from the components section on the right side. Click on the component to select and click again anywhere on the workspace to place.
2. Hover over the points of the module to know the output name and click it to start wiring the components.

1 ![](RackMultipart20240211-1-8xy322_html_b946f1d08ac7a467.jpg) 0.While wiring click to bend the wire

![](RackMultipart20240211-1-8xy322_html_864fd9ec205f4196.jpg)

11.Click on wire to select the wire color. This helps in differentiating between wire use. For example, 5v wire color is Red and for GND(Ground) wire color is Black.

12.Once all the wiring has been don click simulation to start the simulation

 ![Shape19](RackMultipart20240211-1-8xy322_html_d409d2f2be5a351.gif)

![Shape17](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape18](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)

13.Once wiring is complete, select the code option to start coding.

![Shape20](RackMultipart20240211-1-8xy322_html_488574c653300d5b.gif)

14.Use the Text option to write the code for this tutorial or use block coding.

![Shape21](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape22](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)

**EXERCISE 1:**

**SPEED CONTROL OF SERVO MOTOR**

**WHAT IS SERVO MOTOR:**

A servo motor consists of a small electric motor, a potentiometer, control electronics, and a gearbox. The position of the output shaft is constantly measured by the internal potentiometer and compared with the target position set by the controller -Arduino. The gearbox decreases the speed of the motor, which increases the torque at the output shaft.

![Shape23](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape24](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif) ![](RackMultipart20240211-1-8xy322_html_136ee3963f66ae6e.jpg)

**SERVO MOTOR SPECIFICATIONS :**

Operating speed: 0.12second/ 60degree ( 4.8V no load)

Stall Torque (4.8V): 17.5oz /in (1kg/cm)

Operating voltage: 3.0V~7.2V

Temperature range: -30 to +60

Dead band width: 7usec

**CONTROLLING A SERVO MOTOR:**

Servo motors are controlled by sending a PWM (pulse-width modulation) signal to the signal line of the servo. The width of the pulses determines the position of the output shaft. When a signal with a pulse width of 1.5 milliseconds (ms)is sent , the servo will move to the neutral position (90 degrees). The min (0 degrees) and max (180 degrees) position typically correspond to a pulse width of 1 ms and 2 ms respectively.

![](RackMultipart20240211-1-8xy322_html_9893edf42deef624.png)

![Shape25](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape26](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)

**RUN 1:**

**TINKERCAD/ARDUINO CIRCUIT DIAGRAM:**

![](RackMultipart20240211-1-8xy322_html_6e8b41dba848074b.jpg)

**WIRING TABLE:**

| **Servo motor** | **Arduino** |
| --- | --- |
| Power(red) | 5V |
| Ground(black or white) | GND |
| Signal(yellow, orange or white) | Pin 9 |

**ARDUINO CODE:**

_/\* Servo motor with Arduino example code. Position and sweep. More info:_

_https://www.makerguides.com/ \*/_

_// Include the servo library:_

![Shape27](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape28](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)_#include \<Servo.h\>_

_// Create a new servo object:_

_Servo myservo;_

_// Define the servo pin:_

_#define servoPin 9_

_// Create a variable to store the servo position:_

_int angle = 0;_

_void setup() {_

_// Attach the Servo variable to a pin:_

_myservo.attach(servoPin);_

_}_

_void loop() {_

_// Tell the servo to go to a particular angle:_

_myservo.write(90); delay(1000); myservo.write(180); delay(1000); myservo.write(0);_

_delay(1000);_

_// Sweep from 0 to 180 degrees: for (angle = 0; angle \<= 180; angle += 1) { myservo.write(angle);_

_delay(15);_

_}_

_// And back from 180 to 0 degrees: for (angle = 180; angle \>= 0; angle -= 1) { myservo.write(angle);_

_delay(30);_

![Shape29](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape30](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)_}_

_delay(1000); }_

**RUN 2:**

**POSITION CONTROL OF SERVOMOTOR WITH POTENTIOMETER**

In this example, we will use the potentiometer to control the servo motor position. The original idea is that when we change the potentiometer value, the Arduino will reference this value and drive the motor to the desired position.

**TINKERCAD/ARDUINO CIRCUIT DIAGRAM:**

![Shape31](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape32](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)

![](RackMultipart20240211-1-8xy322_html_4151c1c1cf8fa51.jpg)

**WIRING TABLE:**

| **Servo motor** | **Arduino** |
| --- | --- |
| Power(red) | 5V |
| Ground(black or white) | GND |
| Signal(yellow,orange or white) | Pin 9 |
| **Potentiometer** | **Arduino** |
| Middle pin | A0 |
| Other two pins | 5V and GND (any order) |

**ARDUINO CODE:**

_#include \<Servo.h\> // include the required Arduino library_

_Servo myservo; // create a new object of the servo class_

_int angle = 0; // variable to store the servo position in degrees __int reading = 0; // variable to store the reading from the analog input__ void setup() {_ _myservo.attach(9); // Pin 9 of arduino connect to control wire of servo motor__}_

![Shape33](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape34](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)_void loop() {_ _reading = analogRead(A0); // A0 is the pin to read the analog input from the potentiometer_ _angle = map(reading, 0, 1023, 0, 180); // map the input to a value between 0 and 180 degrees_ _myservo.write(angle); // tell the servo to go to the set position_ _delay(15); // wait 15 ms for the servo to reach the position_

_}_

**EXERCISE 2 :**

| **OBSTACLE DETECTION USING ULTRASONIC SENSOR HC-SR04**** BUZZER AND LED** |
| --- |

**ULTRASONIC SENSOR HC-SR04 OVERVIEW:**

![Shape35](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape36](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)The HC-SR04 is an affordable and easy to use distance measuring sensor which has a range from 2cm to 400cm (about an inch to 13 feet). The sensor is composed of two ultrasonic transducers. One is transmitter which outputs ultrasonic sound pulses and the other is receiver which listens for reflected waves. It's basically a sonar which is used in submarines for detecting underwater objects.

![](RackMultipart20240211-1-8xy322_html_f6864bb0bc2c29c3.jpg)

**Specification of HC-SR04:**

| Operating Voltage | 5V DC |
| --- | --- |
| Operating Current | 15mA |
| Operating Frequency | 40KHz |
| Min Range | 2cm / 1 inch |
| Max Range | 400cm / 13 feet |
| Accuracy | 3mm |
| Measuring Angle | \<15° |
| Dimension | 45 x 20 x 15mm
 |

**HC-SR04 Ultrasonic Sensor Pinout**

Here's the pinout of the sensor:

![Shape37](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape38](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif) ![](RackMultipart20240211-1-8xy322_html_f11992f6c7508dbe.jpg)

The sensor has 4 pins. _ **VCC** _ and _ **GND** _ go to _ **5V** _ and _ **GND** _ pins on the Arduino, and the _ **Trig** _ and _ **Echo** _ go to any digital Arduino pin. Using the _ **Trig** _ pin we send the ultrasound wave from the transmitter, and with the _ **Echo** _ pin we listen for the reflected signal.

**RUN1:**

![Shape39](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape40](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif) **HC-SR04 ULTRASONIC SENSOR WITH BUZZER AND LED:**

![](RackMultipart20240211-1-8xy322_html_b3ca770ad496a046.png)

**WIRING TABLE:**

| **Ultrasonic Sensor** | **Arduino** |
| --- | --- |
| Vcc | 5V |
| Trig | Pin 3 |
| Echo | Pin 2 |
| Gnd | GND |
| **Buzzer** | **Arduino** |
| + | 5V |
| - | Pin 7 |
| **(RGB) Led** | **Arduino** |
| Cathode (-) | GND |
| Anode (+) | Pin 6, 5, 4 through resistor |

**ARDUINO CODE:**

_const int echoPin=2, triggerPin=3, red=4, green=5, blue=6; const int buzz = 7; int pulseValue;_

_float distance;_

![Shape41](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape42](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)_void setup( ) { pinMode(echoPin, INPUT); pinMode(triggerPin, OUTPUT); pinMode(red, OUTPUT); pinMode(green, OUTPUT); pinMode(blue, OUTPUT); pinMode(buzz, OUTPUT);_

_Serial.begin(9600);_

_}_

_void loop( )_

_{_

_digitalWrite(triggerPin, LOW); delayMicroseconds(5); digitalWrite(triggerPin, HIGH); delayMicroseconds(10); pulseValue=pulseIn(echoPin, HIGH); distance=(pulseValue\*0.0001657\*39.37); if (distance\<=5)_

_{ digitalWrite(red, HIGH); digitalWrite(green, LOW); digitalWrite(blue, LOW); tone(buzz, 500);_

_}_

_else if (distance\<=10)_

_{_

_digitalWrite(green, HIGH); digitalWrite(red, LOW); digitalWrite(blue, LOW);_

![Shape43](RackMultipart20240211-1-8xy322_html_28f7477457fd8f25.gif) ![Shape44](RackMultipart20240211-1-8xy322_html_98b2bdffd4558bb.gif)_tone(buzz, 1000);_

_}_

_else_

_{ digitalWrite(blue, HIGH); digitalWrite(red, LOW); digitalWrite(green, LOW);_

_tone(buzz, 1500);_

_}_

_Serial.print(distance); Serial.println(" inch/es");_

_delay(500);_

![Shape48](RackMultipart20240211-1-8xy322_html_8b0c7f27ae1abaf9.gif)