# Task-Priority Kinematic Control (Lab 6 – Mobile Manipulator, 2B)

This project extends the **Task-Priority (TP) kinematic control** framework to a **mobile manipulator**:  
a differential-drive mobile base with a 3-link planar manipulator mounted on top.  
The lab explores how to integrate base and arm kinematics, apply weighted control, and compare different base integration methods.

## Overview
- **Exercise 1**:  
  - Implemented a `MobileManipulator` class combining a differential-drive base and a 3-link manipulator.  
  - Integrated recursive TP control with two tasks:  
    1. **Joint Limits** (safety constraint).  
    2. **End-effector Position** (goal task).  
  - Verified that the manipulator respects joint limits while reaching the target.  

- **Exercise 2**:  
  - Introduced **Weighted Damped Least Squares (WDLS)**.  
  - Applied different weighting matrices to control the relative influence of base vs. manipulator joints.  
  - Compared how different weightings affect velocity distribution and error convergence.  

- **Exercise 3**:  
  - Compared three **mobile base integration methods**:  
    1. Move then Rotate.  
    2. Rotate then Move.  
    3. Move and Rotate (arc-based).  
  - Assessed their effect on trajectory tracking and task error evolution.  

## Key Concepts
- **Mobile Manipulator Kinematics**: Combines base pose \((x, y, \theta)\) with manipulator joint states.  
- **Recursive TP Algorithm**: Ensures higher-priority tasks (e.g., safety) are satisfied before lower-priority ones.  
- **Weighted DLS**: Allows tuning of joint contributions, balancing base vs. arm motion.  
- **Base Integration Methods**: Different update schemes (linear vs. arc-based) significantly affect accuracy.  

## Files
- `Exercice1.py` – Mobile manipulator TP control with joint limits and EE position.  
- `Exercice2.py` – Weighted DLS with end-effector configuration task.  
- `Exercice3.py` – Comparison of base integration methods.  
- `final_plot.py` – Visualization of trajectories for different base integration methods.  
- `Lab6_robotics.py` – Core classes (MobileManipulator, tasks, kinematics).  
- `Common.py` – Shared functions (Jacobian, DLS, WDLS, transformations).  
- `Report_RihabLaroussi.pdf` – Full lab report with methodology, code, results, and analysis.  

## Results
- **Exercise 1**: The manipulator reached the target while respecting joint limits.  
- **Exercise 2**: Different weighting matrices redistributed motion between base and arm, confirming WDLS flexibility.  
- **Exercise 3**: Arc-based integration produced the most realistic trajectories, while simpler methods introduced larger errors.  

## Conclusion
This lab demonstrated how to extend **Task-Priority control** to **mobile manipulators**.  
By combining recursive TP, weighted control, and realistic base integration, the system achieved safe, flexible, and accurate motion — a crucial step toward deploying robots in dynamic, real-world environments.
