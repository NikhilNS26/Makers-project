# ⚡ Energy Consumption Analysis of the Ender-3 3D Printer

This repository contains the code, experimental dataset, and report for a study analyzing the energy consumption of the **Creality Ender-3 FFF 3D printer**, using the **PZEM-017 DC energy measurement module**. The objective of this work is to quantify subsystem-level power usage and evaluate strategies for energy optimization to support sustainable additive manufacturing.

---

## 📌 Overview

Fused Filament Fabrication (FFF) 3D printing is widely adopted, yet its energy profile—especially at the consumer printer scale—is under-studied. This project measures and analyzes energy consumption across different print configurations and hardware adjustments, including:

* Variation in **layer height** (0.1 mm, 0.2 mm, 0.3 mm)
* Impact of disabling heating components
* Effectiveness of heated-bed insulation
* Subsystem energy decomposition using controlled operating modes

All experiments were performed using benchmark models under consistent controlled conditions.

---

## 📂 Repository Structure

```
📁 Repository Root
│
├── 📁 Code
│     ├── PZEM Code
│     └── Analysis Code
│
├── 📁 CSV
│     ├── baseline_l1_modified.csv
│     ├── baseline_l2_modified.csv
│     ├── baseline_l3_modified.csv
│     ├── Modified_Insulation_result.csv
│     ├── Modified_WIthout_heat_bed.csv
│     └── Modified_without_heatbed_heat_end.csv
│
└── 📄 Report.pdf
```

* **Code Folder:** Contains the energy logging scripts used for communication with the PZEM-017 module and data analysis notebook(s).
* **CSV Folder:** Includes all processed datasets used in analysis and visualization.
* **Report:** Full documentation including methodology, results, and conclusions.
---

## 📑 Key Findings (from the Report)

* The **heated bed and hotend together contribute ~80%** of energy usage.
* Increasing layer height from **0.1 mm → 0.3 mm reduced total energy consumption by ~39%.**
* Applying bed insulation resulted in a **27% reduction** in total energy.
* Ghost print mode demonstrates the motion system consumes only **~16–17%** of total power.

These findings highlight parameter selection and thermal management as primary levers for improving energy efficiency.

---

## 🛠️ Software and Hardware Requirements

### Hardware

* Creality Ender-3 (24V DC supply)
* PZEM-017 Energy Sensor
* RS485-USB converter

### Software

* Python 3.8+
* Required libraries:

  ```
  minimalmodbus
  pandas
  matplotlib
  numpy
  jupyter
  ```

---

## 🚀 How to Use

1. Connect the PZEM-017 module inline with the printer’s 24V supply.
2. Run the data logging script from the `Code` directory.
3. Run analysis using the Jupyter notebook.
4. Compare results using CSV files under the `/CSV` directory.
