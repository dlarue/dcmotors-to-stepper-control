# dcmotors-to-stepper-control
This Arduino program is refered from: https://github.com/tuenhidiy/CNC-PLOTTER-FROM-DC-MOTORS-AND-OPTICAL-ENCODERS

It is used to control 2 DC motors having 2 optical encoders with step / direction signals typically found as stepper driver inputs on CNC machines.
In this project, DC motors can be simulated as same as stepper motors and we can control them via GRBL firmware for CNC application.
Combined with a GRBL based Arduino, a 3 axis CNC plotter/painter can be built from 2 DC motors w/encoders and a servo to operate as the Z axis.

Inspired by this DIY wall painting bot with the hopes of having far more resolution capabilities and instead of using custom software for the workflow
be able to use commonly used CNC CAM software for GCode generation. 

https://www.instructables.com/3-AXIS-CNC-PLOTTER-FROM-DC-MOTORS-AND-OPTICAL-ENCO/

The firmware runs on an Arduino Mega 2560 as it uses 4 interrupts to handle step/direction input and encoder inputs.
The motors are driven by a L298N H-bridge contolling each channels via "ENA,IN1,IN2,IN3,IN4,ENB" inputs(outputs on the Arduino).
Motor encoder outputs are also connected directly to the Arduino Mega.

Installation:
clone this repository to your computer. Extract the utility.rar contents into your local repository preserving the directory structure. In your Arduino IDE library add the L298N library by Andrea Lombardo( https://github.com/AndreaLombardo/L298N ). Compile and upload.

Arduino Pin	->	signal name

3		->	L298N-ENA

5		->	L298N-IN2

6		->	L298N-IN1

7		->	L298N-IN3

8		->	L298N-IN4

9		->	L298N-ENB

18		<-	MotorX-Encoder-chanA	(interrupt)

19		<-	MotorX-Step		(interrupt)

20		<-	MotorY-Encoder-chanA	(interrupt)

21		<-	MotorY-Step		(interrupt)

22		<-	MotorX-Encoder-chanB

23		<-	MotorX-Direction

24		<-	MotorY-Encoder-chanB

25		<-	MotorY-Direction



		
