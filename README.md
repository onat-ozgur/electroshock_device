# ⚡ Portable High-Voltage Pulse Generator (400 kV Arc Generator)

<p align="center">
  <img src="demo.gif" alt="High-Voltage Arc Test Demonstration" width="350">
</p>

<p align="center">
  <b>3.7V DC Input</b> • <b>400 kV Pulse / Arc Output</b> 
</p>

---

## 📌 Project Overview

This project is a compact, handheld, and rechargeable **400 kV high-voltage pulse and electrical arc generator** powered by a single-cell lithium-ion battery.

I designed and assembled the hardware to convert a low-voltage 3.7V DC source into a 400 kV output using a high-frequency solid-state inverter and step-up flyback transformer stage. The resulting potential difference exceeds the dielectric breakdown threshold of air, establishing an ionized plasma arc across the discharge electrodes. Power delivery, constant-current/constant-voltage (CC/CV) charging, and cell safety are handled by an integrated TP4056 management board.

---

## ⚡ Hardware Architecture & Components

| Component | Specification | Function |
| :--- | :--- | :--- |
| **Li-Ion Battery** | 18650 (3.7V / 2200 mAh) | Main power reservoir; provides high instantaneous discharge current |
| **Charge & Protection Board** | TP4056 | |
| **Step-Up Pulse Module** | 400 kV Boost Inverter Module | High-frequency oscillator and potted step-up transformer stage |
| **Trigger Switch** | Snap-Action Micro Switch | Momentary manual control for the high-current primary circuit |
| **Battery Sled / Holder** | 18650 Slot | Structural chassis and mechanical backbone |
| **Arc Electrodes** | Pointed Screws (Tape-Insulated) | Screws mounted at the terminals, insulated with tape up to the sharp tips |

---

## 🔌 Circuit & Wiring Schematic

```text
  [ 5V USB Input ]
         │
         ▼
  +-------------+   B+   +-----------------------+
  |   TP4056    |------->| 18650 Battery Sled (+) |
  | Charge/BMS  |   B-   | (3.7V 2200mAh Li-ion) |
  +-------------+------->| 18650 Battery Sled (-) |
                         +-----------------------+
                                 │           │
                                 │(+)        │(-)
                                 ▼           │
                         +---------------+   │
                         | Micro Switch  |   │
                         |   (Trigger)   |   │
                         +---------------+   │
                                 │           │
                                 ▼(+)        ▼(-)
                    +-----------------------------+
                    |    400 kV Step-Up Module    |
                    |   (Inverter / Boost Coil)   |
                    +-----------------------------+
                                 │           │
                                 ▼           ▼
                              [ Spark Gap Electrodes ]
                               (Ionized Plasma Arc)
```

---

## ⚙️ Engineering Principles & Working Mechanism

1. **TP4056:** Regulates incoming 5V USB power to safely charge the 18650 cell up to 4.2V using a standard CC/CV profile. The integrated protection circuit isolates the cell if voltage drops below safe thresholds under heavy load.
2. **High-Frequency Inversion:** The 3.7V DC bus feeds a solid-state switching circuit that generates high-frequency AC oscillation to drive the primary winding of the miniature ferrite core transformer.
3. **Step-Up Transformation (400 kV):** With a very high secondary-to-primary turns ratio, the transformer steps up the voltage to a 400 kV pulsed output. When the voltage gradient across the electrode tips surpasses the dielectric strength of ambient air (~3 kV/mm), electric breakdown occurs, generating an audible high-temperature plasma discharge.
4. **Mechanical Packaging:** The 18650 battery holder acts as the primary structural frame. All functional sub-assemblies—charging PCB, trigger mechanism, and encapsulated step-up coil—are hardwired and mounted directly along the perimeter to maintain an ergonomic, single-hand form factor.
5. **Electrode Design & Insulation:** Screws were mounted at the high-voltage output terminals and insulated with tape up to their sharp points to define the spark gap and concentrate the electric field at the tips for reliable arc discharge.



<img width="1500" height="2000" alt="image" src="https://github.com/user-attachments/assets/8e28129c-c05e-4ed8-89f2-52b842d1e07e" />





<img width="1500" height="2000" alt="image" src="https://github.com/user-attachments/assets/d1e0aac6-85fc-4f1a-9ca6-062c556b7261" />




https://github.com/user-attachments/assets/7aa8440c-598a-410e-8167-74bb529b6d7c







---
