# Arduino Based Black Line Follower Robot

## Introduction
An interesting project that incorporates robotics, electronics, and programming is building a line follower robot. We’ll walk you through the process of creating your very own black line follower robot on an Arduino platform. This project is a fantastic chance to practice your programming abilities in a real-world scenario, in addition to learning a lot about robotics. Now let’s dig in and discover the intriguing realm of robots that follow lines!

---

## Components Required
- 5mm Acrylic Sheet (20cm x 12cm)
- DC Gear Motor x 4
- Arduino UNO
- IR Sensor x 2
- L298 Motor Driver
- 4 Pcs Smart Robot Car Tyres Wheels
- Male to Female Jumper Wires
- On/Off Switch
- 18650 Battery Holder – 2 Cell
- 18650 Battery Cell 3.7V x 2

---

## Circuit Diagram
Knowing how the parts fit together is crucial before beginning the assembling process. A condensed circuit diagram that shows how each component works together is shown below. To guarantee correct operation, carefully follow this diagram. In this circuit diagram:

- An Arduino UNO is used as a microcontroller.  
- A L293D motor driver is used that drives four DC motors.  
- Two IR sensors are used to detect any obstacle on the way.  
- Two cells of 3.7V batteries are used as a power source.  
- A power on/off switch is used.  
- The output of the IR sensors are connected to **A0 and A1 pins** of the Arduino UNO.  

---

## Pin Connections  

### Motor Driver (L298N → Arduino UNO)
| L298N Pin | Arduino Pin | Function |
|-----------|-------------|----------|
| enA       | 10          | Enable Motor A (Right Side Motors Speed Control) |
| in1       | 9           | Motor 1 Forward |
| in2       | 8           | Motor 1 Backward |
| in3       | 7           | Motor 2 Forward |
| in4       | 6           | Motor 2 Backward |
| enB       | 5           | Enable Motor B (Left Side Motors Speed Control) |

### IR Sensors → Arduino UNO
| IR Sensor | Arduino Pin | Function |
|-----------|-------------|----------|
| Right IR  | A0          | Detects line on right side |
| Left IR   | A1          | Detects line on left side |

### Motors
- Motor A (Right Side) connected to **OUT1 & OUT2** of L298N.  
- Motor B (Left Side) connected to **OUT3 & OUT4** of L298N.  

### Power
- L298N **+12V pin** connected to **Battery + (7.4V from 2 x 18650 cells)**  
- L298N **GND** connected to **Arduino GND and Battery -**  
- 5V regulated output from L298N can power **Arduino UNO (Vin/5V)**  

---

## Explanation
These lines define symbolic names for different pins and sensors using `#define`. In Arduino programming, this is a standard procedure to improve readability and maintainability of the code.  

To operate the motors, the digital pins linked to the L298 motor driver are named `enA`, `in1`, `in2`, `in3`, `in4`, and `enB`. The left and right infrared (IR) sensors are attached to analog pins denoted as `L_S` and `R_S`, respectively.  

The `pinMode` parameter in the `setup()` method determines whether the IR sensor pins are inputs or outputs. The motor speeds are set using `analogWrite`. The numbers go from 0 to 255, where 255 represents maximum speed and 0 represents off. To give the motors time to stabilize, a delay is inserted.  

The software uses `digitalRead` in the `loop()` method to determine the current statuses of the left (`L_S`) and right (`R_S`) infrared sensors. The robot’s movement is controlled by invoking the relevant function (`forword()`, `turnRight()`, `turnLeft()`, or `Stop()`) based on the sensor data.  

Based on the sensor data, these routines regulate the robot’s movement. They identify each motor’s orientation by applying the proper blends of HIGH and LOW signals to the motor driver pins. 



## 👨‍💻 Author
**Suman R N**  
📧 Contact: sumansurn@gmail.com 
🔗 LinkedIn: https://www.linkedin.com/in/suman-r-1b5260335 

