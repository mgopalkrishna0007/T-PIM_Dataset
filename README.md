# T-PIM Dataset

This repository contains the **Transmissive Polarization-Insensitive Metasurface (T-PIM)** datasets and implementation of the **PIM-CNN** deep learning model for inverse metasurface filter design.  
It supports both **Normally Pixelated (NP-PIM)** and **Complex Pixelated (CP-PIM)** configurations across **15 GHz**, **28 GHz**, and **79 GHz** center frequencies.
![final-flow](https://github.com/user-attachments/assets/2b998fcb-2a75-4f0b-9993-15349364ae8d)


## 📥 Dataset Access

The **T-PIM Dataset** is available here:  
🔗 **[T-PIM Dataset](https://drive.google.com/drive/folders/14NpCbfqlzJvdVdeMERzPV9GO3-yTIyiO?usp=sharing)**  

The folder contains:
- **NP-PIM** datasets (15 GHz, 28 GHz, 79 GHz)
- **CP-PIM** datasets (15 GHz, 28 GHz, 79 GHz)  

Please download and place them inside the corresponding `datasets/` subfolders

Dataset is generated using **full-wave electromagnetic (EM) simulations** in **CST Microwave Studio** via a **Python API**.

The designs are based on **PEC patches** on an **FR-4 substrate** with:
- Relative permittivity: εr = 4.3
- Loss tangent: tan δ = 0.025
- Thickness: 0.8 mm

Periodic boundary conditions are applied along the **x** and **y** axes, with expanded open boundaries along **z**.  
The datasets span:
- **15 GHz** (5–25 GHz range)
- **28 GHz** (18–38 GHz range)
- **79 GHz** (69–89 GHz range)

---

## 🧩 Dataset Categories

### **1. Normally Pixelated PIM (NP-PIM)**
- Binary grid: `0` → no metal, `1` → PEC patch
- Symmetry: **8-fold rotational symmetry** applied to reduce design space complexity
- Base pattern: **1/8 of the unit cell (right triangle)**

**Datasets:**
- [15 GHz Dataset](#)  
- [28 GHz Dataset](#)  
- [79 GHz Dataset](#)  

---

### **2. Complex Pixelated PIM (CP-PIM)**
- Ternary grid:  
  - `0` → no metal  
  - `1` → PEC patch  
  - `2` → complex features (rings, circular slots, Jerusalem cross slots)
- Symmetry: **8-fold rotational symmetry**
- Base pattern: **1/8 of the unit cell**

**Datasets:**
- [15 GHz Dataset](#)  
- [28 GHz Dataset](#)  
- [79 GHz Dataset](#)  

![finaldesign](https://github.com/user-attachments/assets/65053421-4dcb-4547-a359-6936a33787e4)


## 📊 Dataset Format

Each dataset entry contains:
- **Base pattern**: 1/8 unit cell binary/ternary encoding
- **Full unit cell configuration** (after symmetry expansion)
- **S-parameters**: S11, S21, S12, S22
- **Transmission Efficiency (TE)**:
  
  \[
  TE = \frac{|S_{ZMin1,ZMax1}|^2}{|S_{ZMin1,ZMax1}|^2 + |S_{ZMax1,ZMax1}|^2}
  \]

- **Frequency response**: 501 frequency points per simulation
- **Stored format**: `.pkl`


![RESULTS2 (1)](https://github.com/user-attachments/assets/378c5d79-2e1e-406b-8fae-e06069f06ca6)
