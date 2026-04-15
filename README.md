# esim-latching-gas-alarm
A mixed-signal circuit simulation of an industrial gas leak detector using eSim. Features zero-latency hardware logic, automated ventilation, and a fail-safe SR Latch memory block for critical alarms.
# Smart Industrial Gas Leak Detection System

## 📌 Project Overview
This project demonstrates the circuit-level design and simulation of an industrial IoT safety node using **eSim**, an open-source EDA tool by FOSSEE (IIT Bombay). Operating entirely on hardware logic without the need for microcontrollers, the system uses a mixed-signal approach to monitor gas levels, trigger automated ventilation at moderate gas concentrations, and activate a permanent, fail-safe latching alarm during critical emergencies.

## ⚙️ Key Features
* **Zero-Latency Logic:** Purely hardware-driven architecture eliminating the risk of software crashes or loop delays.
* **Dual-Threshold Sensing:** Utilizes an LM393 Dual Differential Comparator to differentiate between moderate (2.0V) and critical (3.5V) gas concentrations.
* **Automated Mitigation:** Directly drives high-power MOSFETs to control exhaust fans during moderate leaks.
* **Fail-Safe Hardware Memory:** Implements an SR Latch (cross-coupled NOR gates) to ensure critical alarms remain permanently active until manually reset by an operator, complying with industrial safety standards.

## 🛠️ Tech Stack & Components
* **Simulation Software:** FOSSEE eSim, Ngspice
* **Logic Design:** Mixed-Signal (Analog to Digital bridging)
* **Core Components:**
  * Wheatstone Bridge & PWL Source (Sensor Emulation)
  * LM393 Comparators (Decision Logic)
  * Digital NOR Gates (SR Latch Memory)
  * IRF540 N-Channel MOSFETs (Actuation)

## 📊 Simulation Results
The logic architecture was successfully verified using Transient Analysis in Ngspice. The system correctly passes through four distinct phases:
1. **Normal:** Fan OFF, Alarm OFF.
2. **Moderate Leak:** Fan ON, Alarm OFF.
3. **Critical Leak:** Fan ON, Alarm ON (Memory Set).
4. **Clearance:** Gas dissipates $\rightarrow$ Fan OFF, **Alarm REMAINS ON** (Memory verified).

## 👨‍💻 Author
**Shivansh Chaurasiya** B.Tech Electronics and Communication Engineering (ECE)  
Noida Institute of Engineering and Technology (NIET)  

[*This project was developed as part of a FOSSEE eSim implementation task.*](https://esim.fossee.in/circuit-simulation-project/esim-circuit-simulation-run/799)
