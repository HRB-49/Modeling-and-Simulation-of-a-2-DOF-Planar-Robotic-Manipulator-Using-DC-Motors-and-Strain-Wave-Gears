# 2-DOF Planar Robotic Manipulator: Modeling, Simulation, and Control

## 1. Project Overview
This project focuses on the modeling and simulation of a two-degree-of-freedom (2-DOF) planar robotic manipulator. The system is designed using industrial-grade components, specifically the **Maxon RE 40 DC motor** and **LHT-20 Strain Wave Gears** (Harmonic Drives). Developed in **MATLAB/Simulink** using the **Simscape** environment, the project implements a unified multi-domain model that accounts for electrical, mechanical, and thermal behaviors under gravitational disturbances.

The manipulator was successfully validated by tracing a square trajectory in both 5-second and 10-second intervals with high tracking fidelity.

---

## 2. Key Features
* **Model-Based Design (MBD):** A complete electromechanical and thermal representation of the robot joints.
* **Explicit Thermal Network:** A custom-built thermal network (winding/housing) for real-time temperature prediction, ensuring the system remains within the 155°C hardware limit.
* **Discrete-Time Control:** Implementation of a tuned discrete PID controller to manage position control in a vertical plane.
* **Inverse Kinematics:** Integrated geometric solutions to translate Cartesian square paths into joint space trajectories.
* **Power & Efficiency Analysis:** Detailed evaluation of copper losses, peak power requirements, and overall system efficiency (calculated at ~69%).

---

## 3. System Specifications

### 3.1 Actuator: Maxon RE 40 (148866)
The manipulator is driven by two identical joints with the following verified parameters:
* **Nominal Voltage:** 12 V
* **No-load Speed:** 6920 rpm
* **Stall Torque:** 1720 mNm
* **Terminal Resistance:** 0.115 Ω
* **Rotor Inertia:** 139 gcm²

### 3.2 Transmission: Strain Wave Gear (LHT-20)
* **Model:** LHT-20-100-U-III
* **Reduction Ratio:** 100:1
* **Rated Efficiency:** 75%
* **Validated Payload:** Capable of handling loads up to ~4.0 kg.

### 3.3 Mechanical Structure
* **Links:** Dual 0.2m links modeled using Aluminum 6061 properties.
* **Operating Plane:** Vertical (Parallel to gravity).

---

## 4. Control System Design
The system employs independent joint PID controllers tuned to meet rigorous industrial performance criteria.

### PID Parameters
| Parameter | Value |
| :--- | :--- |
| **Proportional (Kp)** | 6.005 |
| **Integral (Ki)** | 0.11 |
| **Derivative (Kd)** | 6.5 |
| **Sample Time (Ts)** | 0.001 s |

### Performance Metrics
* **Settling Time:** < 1.14 s
* **Overshoot:** < 2%
* **Steady-State Error:** < 1%

---

## 5. Performance Analysis
The system was evaluated through a square trajectory tracking mission, yielding the following results:
* **Average Electrical Power:** ~37.45 W
* **Peak Power Requirement:** ~72.00 W (Occurs during transients and start-up)
* **Average Mechanical Power:** ~26.00 W
* **Thermal Stability:** Winding temperature rise stabilized at ~5.26°C above ambient, confirming continuous operation without an external heat sink.

---

## 6. Conclusions
The project successfully realized the modeling and simulation of a 2-DOF planar robotic manipulator. By integrating high-performance Maxon motors with 100:1 strain wave gears, we developed a robust joint architecture capable of precise movement despite gravitational disturbances. 

Key achievements include:
* **System Integration:** Successfully bridged electrical, mechanical, and thermal domains in a unified Simscape model.
* **Precision Tracking:** Achieved sub-second settling times and negligible steady-state error for complex trajectories.
* **Thermal Validation:** Confirmed that the motor housing and winding temperatures stay well within permissible safety limits during operation.
* **Efficiency:** Demonstrated a 69% overall system efficiency, validating the choice of high-ratio precision gearing.

This computational framework provides a solid foundation for future Hardware-in-the-Loop (HIL) testing and physical implementation of 2-DOF robotic systems.

---

## 7. License
This project is licensed under the **MIT License**.
