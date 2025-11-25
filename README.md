# Advanced Thermo-responsive Polymer Drug Delivery System using Machine Learning
## Overview

This repository contains a MATLAB GUI for simulation and analysis of thermoresponsive polymer-based drug delivery systems. The application predicts drug loading capacity, release efficiency, swelling ratio, hemolysis, cell viability, and more. It supports single and dual polymer analysis, combination studies, and direct model validation against published experimental data.

## Features

- Four analysis modes: Single Polymer, Dual Polymer Comparison, Polymer Combination, Model Validation
- Predicts drug release, cell viability, hemolysis, swelling ratio, drug loading capacity, and biocompatibility score
- Visualizes polymer combination results with heatmaps and bar plots
- Auto-fills literature reference values and supports manual input
- Validation with reference literature values and error metrics
- Sample screenshots and datasets included

## How To Run

1. Requirements:
    - MATLAB R2020a or later
    - Statistics and Neural Network Toolboxes
2. Clone or download this repository.
3. Open `main.m` in MATLAB and Run.
4. Use the GUI for analysis and visualization.

## Dataset Description
This project dataset contains 650 samples, compiled from published research and synthetic simulation, with each row representing one polymer/drug formulation and experimental or simulated outcome.
Please refer to the 'Data' folder for more information

## Output Formulae
- **Drug Loading Capacity (%)-**
  Drug Loading = 15 × LCST_Factor × Crosslinker_Factor × Size_Factor × pH_Factor
  LCST_Factor = 1 + 0.02 × (LCST - 30)
  Crosslinker_Factor = 1 / (1 + 1.5 × Crosslinker Ratio)
  Size_Factor = 1 + (200 - Particle Size) / 1000
  pH_Factor = 1 + 0.03 × |pH - 7.4|
- **Release Efficiency (%)-**
  0.6 × Drug Release(72h) + 0.3 × Cell Viability(24h) + 0.1 × [100 - 10 × Hemolysis]
- **Swelling Ratio-**
  2 + 12 × TempFactor × CrosslinkerFactor × pHFactor
  TempFactor = 1 + (LCST - Temp)/15 (if Temp < LCST), else 1 + (LCST - Temp)/10
  CrosslinkerFactor = 1 / (1 + 2 × Crosslinker Ratio)
  pHFactor = 1 + 0.05 × |pH - 7.4|
- **Biocompatibility Score -**
  Cell Viability(24h) - 8 × Hemolysis + IC50 Bonus
  IC50 Bonus = min(20, max(0, (50 - IC50) × 0.4))

  







