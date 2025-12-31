# Smart Grid Active Battery Balancing System 🔋⚡

![MATLAB](https://img.shields.io/badge/MATLAB-R2024b-orange) ![Simulink](https://img.shields.io/badge/Simulink-Simscape-blue) ![Status](https://img.shields.io/badge/Status-Completed-green)

An advanced **Battery Management System (BMS)** simulation designed for DC Microgrids. This project demonstrates an **Active Balancing Algorithm** integrated with a real-time **MATLAB App Designer** dashboard to monitor and manage energy transfer between multiple Li-Ion battery packs.

---

## 📸 Dashboard Preview

![Interface Preview](dashboard_view.png)
*(Real-time monitoring interface showing SOC levels, charging trends, and system status)*

---

## 🚀 Key Features

* **Active Balancing Logic:** Implements a smart algorithm that detects SoC mismatches across 5 battery packs and transfers energy from the highest charged (Source) to the lowest charged (Load) unit via a common DC Bus.
* **Hybrid Power Source:** Integrates **PV (Solar) Array**, **Grid connection**, and **Battery Storage** in a unified Simulink model.
* **Real-Time Visualization:** A custom GUI built with MATLAB App Designer featuring:
    * Analog Gauges for charge/discharge acceleration.
    * Precision Numeric Displays for SoC tracking.
    * Cinematic Playback: Uses a custom `tic-toc` synchronization algorithm to visualize high-speed simulation data in real-time flow.
* **Sequential Priority Charging:** Demonstrates "Round-Robin" style charging priority when initial battery states are equal.

## 🛠️ Technical Architecture

| Component | Description |
| :--- | :--- |
| **Simulink Model** | `Akillisebeke1.slx` - Contains the power electronics, breakers, PV array, and Grid blocks. |
| **Control Logic** | MATLAB Function Block - executing the Min/Max SoC detection and switching decisions. |
| **User Interface** | `BataryaArayuzu.mlapp` - The front-end control panel for operators. |
| **Protocol** | Direct Signal connection with isolated breaker control lines. |

## ⚙️ How to Run the Project

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/yourusername/Smart-Grid-Active-Battery-Balancing-System.git](https://github.com/yourusername/Smart-Grid-Active-Battery-Balancing-System.git)
    ```
2.  **Open MATLAB:** Ensure you have the Simulink and Simscape Electrical toolboxes installed.
3.  **Load the Model:** Open `Akillisebeke1.slx`. **Do not run it yet.**
4.  **Launch the GUI:** Open `BataryaArayuzu.mlapp`.
5.  **Start Simulation:** Click the **"Simülasyonu Başlat"** button on the interface. The App will trigger the Simulink engine and visualize the results.

## 📊 Simulation Logic & Results

The system uses a **Voltage-Based Active Balancing** method.
1.  Sensors read the SoC of 5 batteries.
2.  The central controller identifies $SoC_{max}$ and $SoC_{min}$.
3.  Specific breakers are closed to allow current flow, while others remain isolated.
4.  **Result:** The batteries self-balance while absorbing energy from the Grid/PV, ensuring longevity and efficiency of the storage system.

---

### 👨‍💻 Developer
**Emirhan Torun**
*Software Engineering Student*

*Developed as part of the "Smart Grids & Microgrid Analysis" project.*
