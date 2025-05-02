# 🧠 RL-Based Control of Dielectric Elastomer Actuators (DEA)

This repository contains the report and code for a semester project at EPFL on **Reinforcement Learning (RL)**-based control of **Dielectric Elastomer Actuators (DEAs)**. The project explores the use of **Proximal Policy Optimization (PPO)** to learn control policies for highly non-linear, viscoelastic actuators, both in simulation and on real hardware.

📄 [Download the project report (PDF)](Semester_Project_Report.pdf)

---

## 📌 Overview

**Dielectric Elastomer Actuators (DEAs)** are soft, flexible actuators that mimic biological muscle behavior. Their inherent **nonlinearities**, **hysteresis**, and **viscoelastic effects** pose significant challenges for traditional control strategies like PID or LQR.

This project investigates how **Reinforcement Learning**, particularly PPO, can be used to model and control DEAs effectively **without requiring an explicit physical model**.

---

## 🛠️ Methodology

### 🔧 Control Formulation
- **State space**: `{displacement, velocity, target displacement}`
- **Action space**: continuous voltage control
- **Reward function**: combines displacement error and stabilization bonus
- **RL Algorithm**: PPO (Proximal Policy Optimization)
- **Frameworks**: `Stable-Baselines3`, `PyTorch`, `Gymnasium`

### ⚙️ Experimental Setups
1. **Simulation** of a simplified linear actuator
2. **Moving Platform** with DEA driving a mass
3. **Cranium Setup** with a free actuator and a marker for displacement tracking

---

## 📊 Results Summary

| Setup              | RMSE (Step) | RMSE ("Hello") | Notes                                             |
|-------------------|-------------|----------------|---------------------------------------------------|
| Simulated Actuator| ~0.07       | N/A            | Good convergence, stable tracking                 |
| Moving Platform   | 0.11        | 0.16           | Affected by oscillations and mass interactions    |
| Cranium Setup     | 0.05        | 0.13           | Best results; stable and accurate tracking        |
| PID (Baseline)    | 0.114       | 0.118          | RL is comparable without needing a model          |

---

## 🚀 Key Contributions

- ✅ End-to-end RL controller for DEAs with continuous action space
- ✅ Real-world deployment and evaluation on two physical test benches
- ✅ Comparable performance to hand-tuned PID controller
- ⚠️ Robust to actuator variance, no explicit modeling needed

---

## 🧠 Future Work

Suggestions for improvement include:
- Smoothing voltage signals
- Refining reward structure
- Adding RNNs for better temporal memory
- Trying more advanced RL algorithms (e.g., DreamerV3)

---

## 👥 Author and Supervision

- **Author**: Jad Benabdelkader  
  *Master in Robotics, EPFL*

- **Supervisors**:  
  Marc Favier  
  Stefania Konstantinidi  

Semester: Fall 2024  
School: EPFL, Section de Microtechnique

---


