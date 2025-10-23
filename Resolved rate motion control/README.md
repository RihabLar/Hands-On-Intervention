# Resolved-Rate Motion Control (Lab 2)

This project implements **resolved-rate motion control** for a planar robotic manipulator.  
The lab is divided into two main parts: simulating the kinematics of a 2-link planar manipulator and applying resolved-rate motion control using different inverse kinematics methods.

## Overview
- **Exercise 1: Kinematic Simulation**
  - Modeled a 2-link planar manipulator using the **Denavit–Hartenberg (DH) convention**.
  - Implemented forward kinematics to compute the end-effector pose.
  - Simulated joint motion and visualized the manipulator’s trajectory and joint angle evolution.

- **Exercise 2: Resolved-Rate Motion Control**
  - Implemented the resolved-rate control algorithm to compute joint velocities for a desired end-effector velocity.
  - Compared three inverse kinematics methods:
    1. **Jacobian Transpose**
    2. **Pseudoinverse**
    3. **Damped Least Squares (DLS)**
  - Evaluated performance by analyzing error norms over time.

## Key Concepts
- **Jacobian Matrix**: Relates joint velocities to end-effector linear and angular velocities.  
- **Inverse Kinematics Solutions**:
  - *Transpose*: Simple but less accurate.  
  - *Pseudoinverse*: Accurate when Jacobian is non-singular.  
  - *DLS*: Robust near singularities, balances stability and accuracy.  
- **Error Norm Analysis**: Used to compare convergence and stability of the three methods.

## Files
- `Exercice1.py` – Kinematic simulation of the 2-link manipulator.  
- `Exercice2.py` – Resolved-rate motion control with multiple inverse kinematics methods.  
- `Common.py` – Shared functions (DH transformations, kinematics, Jacobian, DLS).  
- `error.py` – Visualization of error norms for the three methods.  
- `Report_RihabLaroussi.pdf` – Full lab report with methodology, code, results, and analysis.  

## Results
- **Kinematic Simulation**: Correctly visualized the manipulator’s motion and end-effector trajectory.  
- **Control Methods**:
  - Jacobian Transpose had the largest error norm.  
  - Pseudoinverse and DLS performed significantly better, with DLS showing the most stable results near singularities.  
- **Error Norm Plots** confirmed that DLS provided the best trade-off between accuracy and robustness.

## Conclusion
This lab demonstrated the fundamentals of **resolved-rate motion control**.  
By comparing different inverse kinematics methods, we showed that while the pseudoinverse is effective, the **DLS method** offers superior stability and robustness, making it highly suitable for real-world robotic applications.
