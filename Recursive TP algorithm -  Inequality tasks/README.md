# Task-Priority Kinematic Control (Lab 5 – Set-Based Tasks)

This project extends the **Task-Priority (TP) kinematic control** framework for a planar 3-link manipulator by introducing **set-based tasks**.  
Unlike equality tasks (which aim to reach a precise target), set-based tasks enforce constraints such as obstacle avoidance and joint limits, ensuring safe and feasible robot motion in constrained environments.

## Overview
- **Exercise 1**:  
  - Implemented an **Obstacle Avoidance Task** (`Obstacle2D`) as a set-based task.  
  - Defined three obstacles in the workspace with activation/deactivation thresholds.  
  - Combined obstacle avoidance with an end-effector position task using the recursive TP algorithm.  
  - Demonstrated how the manipulator avoids obstacles while still reaching its target.  

- **Exercise 2**:  
  - Implemented a **Joint Limits Task** (`JointLimits`) to keep joint 1 within a safe operational range.  
  - Combined joint limits with an end-effector position task.  
  - Showed how the robot respects joint constraints while still attempting to reach the desired end-effector position.  

## Key Concepts
- **Set-Based Tasks**:  
  Activated only when constraints are violated (e.g., too close to an obstacle, joint near its limit).  
  Deactivated once the system returns to a safe zone, avoiding chattering by using different activation/deactivation thresholds.  

- **Recursive TP Algorithm with Inequality Tasks**:  
  Extended to handle both equality and inequality tasks in a unified framework.  

- **Trade-Offs**:  
  Obstacle avoidance and joint limits may temporarily increase end-effector error, but ensure safety and feasibility.  

## Files
- `lab4_robotics.py` – Core manipulator and task classes (Manipulator, Task, Position2D, Orientation2D, Configuration2D, Joint_Position, Obstacle2D, JointLimits).  
- `Exercice1.py` – Simulation of obstacle avoidance with end-effector positioning.  
- `Exercice2.py` – Simulation of joint limits with end-effector positioning.  
- `Report_RihabLaroussi.pdf` – Full lab report with methodology, code, results, and analysis.  

## Results
- **Obstacle Avoidance**:  
  The manipulator successfully avoided all three obstacles while converging to the target end-effector position.  
  Distance-to-obstacle plots confirmed safe margins were maintained.  

- **Joint Limits**:  
  Joint 1 remained within the defined safe set while the end-effector approached its target.  
  Small oscillations in EE error occurred near joint boundaries, reflecting the balance between safety and accuracy.  

## Conclusion
This lab demonstrated how **set-based tasks** can be integrated into the Task-Priority control framework.  
By combining equality and inequality tasks, the manipulator achieved both **goal-directed motion** and **constraint satisfaction**, a critical step toward deploying robots in real-world, cluttered, and safety-critical environments.
