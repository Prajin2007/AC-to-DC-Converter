# ⚡ AC to DC Converter PCB

A full-wave bridge rectifier circuit designed in KiCad, converting AC mains input to filtered DC output with a power indicator LED.

---

## 📌 Overview

This PCB implements a classic **full-wave bridge rectifier** using four 1N4007 diodes, a 1000µF smoothing capacitor, and a power-on LED indicator. Designed as a foundational power electronics project to learn KiCad schematic capture and PCB layout.

---

## 🔧 Specifications

| Parameter | Value |
|:----------|:------|
| Topology | Full-wave Bridge Rectifier |
| Input | AC (via screw terminal J1) |
| Output | Filtered DC (via screw terminal J2) |
| Rectifier Diodes | 4x 1N4007 |
| Filter Capacitor | 1000µF electrolytic |
| Power Indicator | LED (D5) with 2.2k series resistor |
| Bleeder Resistor | 10k (R2) |
| EDA Tool | KiCad |

---

## 🗂️ Repository Structure

```
ac-to-dc-converter/
├── README.md
├── schematic/
│   └── ac-dc-converter.kicad_sch
├── pcb/
│   └── ac-dc-converter.kicad_pcb
├── gerbers/
│   └── (manufacturing files)
├── images/
│   ├── schematic.png
│   ├── pcb-layout.png
│   └── 3d-render.png
└── bom.csv
```

---

## 🧠 How It Works

```
AC Input (J1)
     │
     ▼
┌─────────────────┐
│  Bridge Rectifier│  ← D1, D2, D3, D4 (1N4007)
│  (Full-wave)     │     converts AC → pulsating DC
└────────┬────────┘
         │
         ▼
   ┌─────────┐
   │  C1     │  ← 1000µF smoothing capacitor
   │ 1000µF  │     reduces ripple voltage
   └────┬────┘
        │
        ├──── R1 (2.2k) + D5 (LED) → Power indicator
        │
        ├──── R2 (10k) → Bleeder resistor (discharges cap safely)
        │
        ▼
  DC Output (J2)
```

1. **Bridge rectifier** — four 1N4007 diodes arranged so both halves of the AC cycle contribute to DC output
2. **Filter capacitor** — 1000µF electrolytic smooths the pulsating DC into steady DC
3. **LED indicator** — lights up when DC output is present, with 2.2k current-limiting resistor
4. **Bleeder resistor** — 10k resistor safely discharges the capacitor when power is removed

---

## 🧩 Bill of Materials

| Ref | Component | Value | Package |
|:----|:----------|:------|:--------|
| D1, D2, D3, D4 | Rectifier Diode | 1N4007 | DO-41 |
| D5 | LED | Any colour | 5mm / 3mm |
| C1 | Electrolytic Capacitor | 1000µF | Radial |
| R1 | Resistor | 2.2k | 0805 / Through-hole |
| R2 | Resistor | 10k | 0805 / Through-hole |
| J1 | Screw Terminal | AC Input | ScreW_Terminal_01x02 |
| J2 | Screw Terminal | DC Output | Screw_Terminal_01x02 |

---

## 🖼️ Screenshots

### Schematic
<img width="822" height="486" alt="Screenshot 2026-06-28 101313" src="https://github.com/user-attachments/assets/786e667d-b55e-4c79-a09a-5e58bed32cb9" />


### PCB Layout
<img width="797" height="583" alt="Screenshot 2026-06-28 101259" src="https://github.com/user-attachments/assets/b8a411c8-714d-462c-8fd7-dc3d87265f0b" />


### 3D Render
<img width="976" height="815" alt="Screenshot 2026-06-28 101251" src="https://github.com/user-attachments/assets/53008a4c-4771-4e44-af1e-919c189a51b3" />


---

## 🛠️ Tools Used

![KiCad](https://img.shields.io/badge/KiCad-314CB0?style=flat-square&logo=kicad&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)

---

## 📚 What I Learned

- KiCad schematic capture and symbol placement
- Full-wave bridge rectifier theory and component selection
- Filter capacitor sizing for ripple reduction
- PCB layout, component footprint assignment and DRC
- Exporting Gerber files for manufacturing

---

## 👤 Author

**Prajin S**
B.Tech Electronics and Instrumentation Engineering, VIT Vellore

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Prajin%20S-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/prajin-s-5880b3328/)
[![GitHub](https://img.shields.io/badge/GitHub-Prajin2007-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Prajin2007)

---

*First KiCad PCB design — part of my electronics learning journey.*
