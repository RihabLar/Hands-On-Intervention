# Task-Priority Kinematic Control (Lab 4 – Recursive TP Algorithm)

This project extends the **Task-Priority (TP) kinematic control** approach for a planar 3-link manipulator.  
Building on Lab 3, we implement the **recursive TP algorithm**, enabling the handling of multiple tasks with arbitrary hierarchies.  
We also enhance the control with **gain matrices, feedforward velocity, and link selection**, making the system more robust and adaptable.

## Overview
- **Exercise 1**:  
  - Implemented the recursive TP algorithm.  
  - Defined four tasks:  
    1. End-effector position  
    2. End-effector orientation  
    3. End-effector configuration (position + orientation)  
    4. Joint 1 position  
  - Simulated different task hierarchies to show how priorities affect robot behavior.  

- **Exercise 2**:  
  - Extended the algorithm with:  
    - **Link selection** (tasks can target any link, not just the end-effector).  
    - **Gain matrices** for weighted task control.  
    - **Feedforward velocity** for improved tracking.  
  - Demonstrated more flexible and realistic task definitions.  

## Key Concepts
- **Recursive TP Algorithm**:  
  Iteratively computes joint velocities while projecting lower-priority tasks into the null space of higher-priority ones.  

- **Null Space Projection**:  
  Ensures secondary tasks do not interfere with higher-priority tasks.  

- **Weighted DLS**:  
  Gain matrices allow prioritization of tasks beyond strict hierarchy.  

- **Feedforward Control**:  
  Improves tracking performance by anticipating desired motion.  

## Files
- `Exercice1.py` – Recursive TP algorithm with multiple task hierarchies.  
- `Exercice2.py` – Extended TP algorithm with link selection, gain matrices, and feedforward velocity.  
- `lab4_robotics.py` – Core classes and functions (Manipulator, Task, Position2D, Orientation2D, Configuration2D, Joint_Position).  
- `Report.pdf` – Full lab report with methodology, code, results, and analysis.  

## Results
- Recursive TP algorithm successfully handled multiple tasks with different hierarchies.  
- End-effector position and orientation tasks converged smoothly when prioritized.  
- Joint-level tasks could be satisfied without disturbing higher-priority end-effector tasks.  
- Gain matrices and feedforward velocity improved robustness and tracking accuracy.  

## Conclusion
This lab demonstrated the flexibility of the **recursive Task-Priority control framework**.  
By combining null space projection, gain weighting, and feedforward terms, the controller can manage complex multi-task scenarios, making it suitable for advanced robotic applications.
