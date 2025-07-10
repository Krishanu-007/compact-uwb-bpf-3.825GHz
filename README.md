# 📡 Design & Analysis of a Compact Ultra-Wideband Microstrip Bandpass Filter (3.825 GHz)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

This repository documents the end-to-end design, simulation, and optimization process for a **compact Ultra-Wideband (UWB) microstrip bandpass filter** centered at **3.825 GHz**, conducted during a research training program at **ISRO – Space Applications Centre (SAC)**.

> **👤 Author**: Krishanu Bandyopadhyay  
> **🛰 Host Organization**: Space Applications Centre (ISRO), Ahmedabad  
> **📅 Duration**: 03 March 2025 – 20 May 2025  
> **🧑‍🏫 Guide**: Sri Vinit Kumar, SCI/ENGR-SG, MSRD, MSRG, MRSA, SAC

---

## 🎯 Objective

To design a **compact, low-loss, wideband microstrip bandpass filter** suitable for C & S-band applications in satellite and radar communication systems, fulfilling strict electrical and physical constraints.

| Parameter                  | Specification                        |
|---------------------------|--------------------------------------|
| Center Frequency          | 3.825 GHz                            |
| Passband                  | 2.625 – 5.025 GHz                    |
| Bandwidth (0.3 dB Ripple) | 2.4 GHz                              |
| Insertion Loss            | < 2 dB                               |
| Return Loss               | > 15 dB                              |
| Stopband Rejection        | > 25 dBc (5.55 – 17.25 GHz)          |
| NEB                       | 2400 MHz ±10%                        |
| Layout Constraint         | ≤ 1 inch × 1 inch                    |
| Substrate                 | Alumina (εr = 9.9, TanD = 0.0007)    |
| Conductor                 | Gold (8 µm thickness)                |

---

## 🧰 Tools & Materials

- **Design Tool**: Keysight ADS (Advanced Design System)
- **EM Simulation**: Momentum 2.5D solver
- **Substrate**: Alumina (Al₂O₃)
- **Conductor**: Gold
- **Upper Housing Height**: 11 mm

---

## 🧱 Design Methodology

The filter was designed using an **open-stub topology** based on a **Chebyshev response**. After theoretical analysis and prototype trials of 7th, 6th, and 5th-order filters, the final optimized design was selected and paired with a **Harmonic Rejection Filter (HRF)** to meet out-of-band performance criteria.

---

## 🧾 Design Progression

### 🔹 7th Order Open-Stub BPF
- Initial high-order design using Chebyshev response.
- ✅ Targeted electrical specs
- ❌ Oversized (>1×1 inch), high return loss

---

### 🔹 6th Order Open-Stub BPF
- Reduced complexity to improve layout and performance.
- ✅ Improved passband shaping
- ❌ Return loss still not ideal

---

### 🔹 5th Order Open-Stub BPF
- Optimized balance between performance and area.
- ✅ Fits within 1 inch × 1 inch
- ✅ Meets ripple and insertion loss targets

---

### 🔹 7th Order Harmonic Rejection Filter (HRF)
- Designed to suppress 2nd and 3rd order harmonics.
- ✅ Uses open stubs, λg/4 and λg/2 sections
- ✅ Co-simulated with BPF using:
  - T-section matching
  - Stepped impedance networks
- ✅ Achieved >25 dBc rejection in 5.55–17.25 GHz range

---

### 🔹 Final Optimized Filter (BPF + HRF + Tuning Pads)
- Combines the 5th order BPF with 7th order HRF.
- Adds tuning pads for practical fabrication tolerances.
- ✅ Fully EM simulated and validated

---

## 📈 Performance Highlights

| Metric              | Achieved Result     |
|---------------------|---------------------|
| Insertion Loss      | ~1.75 dB            |
| Return Loss (S11)   | > 17 dB             |
| Return Loss (S22)   | > 15 dB             |
| NEB                 | 2400 MHz ±10%       |
| Area Fit            | ✅ Yes (<1×1 inch)  |
| Harmonic Suppression | > 25 dBc (5.55–17.25 GHz) |

---

## 🧠 Key Design Decisions

- **Why Open-Stub?**
  - Compact, wideband-compatible
  - Low conductor loss
  - EM-tunable and compatible with λg-based lengths

- **Why Not Hairpin/Coupled Line?**
  - Difficult to meet wideband specs in <1 inch²
  - Tight coupling → fabrication risk
  - Inefficient for 60%+ fractional bandwidth

- **Why Add HRF?**
  - UWB filters inherently produce higher-order harmonics.
  - HRF ensures regulatory compliance and better integration with front-ends.


Each folder contains:
- `schematic.png` – Topology-level schematic
- `layout.png` – Microstrip layout
- `s_params.png` – S11/S21 simulation results
- `notes.md` – Design summary and evaluation

---

## 🔮 Future Work

- Fabrication and measurement validation
- Explore multilayer/multiband integration
- Investigate tunability via MEMS or varactor loading
- Co-design with antenna systems

---

## 📚 References

- Pozar, D.M. – *Microwave Engineering* 
- Hong & Lancaster – *Microstrip Filters for RF/Microwave Applications* 
- Keysight ADS Documentation 
- Literature studies referenced in `report_reference.txt`

---

## 📜 License

This repository is intended for academic, research, and demonstration purposes. 
Feel free to fork and share with proper attribution.

**© 2025 Krishanu Bandyopadhyay**

