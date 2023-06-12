PID Controllers
===============

This page will explain what a PID controller is, where it can be useful, and how to use it!

Introduction
------------
A PID (Proportional-Integral-Derivative) controller is a control loop feedback mechanism widely used in robotics and automation. It helps maintain stability and accuracy in various systems by adjusting the output based on the difference between a desired setpoint and the actual measured value. In FRC robotics, PID controllers are commonly used to control mechanisms such as arm positioning, elevator height, or drivetrain movement.

Components of a PID Controller
------------------------------
A PID controller consists of three main components:

1. Proportional (P) term:
   - The P term produces an output directly proportional to the error between the setpoint and the measured value.
   - It helps the system quickly respond to changes and reach the desired setpoint.

2. Integral (I) term:
   - The I term accumulates the error over time and produces an output proportional to the integral of the error.
   - It helps eliminate steady-state errors and corrects for system biases or external disturbances.

3. Derivative (D) term:
   - The D term predicts the future trend of the error by calculating the rate of change of the error.
   - It helps dampen oscillations and stabilize the system's response.

Usage in our Robot
---------------------
In our Robot, PID controllers are employed in various applications, including:

1. Arm Positioning:
   - PID control can be used to precisely control the position of an arm mechanism, such as a robot's lifting arm.
   - The setpoint represents the desired angle or position, while the feedback sensor provides the measured angle.
   - The PID controller adjusts the motor output based on the error to maintain the desired arm position.

2. Elevator Height Control:
   - PID control is often used to control the height of an elevator mechanism.
   - The setpoint represents the desired height, while the feedback sensor provides the measured height.
   - The PID controller adjusts the motor output to ensure the elevator reaches and maintains the desired height accurately.

3. Drivetrain Control:
   - PID control is utilized to control the movement and navigation of the robot's drivetrain.
   - The setpoint represents the desired position or velocity, while the feedback sensor provides the current position or velocity.
   - The PID controller adjusts the motor outputs to enable precise movement, accurate turning, and maintaining straight paths.

How to Use a PID Controller
---------------------------
The WPILib library provides a PIDController class that can be used to implement PID control in your robot. The class can be found `here <https://first.wpi.edu/FRC/roborio/release/docs/java/edu/wpi/first/wpilibj/controller/PIDController.html>`_.`

Code Examples
-------------   

Here we are importing the PIDController class from the WPILib library.

.. highlight:: java
   import edu.wpi.first.wpilibj.controller.PIDController;

   public class PIDExample {
      private final double kP_ = 0.1;

      // We usually leave the kI and kD terms as 0 unless there is oscillations
      private final double kI_ = 0.0;
      private final double kD_ = 0.0;

      public PIDExample() {
         // Create a PIDController with the specified constants
         PIDController pid_controller_ = new PIDController(kP_, kI_, kD_);
       
         // Set the setpoint to 10
         pid_controller_.setSetpoint(10);
       
         // Get the output of the PID controller
         double output = pid_controller_.calculate(5);
      }

      public double getOutput() {
         return output;
      }
   }

PID Controllers are one of the most important tools we have in code although we have to use it wisely and only when necessary.

(This is just a basic overview I'll add more images and better examples later)

