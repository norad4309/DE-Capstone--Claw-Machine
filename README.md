# Nora Dunn- clawMachine - DE Final Capstone Project
## Project Overview

This project is a durable claw machine that was built using Arduino, servo, stepper motors, and a joystick. Specifically designed for elementary school students, we focused on making the build durable and user-friendly. Our goal is to donate it to an after school program at Los Peñasquitos Elementary School, BLAST, to provide students with a fun and interactive STEAM experience.

This claw machine is built around an Arduino Mega Board and controls multiple motors, a joystick, buttons, limit switches, and an LCD screen to deliver real-time feedback.

### Key Features:

- X/Y/Z gantry system with for precise claw movement
- Z direction pulley design for precise claw movement
- Servo-controlled claw for gripping objects
- Stepper motors for X/Y movement and high-torque, repeatable positioning
- Joystick and buttons for controlling movement of claw
- LCD display for messages such as “INSERT COIN” and “GAME OVER”
- Implemented safety features using limit switches to prevent over-travel
- Ultrasonic Sensors to sense the coin being inserted

## Engineering Design Process
1. Identify Problem (done)
2. Define Criteria & Constraints (done)
3. Research & Brainstorming (done)
4. Select a Solution (Decision Matrix) (done)
5. Build & Prototype (in progress)
6. Test & Iterate (in progress)
7. Final Solution (in progress)

## Bill of Materials

| Component              | Quantity | Notes / Source                                 |
|------------------------|----------|-----------------------------------------------|
| Arduino Mega 2560      | 1        | Needed for sufficient I/O pins               |
| 16x2 LCD Screen        | 1        | Displays messages to user                     |
| NEMA 17 Stepper Motors | 4        | 2 for Y-axis, 1 X-axis, 1 Z-axis             |
| Servo Motor            | 1        | Controls claw grip                            |
| Joystick               | 1        | Controls X/Y gantry                           |
| Buttons                | 3       | Start, coin, Z-axis control                   |
| Limit Switches         | 3       | For X/Y/Z travel limits                       |
| TIP-120 Transistors    | 18       | Control motor power safely                    |
| Resistors              | 18       | For transistor bases                           |
| Breadboard & Jumper Wires | N/A   | For testbed and prototyping                   |
| Power Supply           | N/A      | 5V logic for Arduino, separate motor supply  |

*Most of the important stuff is here, smaller parts such as screws aren't documented.*


| Component              | Quantity | Notes / Source                                 |
|------------------------|----------|-----------------------------------------------|
| Arduino Mega 2560      | 1        | Needed for sufficient I/O pins               |
| 16x2 LCD Screen        | 1        | Displays messages to user                     |
| NEMA 17 Stepper Motors | 4        | 2 for Y-axis, 1 X-axis, 1 Z-axis             |
| Servo Motor            | 1        | Controls claw grip                            |
| Joystick               | 1        | Controls X/Y gantry                           |
| Buttons                | 3       | Start, coin, Z-axis control                   |
| Limit Switches         | 3       | For X/Y/Z travel limits                       |
| TIP-120 Transistors    | 18       | Control motor power safely                    |
| Resistors              | 18       | For transistor bases                           |
| Breadboard & Jumper Wires | N/A   | For testbed and prototyping                   |
| Power Supply           | N/A      | 5V logic for Arduino, separate motor supply  |
| Motor Driver           | 5      | 4 for Stepper motors and 1 for Servo motor, controls the speed, direction, and torque  |
| Potentiometer           | 1      | Controls the voltage supply to the motor  |

*Additional smaller electrical components and screws were used for the assembly but not documented* 

## Motor & Component Testing
All motors and components were tested individually before integration:

| Component      | Test Summary          | Observations                                      |
|----------------|---------------------|--------------------------------------------------|
| Servo Motor    | Potentiometer control | Smooth motion, precise positioning, limited torque |
| Stepper Motor  | Step-based control    | High torque, precise positioning, slower for continuous motion |
| Joystick       | Analog X/Y           | Controlled gantry axes successfully             |
| Limit Switches | Digital input        | Effectively stops motion and prevents over-travel |

*Test codes are in the `Code` folder.*

**Note:**  We chose to use stepper motors for the X and Y axes due to their precise step-based positioning, while we chose a servo motor for the claw to provide controlled angular motion for gripp

## Assembly Plan
1. Create the CAD design of the claw machine on Fusion360
2. Build testbed for individual components (Arduino Uno (for initial testing), motors, joystick, switches, etc)
3. Assemble X/YZ gantry system and mount motors
4. Assemble Claw using pulley design for Z-Axis
5. Wire motors through TIP-120 transistors to Arduino Mega 
6. Connect all electrical components (limit switches, joystick, buttons, LCD Screen, etc.)
7. Verify shared ground connections and separate motor power supply
8. Upload Arduino code and test individual subsystems
9. Integrate all code and run full test
10. If not initially, troubleshoot until successful

## Gantry Decision Matrix
Note: We're currently still finalizing the gantry plan. We're leaning towards a Cartesian Gantry with T-slots or linear-rods. This is our decision matrix between possible gantry types: 

**Rating Scale:**  
1 = Poor / Very Difficult  
5 = Excellent / Ideal  

| Gantry Type | Mechanical Simplicity | Precision | Safety for Kids | Ease of Control (Code) | **Total ( /25 )** |
|------------|----------------------|-----------|------------------|------------------------|------------------|
| Cartesian (X/Y/Z) | 5 | 5 | 5 | 5 | **20** |
| CoreXY | 2 | 5 | 2 | 2 | 11 |
| H-Bot | 3 | 3 | 3 | 3 | 12 |
| Polar (Rotational + Radial) | 3 | 3 | 2 | 3 | 11 |
| Cable-Driven | 2 | 2 | 2 | 2 | 8 |
| SCARA Arm | 1 | 3 | 1 | 1 | 6 |


## CAD Design
We designed the internal and external layout of the claw machine in CAD to ensure all components would fit properly and the machine would be structurally sound.

Below is the CAD model of the structure:
<img width="490" height="539" alt="Screenshot 2026-01-16 at 5 00 43 AM" src="https://github.com/user-attachments/assets/395d9ddc-7bd5-46a3-a5b1-cc5b86861f99" />

## Wiring Diagram
<img width="623" height="458" alt="Screenshot 2026-01-16 at 5 01 50 AM" src="https://github.com/user-attachments/assets/1e4e4bc6-fae4-4c8c-b421-a4832fbac842" />
All motors are powered through TIP-120 transistors which allows the Arduino Mega to safely manage high-current components. A common ground keeps logic levels stable. Signal wiring was arranged to reduce noise and interference.

## Code Outline
<img width="416" height="538" alt="Screenshot 2026-01-16 at 5 02 37 AM" src="https://github.com/user-attachments/assets/9c728dd0-d83a-4275-b355-413c9a835524" />


## Code
Full code is still in progress as shown in the `code` folder The completed project code will be updated in the same file when done. 

## Reflections and Connections 
**Reflections
This project has been one of my favorites because it introduced me to controlling components like servos and stepper motors, which I’ve never worked with before. It also helped me develop stronger troubleshooting skills and taught me how to use outside resources effectively. The Arduino websites were especially useful as references because they showed wiring and coding examples that were adaptable while still creating our own unique designs. As someone who doesn’t come from a robotics background and has never taken a coding class, this project has been a bit difficult for me to adjust to but I think I’m doing well. Working through this process showed me how important it is to plan out carefully, test parts individually, and be smarter with our time. I also learned how hardware limitations are to deal with, such as the Arduino Mega’s current capacity and the expense of parts. Overall, this project has just improved my problem-solving abilities and I think it’ll really help me in the future. I look forward to continuing to work on this project after the semester ends.
**Connections**
This project really connects to my future because it allows me to further see what real engineering work and processes look like, especially because that’s what I want to study in college. I know I got a little experience of this process in PLTW HPOE but this was different, more involved. Both my younger siblings are invested in STEM and I loved being a role model to inspire them as they watched me build the project. I hope it motivates them to try and create their own projects.

## Team Members
This project was completed as a collaboration between:

- Nora Dunn @norad4309 (me)
- Lena Li @lenali26 
- Claire Zhu @clairezzhu

All team members contributed to research, design, testing, and coding of the Arduino Claw Machine.

## References
Arduino Mega: https://store.arduino.cc/products/arduino-mega-2560-rev3

LCD: https://www.youtube.com/watch?v=s_-nIgo71_w&t=121s

Servo: https://www.youtube.com/watch?v=8-w_8izUO38

Stepper: https://www.youtube.com/watch?v=7spK_BkMJys&t=360s

Button: https://www.youtube.com/watch?v=VPGRqML_v0w

Joystick: https://www.youtube.com/watch?v=vo7SbVhW3pE&t=336s

Limit Switches: https://www.youtube.com/watch?v=6wuInF9Yw08

