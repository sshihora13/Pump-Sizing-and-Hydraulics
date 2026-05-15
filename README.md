# 🔧 Pump Hydraulics & Line Sizing Calculator — API 610

> A complete **pump hydraulic calculation and pipe sizing tool** built in Excel, covering friction factor methods (Blasius, Swamee-Jain, Haaland), pressure drop calculations, NPSH analysis, and pump power sizing — following **API 610** standards.

---

## 📌 Overview

This Excel workbook provides a full hydraulic calculation framework for centrifugal pump systems. It covers line sizing with three friction factor correlations, fitting and valve losses, suction/discharge hydraulics, NPSH availability, and motor power estimation.

| Parameter | Value |
|-----------|-------|
| Software | Microsoft Excel |
| Standard | API 610 (Centrifugal Pumps) |
| Pump Tag | P-101 |
| Service Fluid | Ethylene Dichloride |
| Flow Rate | 220 m³/hr |
| Sheets | 3 (Line Sizing · Pump Hydraulics · Notes) |

---

## 📐 Sheet 1 — Line Sizing & Pressure Drop Calculator

### Input Data

| Parameter | Value | Unit |
|-----------|-------|------|
| Fluid | Ethylene Dichloride | — |
| Pipe internal diameter (D) | 8 inch / 0.2032 | m |
| Pipe length (L) | 50 | m |
| Flow rate (Q) | 220 | m³/hr |
| Density (ρ) | 853 | kg/m³ |
| Dynamic viscosity (μ) | 0.0674 | Pa·s |
| Absolute roughness (ε) | 0.045 mm / 0.000045 | m |

### Intermediate Calculations

| Parameter | Value | Unit |
|-----------|-------|------|
| Cross-sectional area (A = πD²/4) | 0.032429 | m² |
| Flow velocity (v = Q/A) | 1.884 | m/s |
| Reynolds number (Re = ρvD/μ) | 4,846 | — |
| Relative roughness (ε/D) | 0.000221 | — |
| Flow regime | **Turbulent** | — |

### Friction Factor Results — Three Methods

| Method | Darcy f (f_D) | Fanning f (f_F) | ΔP (Pa) | ΔP (bar) |
|--------|--------------|----------------|---------|---------|
| **Blasius** (smooth, turbulent) | 0.037922 | 0.009480 | 14,132 | 0.1413 |
| **Swamee-Jain** (explicit Colebrook) | 0.038487 | 0.009622 | 14,343 | 0.1434 |
| **Haaland** (explicit) | 0.038258 | 0.009564 | 14,258 | 0.1426 |

> All three methods are in close agreement — confirming reliable results. Haaland is recommended for quick calculations; Colebrook-White is the industry standard.

### Fitting & Valve Losses (K-Method)

| Fitting / Valve | K Value | Qty | Pressure Loss (Pa) |
|----------------|---------|-----|-------------------|
| Gate valve (open) | 0.17 | 0 | 0 |
| Globe valve, bevel seat (open) | 6.00 | 0 | 0 |
| Plug valve (open) | 0.40 | 0 | 0 |
| Diaphragm valve (open) | 2.30 | 0 | 0 |
| Angle valve (open) | 2.00 | 0 | 0 |
| Check valve (swing) | 2.00 | 0 | 0 |
| Foot valve | 15.00 | 0 | 0 |
| 90° elbow (long radius) | 0.45 | **1** | **681.5** |
| Strainer | — | **1** | **20,000** |
| **Total Fitting Loss** | | | **20,681.5 Pa / 0.207 bar** |

### System Pressure Drop Summary

| Line / Equipment | Length | ΔP (bar) | Total with Fittings (bar) |
|-----------------|--------|---------|--------------------------|
| Line-1 | 100 m | 0.2869 | 0.5738 |
| Plate-type HEX | — | — | 0.7000 |
| Line-2 | 100 m | 0.2869 | 0.5738 |
| Cooler (Line-3) | — | — | 0.5000 |
| HEX (Line-3) | — | — | 0.7000 |
| Line-3 | 50 m | 0.1434 | 0.2868 |
| Line-4 | 50 m | 0.1434 | 0.2868 |
| Control valve (Line-3) | — | — | 2.4000 |
| Line-5 | 100 m | 0.2869 | 0.5738 |
| Destination tank back-pressure + elevation | — | — | 2.4000 |
| **Total Line Pressure Drop** | | | **2.0082 bar** |
| **Total Component + Equipment** | | | **4.8738 bar** |

---

## 🔩 Sheet 2 — Pump Hydraulic Calculation (API 610)

### General Data — Pump P-101

| Parameter | Value | Unit |
|-----------|-------|------|
| Pump tag | P-101 | — |
| Temperature (min / normal / max) | 70 / 75 / 80 | °C |
| Flow rate | 220 | m³/hr |
| Fluid density | 853 | kg/m³ |
| Fluid viscosity | 0.001 | Pa·s |
| Vapour pressure (Pv) | 0.103 | bar A |
| Suction line size | 10 inch (0.254 m) | m |
| Discharge line size | 8 inch (0.2032 m) | m |
| Suction line length | 6 | m |
| Discharge line length | 200 | m |
| MOC | Commercial steel (ε = 0.000045 m) | — |
| Design pressure margin (suction) | 10 | % |
| MCF flow margin | 20 | % |
| Shutoff head margin | 25 | % |
| Design pressure margin (downstream) | 10 | % |

---

### Suction Side Hydraulics

| Parameter | Value | Unit (bar) | Unit (m) |
|-----------|-------|-----------|---------|
| Operating pressure of suction vessel (P) | 2.800 | bar A | 33.461 m |
| Total elevation of suction vessel | 10.500 | — | 10.500 m |
| HHLL liquid level to pump centreline | 10.500 | 0.879 bar | 10.500 m |
| LL liquid level to pump centreline (Z) | 8.000 | 0.669 bar | 8.000 m |
| Friction loss — suction line (HFs1) | 0.008 | bar A | 0.096 m |
| Friction loss — fittings & instruments (HFs2) | 0.202 | bar A | 2.414 m |
| Vapour pressure (Pv) | 0.103 | bar A | 1.231 m |
| **NPSH Available (NPSH-A)** | **37.721** | **—** | **37.721 m** |
| Suction Head / Suction Pressure | 38.952 | — | 38.952 m |
| Max. Suction Pressure / Max. Operating Pressure | 3.469 | bar A | 41.452 m |
| Design pressure of suction line | 3.815 | bar A | 45.597 m |

---

### Discharge Side Hydraulics

| Parameter | Value | Unit (bar) | Unit (m) |
|-----------|-------|-----------|---------|
| Operating pressure of discharge vessel (P) | 2.400 | bar A | 28.681 m |
| Elevation head (Z) | 9.000 | 0.753 bar | 9.000 m |
| Friction loss — discharge line (HFs1) | 2.008 | bar A | 23.999 m |
| Friction loss — fittings & equipment (HFs2) | 4.874 | bar A | 58.244 m |
| **Total Discharge Pressure** | **10.035** | **bar A** | **119.923 m** |

---

### Pump Performance Summary

| Parameter | Value | Unit |
|-----------|-------|------|
| **Volumetric Flow Rate** | **220** | **m³/hr** |
| **Total Differential Head** | **80.972** | **m** |
| **Total Differential Pressure** | **6.776** | **bar A** |
| Suction Pressure | 3.469 | bar A |
| **Discharge Pressure** | **10.035** | **bar A** |
| **NPSH Available (NPSH-A)** | **37.721** | **m** |
| NPSH Required (NPSH-R) | Vendor specific | m |
| **Shutoff Head** | **142.666** | **m (11.938 bar A)** |
| Downstream components design pressure | 156.933 m | 13.132 bar A |

---

### Pump Power Calculations

| Parameter | Value | Unit |
|-----------|-------|------|
| Pump efficiency | 60 | % |
| Motor efficiency | 90 | % |
| **Hydraulic Power** | **41.404** | **kW** |
| **Brake Horse Power (BHP)** | **69.006** | **kW** |
| **Motor Power Required** | **76.674** | **kW** |

**Formula used:**
```
Hydraulic Power = ρ · g · Q · H / 3,600,000   [kW]
BHP = Hydraulic Power / Pump Efficiency
Motor Power = BHP / Motor Efficiency
```

---

## 📋 Sheet 3 — Reference Data & Notes

### Pipe Roughness Reference (ε values)

| Material | ε (m) |
|----------|-------|
| Smooth drawn tubing / PVC | 0.000002 |
| New steel (very smooth) | 0.000015 |
| **Commercial steel (typical)** | **0.000045** |
| Galvanized iron (rough) | 0.000150 |
| Old cast iron (very rough) | 0.000260 |

### Velocity Guidelines by Fluid Type

| Fluid Type | Suction Velocity (m/s) | Discharge Velocity (m/s) |
|-----------|----------------------|------------------------|
| Water / low-viscosity liquids | 0.5–1.5 | 2–5 |
| High-viscosity liquids | 0.3–1.0 | 1–3 |
| Volatile liquids (hydrocarbons) | ≤ 1.0 | 2–4 |
| Slurries | 1.5–3.0 (min) | 2–5 |
| Corrosive / hazardous fluids | 0.5–1.5 | 1.5–4 |

### Design Pressure Margin (List-2)

| System Type | Margin Above MOP |
|-------------|-----------------|
| Water / utility piping | 10–25% |
| General process systems | 10–30% |
| High fluctuation / transient systems | 20–50% |
| Pumps / surge-prone systems | Surge analysis required |

### Downstream Component Design Pressure Margin (List-3)

| Shutoff Pressure Range | Margin (bar) |
|----------------------|-------------|
| 0–10 bar | 0.1 |
| 10–20 bar | 0.2 |
| 20–50 bar | 0.3 |
| Above 50 bar | 0.5 |

---

## 🧮 Key Formulas Used

| Formula | Expression |
|---------|-----------|
| NPSH(A) | P ± Z − HFs1 − HFs2 − Pv |
| Component loss (HFs2) | K · (ρv²/2) |
| Suction Head | P ± Z − HFs1 − HFs2 |
| Max. Suction Head | P ± HHLL − HFs1 − HFs2 |
| Discharge Head | P + Z + HFs1 + HFs2 |
| Shutoff Pressure | Max. Suction Pressure + (Diff. Pressure × 25%) |
| Blasius (smooth turbulent) | f = 0.316 / Re^0.25 |
| Swamee-Jain | f = 0.25 / [log(ε/3.7D + 5.74/Re^0.9)]² |
| Haaland | 1/√f = −1.8·log[(ε/D/3.7)^1.11 + 6.9/Re] |

---

## 🗂️ File Structure

```
📁 pump-hydraulics-line-sizing/
│
├── README.md           ← This file
├── hydraulics.xlsx     ← Complete hydraulic calculation workbook (3 sheets)
│
└── 📄 Sheet Contents
    ├── Line Sizing     ← Pipe sizing, friction factors, fitting losses, system ΔP
    ├── Pump Hydraulics ← NPSH, suction/discharge heads, power calculations (API 610)
    └── Notes           ← Reference tables: roughness, K-values, velocity guidelines
```

---

## 🔬 Key Engineering Takeaways

1. **Three friction factor methods agree within 1.5%** — confirms robustness of calculation
2. **Strainer dominates fitting losses at 20,000 Pa** — always account for strainer ΔP in suction design
3. **NPSH-A = 37.72 m is well above typical NPSH-R** — pump has excellent cavitation margin
4. **Discharge pressure = 10.04 bar A** — sets the design pressure for all downstream components
5. **Shutoff pressure = 11.94 bar A** — all downstream equipment rated above this value
6. **Motor power = 76.67 kW** — sized at combined pump (60%) + motor (90%) efficiency
7. **Component + equipment losses (4.87 bar) dominate over line losses (2.01 bar)** — control valve and heat exchangers are the system bottleneck

---

## 👨‍🔬 Author

**Satyambhai Shihora**
Chemical Engineering Student — Otto von Guericke Universität Magdeburg
[LinkedIn](https://www.linkedin.com/in/satyamshihora/) · [GitHub](https://github.com/sshihora13)

---

## 📚 References

1. API 610 — Centrifugal Pumps for Petroleum, Petrochemical and Natural Gas Industries
2. Crane Technical Paper 410 — Flow of Fluids Through Valves, Fittings and Pipe
3. Moody, L.F. — Friction Factors for Pipe Flow, ASME Transactions (1944)
4. Swamee, P.K. & Jain, A.K. — Explicit Equations for Pipe-Flow Problems, ASCE Journal (1976)

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).
