# Big Data Analysis: Measuring Z Boson Mass from 7.6 Million CERN Proton-Proton Collision Data

A Python-based big data computational physics data analysis project that measures the Z boson mass using ATLAS Open Data from the Large Hadron Collider (LHC). The project demonstrates **large-scale data processing**, **statistical fitting with Cauchy distributions**, and **particle physics analysis** on 550,000 collision events producing 1.1 million rows X 7 columns of data.

**Key Libraries:** `pandas`, `Numpy`, `SciPy` ((for curve fitting and statistics)), `matplotlib`, `uproot`

## 🎯 Project Overview

The goal of this project was to analyze ATLAS Open Data from CERN's LHC to **measure the Z boson mass ($m_Z$)** using muon-pair events (Z→μ⁺μ⁻) from 550,000 proton-proton collisions, and compare the determined mass to the PDG value. This was done by:

1. **Data Selection & Filtering:** Applied particle selection criteria to isolate Z boson decay events from background processes
2. **Invariant Mass Reconstruction:** Calculated the invariant mass of muon pairs from kinematic data
3. **Statistical Fitting:** Used Cauchy distributions to model the Z boson resonance peak
4. **Uncertainty Analysis:** Determined measurement precision and compared with established values

## 📊 Key Results

### Z Boson Mass Measurement
The experimental value Z-boson mass was determined to be: **$m_Z = 91300 \pm 6.83  \text{MeV}/c^2$**

This represents a significant improvement over initial selection methods, reducing the deviation from PDG value ($91187 \pm 4.13  \text{MeV}/c^2$) from 441.6 MeV/c² to 112.4 MeV/c².

## ⚙️ How It Works: Analysis Pipeline

The analysis is structured in a clear pipeline within the `Codes` directory:

1. **Data Selection & Filtering:** Applied selection criteria to 7.6M collision events
   - Opposite charge muons for Z boson analysis
   - Transverse momentum cuts: $39,990 < p_T < 560,000  \text{MeV}/c$
   - Pseudorapidity range: $0.2 < |η| < 2.20$
   - **Result:** Reduced dataset from 7,689,598 to 1,732,276 entries (77.46% background rejection)

2. **Invariant Mass Reconstruction:** Calculated $m_{μ^+μ^-} = \sqrt{E^2 - |\vec{p}|^2}$ for muon pairs

3. **Statistical Fitting:** Used Cauchy (Breit-Wigner) distribution to model Z boson resonance:
   $$
   f(E_{μ^+μ^-}) \propto \frac{1}{(E_{μ^+μ^-} - m_Z)^2 + (\frac{\Gamma_Z}{2})^2}
   $$

![Invariant Mass Distribution](Results_Plots/z_boson_mass_fit.png)
*Figure 1: Invariant mass distribution of muon pairs fitted with Cauchy distribution*

## 📁 Repository Structure

A high-level overview of the project organization:
big-data-analysis-7.6-million-cern-collisions/
│
├── Data/
│ └── ATLAS Open Data files and processed datasets.
│ - Original .root files from CERN Open Data
│ - Processed CSV files with filtered events
│ - Muon pair event selections
│
├── Codes/
│ └── The core analysis scripts and notebooks.
│ - z_boson_analysis.py: Main Python script for Z boson mass measurement
│ - data_processing.ipynb: Jupyter notebook for data filtering and selection
│ - statistical_analysis.ipynb: Notebook with detailed statistical methods and fitting
│ - The complete workflow includes: data selection, invariant mass calculation, and statistical fitting.
│
├── Results_Plots/
│ └── Final publication-quality figures output by the scripts.
│ - Invariant mass distributions with fitted curves
│ - Momentum and pseudorapidity distributions
│ - χ² analysis results
│
└── README.md

text

## 🛠️ Technical Implementation

- **Language:** Python
- **Key Libraries:** `pandas`, `numpy`, `scipy` (for curve fitting and statistics), `matplotlib`, `uproot` (for ROOT file processing)
- **Core Techniques:** Large-scale data filtering, statistical curve fitting (Cauchy distribution), invariant mass reconstruction
- **Data Scale:** Processed 7.6 million collision events with efficient memory management

## 👨‍💻 Skills Demonstrated

This project showcases **directly transferable big data analysis skills**:

### 📊 Big Data Processing
- Handled 7.6 million particle collision events with optimized memory usage
- Implemented efficient event selection criteria reducing dataset by 77.46%
- Processed CERN ROOT data formats and converted to analyzable structures

### 📈 Statistical Analysis & Modeling
- Applied Cauchy (Breit-Wigner) distribution fitting for resonance peak identification
- Performed χ² minimization to determine optimal Z boson mass
- Implemented uncertainty propagation for mass measurements

### 🔧 Programming & Technical Skills
- **Python Data Stack:** `pandas` for large-scale data manipulation, `numpy` for numerical computations, `scipy` for statistical fitting
- **Data Visualization:** Created professional physics plots with `matplotlib`
- **Big Data Tools:** Processed ROOT files with `uproot` library
- **Reproducible Research:** Jupyter notebooks with complete analysis documentation

### 🎯 Physics Data Analysis
- Particle selection criteria development (transverse momentum, pseudorapidity, charge)
- Invariant mass reconstruction from four-vectors
- Background rejection and signal isolation techniques
- Experimental particle physics methodology

## 👨‍💻 View the Analysis Code

For insight into the big data processing and statistical analysis—including event selection criteria, curve fitting methodology, and significance calculation—see the main analysis notebook:
**[statistical_analysis.ipynb](Codes/statistical_analysis.ipynb)**

The code includes detailed explanations of:

-ROOT data file processing with uproot
-Four-vector reconstruction and invariant mass calculation
-Cauchy distribution fitting and χ² minimization
-Uncertainty propagation and result visualization
## 🔬 Note on Academic Integrity

This repository contains the **code and data** for the project. The formal lab report, which contains the detailed theoretical background and full discussion, is not yet published here to uphold my academic institution's integrity policies. The code and results presented here demonstrate the technical implementation and data analysis skills developed in this project.

## 👤 Author

**Valen Lebepe**  
- GitHub: [@ValenLebepe](https://github.com/ValenLebepe)
- LinkedIn: [Valen Lebepe](https://www.linkedin.com/in/valenlebepe)  
- Email: valenlebepe@gmail.com
