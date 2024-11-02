
# Line-Following Robot Project

This project is a line-following robot controlled by an Arduino. The robot uses infrared (IR) sensors to detect a line on the ground and adjusts its movements to follow the line using a PID control mechanism.

## Components
- **Arduino Uno**
- **Motor Driver (L298N H-Bridge)**
- **IR Sensors**: 10 sensors for line detection
- **N20 Motors**: 2 units
- **Battery Pack**
- **Voltage Regulator (LM2596)**
- **LCD Display (1602)**

## Code Overview
The code is structured as follows:

### Variables and Definitions
- **Sensor Pins (c1 to c10)**: Each pin represents an IR sensor input.
- **Motor Control Pins (ena, enb, in1, in2, in3, in4)**: Pins for controlling the motors.
- **PID Control Parameters (kp, kd)**: Gains for the PID control.
- **Motor Speed Variables**: `bms`, `rms`, `lms` for setting baseline, right, and left motor speeds.

### Setup
In the `setup()` function, all sensor pins are initialized as inputs and motor control pins as outputs.

### Main Loop
The main loop reads sensor values and adjusts the robot's movements as follows:
- **Backwards Movement**: When the line is lost on the left side.
- **Turning Left/Right**: Based on heavy line detection on either side.
- **PID Control**: When the line is centered, PID adjustments are made to keep the robot on track.

### Functions
- **forward()**: Moves the robot forward.
- **right()**: Turns the robot to the right.
- **left()**: Turns the robot to the left.
- **back()**: Moves the robot backward.

## How to Use
1. Connect the components according to the pin configuration in the code.
2. Upload the code to the Arduino.
3. Place the robot on a line track, and it will start following the line.

## Notes
- Adjust `kp` and `kd` values if necessary to improve the PID response.
- Ensure the sensors are well-calibrated for the line color.

---

This code is a simple yet effective example of PID-based line following and can be expanded for additional behaviors or sensor configurations.
