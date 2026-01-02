# Crowbar Circuit: High-Speed Overvoltage Protection System

> **An engineering project focused on protecting sensitive electronic loads from voltage transients and power supply failures using a Zener-triggered SCR mechanism.**

## Project Overview
Developed at **Sir Syed University of Engineering and Technology (SSUET)**, this repository documents the design, simulation, and physical implementation of a **Crowbar Circuit**. The system acts as a "tripwire" protection layer, instantly short-circuiting the power supply to blow a fuse when a voltage threshold is exceeded, effectively isolating the load before damage occurs.

This project serves as a practical solution for safeguarding microcontrollers, voltage regulators, and other low-voltage components from regulator faults or surges.

## Balanced Team Contributions
To demonstrate technical project management, roles were divided between design verification and hardware assembly:

* **Shahmeer Hussain ([@shahmeeerx](https://github.com/shahmeeerx)):** Focused on hardware prototyping, breadboard implementation, and technical performance reporting.
* **Amna Yousuf ([@amna-014](https://github.com/amna-014)):** Led the Multisim circuit simulation, threshold analysis, and component selection verification.

## 🛠️ Technical Methodology
The system utilizes a Silicon Controlled Rectifier (SCR) in a "crowbar" configuration to achieve isolation in milliseconds:

* **Trigger Mechanism:** A **7.5V Zener Diode** sets the overvoltage threshold. Once input exceeds 7.5V, the diode conducts to provide gate current to the SCR.
* **Switching Logic:** A **C106D SCR** (rated for 4A) acts as the primary switch. Upon triggering, it creates a low-impedance path to ground.
* **System Isolation:** A **1A Fuse** provides the physical disconnection. The fuse is selected to blow within milliseconds of the SCR trigger, isolating the load.
* **Gate Stability:** A **1kΩ Pull-down Resistor** ensures the SCR remains in the OFF state during normal operation to prevent accidental triggering.

### Test Observations
| Input Voltage (V) | Fuse Condition | System State |
| :--- | :--- | :--- |
| **4V** | Intact | Normal Operation |
| **5V** | Intact | Normal Operation |
| **7.2V** | **Blown** | **Protection Active** |

### Hardware Implementation
The hardware setup used a **14.4Ω bulb** as a load. Photos of the assembly and the glowing bulb under normal operation can be found in the `hardware images/` folder.

## Repository Contents
* **`Simulation/`**: Multisim circuit design files (`.ms14`).
* **`Project_Report.pdf`**: Formal Technical Project Report in PDF format.
* **`hardware images/`**: Photos of the working breadboard prototype.
* **`Technical-References/`**: Component datasheets (C106D) and supporting research paper.

## Development Team
* **Shahmeer Hussain** — [@shahmeeerx](https://github.com/shahmeeerx) (2022F-BBM-014)
* **Amna Yousuf** — [@amna-014](https://github.com/amna-014) (2022F-BBM-012)

---
_© 2026 Overvoltage Protection Project. Built for the Dept. of Biomedical Engineering, SSUET._
