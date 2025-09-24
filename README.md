## Hi there, we are ibn roshd max
Here is the YouTube video link for our robot → \[[(https://youtu.be/F4-R_nkTTqw?si=RATRviskS9dbDN2P)\]

and this fore the obstcale round : https://youtu.be/KA0iE_iIY_Y?si=s2kVDWvs9qxOMXv2

------------------------------------------------------------------------

## Strategy of the Robot in Gameplay

At the start, the robot relies on computer vision processed by the
*Jetson Nano* to detect cubes on the field. The Jetson Nano applies
ROI (Region of Interest) to separate the cubes from each other,
calculate their relative distances, and decide which cube to approach.
The robot always prioritizes avoiding the closest cube rather than
moving toward the farther ones.

The *Arduino Nano* works as the low-level controller. It receives
processed signals from the Jetson Nano and converts them into commands
for the motors and servos. Additionally, the Arduino Nano sends gyro
angle data back to the Jetson Nano to improve navigation accuracy. It
also triggers a buzzer to provide sound feedback during operation.

With the help of *DF Ultrasonic sensors* placed around the robot, we
can detect obstacles in 360 degrees and avoid collisions at corners,
while also ensuring the robot can stop and leave the starting area
safely.

The rear *differential mechanism* allows the wheels to rotate
smoothly, making the robot's turns sharper and more stable. Combined
with servo motors for steering, the robot achieves precise movements
while navigating the field.

------------------------------------------------------------------------

## How to Use Arduino Nano

We programmed the Arduino Nano using the Arduino IDE. The Arduino
receives serial data from the Jetson Nano and translates it into PWM
signals for DC motors and servo motors. The connection is established
via USB or serial pins, and the board communicates bidirectionally with
the Jetson Nano.

------------------------------------------------------------------------

## Robot Components

### 1. Jetson Nano

The Jetson Nano is the high-level controller of the robot. It processes
the video feed from the CSI camera, applies image recognition, detects
cubes, and calculates their distances. Using ROI (Region of Interest),
the Jetson Nano identifies each cube individually and decides which path
to follow while avoiding the closest obstacles.

*Specifications:*\
•⁠  ⁠CPU: Quad-core ARM Cortex-A57\
•⁠  ⁠GPU: 128-core NVIDIA Maxwell\
•⁠  ⁠RAM: 4GB\
•⁠  ⁠Camera Interface: CSI-2\
•⁠  ⁠Connectivity: GPIO, I2C, SPI, UART

------------------------------------------------------------------------

### 2. Arduino Nano

The Arduino Nano serves as the low-level controller. It receives
instructions from the Jetson Nano and controls:\
•⁠  ⁠DC motors for movement\
•⁠  ⁠Servo motors for steering\
•⁠  ⁠A buzzer for sound alerts

It also reads the *gyro sensor* and sends angular data back to the
Jetson Nano for accurate orientation.

------------------------------------------------------------------------

### 3. CSI Camera

The CSI camera provides live video input to the Jetson Nano. It is
lightweight, compact, and designed for fast frame capture, making it
ideal for real-time image processing in robotics.

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
