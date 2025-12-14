# Hybrid Electric Vehicle (EV) Charging Station ⚡🚗
### Simulation of Solar-Grid Integrated Charging Infrastructure

**Domain:** Power Electronics & Renewable Energy Systems

---

## 📖 Project Overview
This repository contains the simulation files and design documentation for a **Hybrid EV Charging Station**. The system integrates **Solar PV** and **Grid Power** to create a sustainable charging infrastructure.

The primary objective is to design a controller that prioritizes renewable energy extraction while maintaining grid stability. The system architecture was validated using **MATLAB Simulink** to ensure robust performance under varying load and irradiance conditions.

---

## ⚙️ System Architecture
The topology is based on a common **400V DC Link** architecture connecting three power stages:

1.  **Solar Power Source (Primary):** A 4kW PV array feeding a DC-DC Boost Converter.
2.  **Grid Interface (Backup):** A single-phase grid connection utilizing an AC-DC Rectifier.
3.  **Battery Charging Unit:** An isolated DC-DC converter for Lithium-ion battery charging.


---

## 🛠️ Key Technical Features

### 1. Solar Subsystem (MPPT)
* **Source Model:** 4kW PV Array (Based on Kyocera KC200GT parameters).
* **Converter:** Non-isolated Boost Converter.
* **Control Algorithm:** **Incremental Conductance MPPT**.
* **Functionality:** The controller dynamically adjusts the duty cycle to track the Maximum Power Point (MPP) regardless of solar irradiance or temperature changes.

### 2. Grid Interface (PFC)
* **Converter Topology:** **Interleaved Boost Power Factor Correction (PFC) Rectifier**.
* **Control Strategy:** Cascaded Dual-Loop Control.
    * **Outer Loop (Voltage):** PI Controller regulates the DC Link voltage at 400V.
    * **Inner Loop (Current):** PR (Proportional-Resonant) Controller ensures grid current is sinusoidal and in-phase with voltage.
* **Performance:** Achieves Near-Unity Power Factor and minimizes Total Harmonic Distortion (THD).

### 3. Battery Charging Stage
* **Converter Topology:** **Dual Active Bridge (DAB)** Isolated DC-DC Converter.
* **Safety Feature:** Provides galvanic isolation between the high-voltage DC bus and the low-voltage battery.
* **Charging Strategy:** Implements a **Constant Current - Constant Voltage (CC-CV)** profile, critical for Lithium-ion battery health and safety.

---

## 📊 Phase 1 Simulation Results
The MATLAB Simulink analysis validated the following performance metrics:
* **DC Link Stability:** Voltage remained regulated at 400V during load transients and source switching.
* **Source Management:** Successful seamless transition between Solar (primary) and Grid (backup) modes.
* **Grid Compliance:** Input current waveforms demonstrated high power factor compliance.
* **Charging Precision:** Battery current and voltage limits were strictly maintained according to the CC-CV profile.

---


---

## 📂 Repository Structure
* `/Simulation` - MATLAB Simulink source files (`.slx`).
* `/Documentation` - Block diagrams, circuit schematics, and design calculations.
* `/Results` - Simulation waveforms and performance graphs.

---

### 📜 License
This project is open-source 
