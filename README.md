# CFD and Fluent Meshing Study: T-Tail Aircraft Aerodynamics

This repository contains the ANSYS Fluent meshing journals, setup files, and related documentation for a computational aerodynamics study of a T-tail aircraft configuration. The project focuses on:

- **Cruise performance analysis** at Mach 0.8 and 30,000 ft altitude.
- **Deep stall investigation** at high angles of attack (20°, 22.5°, 25°).
- **Comparison of aerodynamic tools**: VSPAero (panel method) vs. ANSYS Fluent (CFD).
- **Turbulence modelling** using k-ω SST and k-kl transition models.

## 📁 Repository Structure

## ✈️ Project Overview

The study analyses the aerodynamic behaviour of a DC-9-type T-tail aircraft in both normal cruise and deep stall conditions. Deep stall is a critical safety concern for T-tail configurations where the horizontal stabiliser becomes immersed in the separated wake of the main wing, leading to loss of pitch control.

### Key Objectives:
1. Identify the optimal cruise angle of attack for maximum L/D ratio.
2. Evaluate deep stall characteristics at high AoA.
3. Compare fast panel methods (VSPAero) with high-fidelity CFD (Fluent).
4. Assess turbulence model performance (k-ω SST vs. k-kl transition).

## 🛠️ Computational Setup

### Geometry & Mesh
- Aircraft: DC-9-like T-tail configuration.
- Half-model symmetry used to reduce computational cost.
- **Mesh size**: ~3.1 million cells (coarse due to computational constraints).
- **Mesh type**: Poly-hexcore with prism layers for boundary resolution.
- **Mesh quality**: Skewness < 0.66, orthogonality > 0.45.

### Solver Settings
- **Solver**: ANSYS Fluent (density-based, explicit).
- **Turbulence models**: k-ω SST and k-kl transition.
- **Mach number**: 0.8 at 30,000 ft (ISA conditions).
- **Reynolds number**: ~2.06 × 10⁷ based on mean aerodynamic chord.

### Boundary Conditions
- **Inlet**: Velocity inlet with AoA specification.
- **Outlet**: Pressure outlet.
- **Walls**: No-slip condition for aircraft surfaces.
- **Symmetry**: Symmetry plane for half-model.

## 📊 Key Findings

1. **Cruise Performance**:
   - Optimal L/D occurs at **2° angle of attack**.
   - VSPAero over-predicts lift and under-predicts drag compared to CFD.

2. **Deep Stall Analysis**:
   - At 25° AoA, lift coefficient drops to near-zero.
   - Drag coefficient increases by an order of magnitude.
   - Horizontal tail experiences significant wake ingestion, confirming deep stall risk.

3. **Tool Comparison**:
   - VSPAero is useful for rapid trend analysis but lacks viscous flow modelling.
   - CFD provides physically realistic predictions, essential for safety-critical analyses like deep stall.

## 📈 Results Visualization

*(Example plots to include in repo)*
- Lift and drag coefficients vs. AoA.
- Pressure contours and streamlines at cruise and deep stall.
- Comparison bar charts: VSPAero vs. Fluent.

## ⚠️ Limitations & Notes

- Mesh resolution was limited (~3.1M cells); transition modelling requires finer near-wall resolution (y+ ≈ 1).
- Engine nacelles were omitted from the model due to an oversight in geometry preparation.
- k-ω SST model showed convergence issues; k-kl transition model performed more robustly.

## 🔗 References

1. Skybrary, *Deep Stall* – [https://skybrary.aero/articles/deep-stall](https://skybrary.aero/articles/deep-stall)
2. OpenVSP Documentation – [https://openvsp.org/wiki/doku.php](https://openvsp.org/wiki/doku.php)
3. Anderson, J. D., *Fundamentals of Aerodynamics* (6th ed.), McGraw-Hill, 2017.
4. Menter, F. R., *Two-Equation Eddy-Viscosity Turbulence Models for Engineering Applications*, AIAA Journal, 1994.

## 👨‍🔬 Author
**Saiyed Mohammad Mudassir**  
MSc Aerospace Computational Engineering, Cranfield University (2024–2025)  
Project Supervisor: Tom Robin Teschner  
Date: 2nd December 2024

## 📄 License
This project is shared for academic and research purposes. Please cite appropriately if used in further work.
