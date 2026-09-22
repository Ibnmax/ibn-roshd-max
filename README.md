## Hi there, we are TEAM 7371
Here is the YouTube video link for our robot → \[[([https://youtu.be/F4-R_nkTTqw?si=RATRviskS9dbDN2P](https://youtu.be/d9VSKAYB4kY?feature=shared))\]

and this fore the obstcale round : [https://youtu.be/KA0iE_iIY_Y?si=s2kVDWvs9qxOMXv2](https://youtu.be/1VgxIUpCT7o?feature=shared)

------------------------------------------------------------------------

## Strategy of the Robot in Gameplay

At the start, the robot relies on computer vision processed by the HUSKYLENS 2 to detect field elements. The camera analyzes image geometry to recognize intersections and colored pillars, deciding when to initiate avoidance maneuvers based on visual proximity.
The Arduino Mega 2560 works as the central controller, managing a structured state machine. It receives vision data via UART and integrates it with gyro yaw feedback from the MPU6050 to ensure precise navigation. It then converts these inputs into commands for the drive and steering motors, while triggering a buzzer to provide sound feedback.
With the help of six URM09 ultrasonic sensors placed around the chassis, the robot monitors wall distances to prevent collisions, confirm corner turns, and execute a highly accurate final parking sequence safely.
The custom chassis features a front steering mechanism controlled by a servo motor. Combined with a rear geared DC motor and a Hall encoder for exact distance measurement, the robot achieves stable, precise movements while navigating the field.


------------------------------------------------------------------------

## How to Use Arduino mega 2560

We programmed the Arduino Nano using the Arduino IDE. The Arduino
receives serial data from the Jetson Nano and translates it into PWM
signals for DC motors and servo motors. The connection is established
via USB or serial pins, and the board communicates bidirectionally with
the Jetson Nano.

------------------------------------------------------------------------

## Robot Components

------------------------------------------------------------------------

### 1. Arduino Nano

The Arduino Nano serves as the low-level controller. It receives
instructions from the Jetson Nano and controls:\
•⁠  ⁠DC motors for movement\
•⁠  ⁠Servo motors for steering\
•⁠  ⁠A buzzer for sound alerts

It also reads the *gyro sensor* and sends angular data back to the
Jetson Nano for accurate orientation.

------------------------------------------------------------------------

### 3. HUSKYLENS 2

The HuskyLens 2 is an AI-powered machine vision sensor designed to act as both the "eyes and brain" for robotics and embedded systems.
 * Edge AI Processing: It independently analyzes images to recognize colors, objects, lines, and faces, taking the computational load off the main microcontroller.
 * Click-to-Learn Training: Using its built-in screen and buttons, it can learn to identify new objects or colors instantly without requiring external computers or complex programming.
 * Ready-to-Use Data: It transmits processed results (X, Y coordinates, width, height, and IDs) directly to controllers like Arduino via UART or I2C, making it highly efficient for autonomous tasks
for real-time image processing in robotics.

------------------------------------------------------------------------

### 4. Servo Motors

Servo motors allow the robot to rotate and adjust its steering angles
precisely. By controlling angular position, they help the robot maneuver
effectively around obstacles.

------------------------------------------------------------------------

### 5. Differential Mechanism

We implemented a rear differential that ensures smooth wheel rotation
and better cornering. This design provides the robot with sharper and
more stable turning capabilities.

------------------------------------------------------------------------

### 6. Voltage Regulator

The voltage regulator converts the battery's input voltage to 5V to
power the sensors and control units. This ensures stable operation of
sensitive components.

------------------------------------------------------------------------

### 7. Battery

The battery provides the main power source for the entire robot,
supplying both the Jetson Nano and the Arduino Nano as well as the
motors.

------------------------------------------------------------------------

### 8. DF Ultrasonic Sensors

Multiple *DF ultrasonic sensors* are installed around the robot to
achieve 360-degree obstacle detection. These sensors help prevent
collisions at corners and allow the robot to safely exit and re-enter
the starting area.

------------------------------------------------------------------------

### 9. 3D Printing

We used *Autodesk Inventor* to design the chassis and printed the
parts using a 3D printer. This includes the body, camera holders, and
sensor mounts.

------------------------------------------------------------------------

### 10. Laser Cutter

A laser cutting machine was used to cut acrylic sheets for structural
supports and stands that hold the robot's main components.

------------------------------------------------------------------------

## Source Code

All source codes are available in the ⁠ src ⁠ directory.
