# Task-Priority Kinematic Control (Lab 3)

This project explores **task-priority kinematic control** for a planar 3-link manipulator.  
The focus is on handling redundant degrees of freedom by assigning priorities to tasks: higher-priority tasks are satisfied first, while lower-priority tasks are executed in the null space of the higher-priority ones.

## Overview
- **Exercise 1**:  
  - Implemented resolved-rate motion control with null space projection.  
  - Visualized null space motions of a 3-link planar manipulator.  
  - Demonstrated how the end-effector reaches its target while joints reconfigure in the null space.  

- **Exercise 2**:  
  - Implemented **Task-Priority (TP) control** with two tasks:  
    1. End-effector position control.  
    2. First joint position control.  
  - Showed how task hierarchies affect error convergence and robot behavior.  
  - Compared cases where the end-effector is the priority vs. when the first joint is the priority.  

## Key Concepts
- **Null Space Projection**:  
  \( P = I - J^+ J \), where \( J^+ \) is the pseudoinverse of the Jacobian.  
  Ensures secondary tasks do not interfere with higher-priority tasks.  

- **Task-Priority Control**:  
  Combines multiple tasks by projecting lower-priority tasks into the null space of higher-priority ones.  

- **Weighting Matrix (W)**:  
  Used in pseudoinverse/DLS to penalize or prioritize specific joints, useful for avoiding singularities, joint limits, or sensitive configurations.  

## Files
- `Exercice1.py` – Simulation of resolved-rate motion control with null space motions.  
- `Exercice2.py` – Implementation of task-priority control with two tasks.  
- `Common.py` – Shared functions (kinematics, Jacobian, utilities).  
- `Report_RihabLaroussi.pdf` – Full lab report with methodology, code, results, and analysis.  

## Results
- **Exercise 1**:  
  - End-effector smoothly reached the target.  
  - Joints oscillated due to null space motions, showing redundancy handling.  

- **Exercise 2**:  
  - When **end-effector** was the priority: EE error converged to zero, joint 1 error only reduced when not conflicting.  
  - When **joint 1** was the priority: joint 1 error converged to zero, EE task was only satisfied if compatible.  

## Conclusion
This lab demonstrated how **task-priority control** enables robots with redundant DOFs to handle multiple objectives.  
- Null space projection allows secondary tasks without disturbing primary ones.  
- Task hierarchies strongly influence robot behavior and error convergence.  
- Weighting matrices and advanced strategies can further improve robustness in real-world applications.
