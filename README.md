# Big Data Analysis: Measuring Z Boson Mass from 7.6 Million CERN Proton-Proton Collision Data

A Python-based big data computational physics data analysis project that measures the Z boson mass using ATLAS Open Data from the Large Hadron Collider (LHC). The project demonstrates **large-scale data processing**, **statistical fitting with Cauchy distributions**, and **particle physics analysis** on 550,000 collision events producing 1.1 million rows X 7 columns of data.

**Key Libraries:** `pandas`, `Numpy`, `SciPy` (for curve fitting and statistics), `matplotlib`, `uproot`

## 🎯 Project Overview

The goal of this project was to analyze ATLAS Open Data from CERN's LHC to **measure the Z boson mass ($m_Z$)** using muon-pair events (Z→μ⁺μ⁻) from 550,000 proton-proton collisions, and compare the determined mass to the PDG value. This was done by:

1. **Data Selection & Filtering:** Applied particle selection criteria to isolate Z boson decay events from background processes
2. **Invariant Mass Reconstruction:** Calculated the invariant mass of muon pairs from kinematic data
3. **Statistical Fitting:** Used Cauchy distributions to model the Z boson mass distribution 
4. **Uncertainty Analysis:** Determined measurement precision and compared with established values

## 📊 Key Results

The experimental value Z-boson mass was determined to be: **$m_Z = 91300 \pm 6.83  \text{MeV}/c^2$**

This represents a significant improvement over initial selection methods, reducing the deviation from PDG value ($91187 \pm 4.13  \text{MeV}/c^2$) from 441.6 MeV/c² to 112.4 MeV/c².

![mz Boson mass vs PDG](https://github.com/ValenLebepe/big-data-analysis-7.6-million-data-from-cern-proton-proton-collisions/blob/main/Results/mZ%20boson%20mass%20compared%20to%20PDG.png)

*Figure 1: Comparison of the experimetally determined Z boson mass with the PDG value of the Z boson mass.*

## ⚙️ How It Works: Analysis Pipeline

The analysis is structured in a clear pipeline within the `Codes` directory:

1. **Data Selection & Filtering:** Applied the following selection criteria to 7.6M collision events
   - Opposite charge muons for Z boson analysis
   - Transverse momentum cuts: $39,990 \text{MeV}/c < p_T < 560,000  \text{MeV}/c$
   - Pseudorapidity range: $0.2 < |η| < 2.20$
   - **Result:** Reduced dataset from 7,689,598 to 1,732,276 entries (77.46% background rejection)
     
![momentum distribution of muon 1](https://github.com/ValenLebepe/big-data-analysis-7.6-million-data-from-cern-proton-proton-collisions/blob/main/Results/momentum%20distribution%20of%20muon%201.png)

*Figure 2: Momentum distribution of muon 1 after applying the selection criteria of opposite charge,transverse momentum 39,990𝑀𝑒𝑉/ 𝑐 < 𝑝𝑇 < 560,000𝑀𝑒𝑉/𝑐.*

![pseudorapidity distribution of muon 1](https://github.com/ValenLebepe/big-data-analysis-7.6-million-data-from-cern-proton-proton-collisions/blob/main/Results/pseudorapidity%20distribution%20of%20muon%201.png)

*Figure 3: Pseudorapidity distribution of muon 1 after applying the selection criteria of opposite charge,transverse momentum 39,990𝑀𝑒𝑉/ 𝑐 < 𝑝𝑇 < 560,000𝑀𝑒𝑉/𝑐 and pseudorapidity 0.2 <∣ 𝜂 ∣< 2.20.*

2. **Invariant Mass Reconstruction:** Calculated using the equation $m_{μ^+μ^-} = \sqrt{E^2 - |\vec{p}|^2}$  

3. **Statistical Fitting:** Used Cauchy (Breit-Wigner) distribution to model and determine the Z boson mass distribution:
   
   $$f(E_{\mu^+\mu^-}) \propto \frac{1}{(E_{\mu^+\mu^-} - m_Z)^2 + \left(\frac{\Gamma_Z}{2}\right)^2}$$

![Invariant Mass Distribution](https://github.com/ValenLebepe/big-data-analysis-7.6-million-data-from-cern-proton-proton-collisions/blob/main/Results/mZ%20boson%20mass%20distribution%20fitted%20with%20a%20cauchy.png)

*Figure 4: Invariant mass distribution of muon pairs fitted with Cauchy distribution*

## 📄 Project Report

A detailed technical report documenting the full methodology, theoretical background, and discussion is available here:  
[**Rediscovering the Higgs Boson Report**](https://github.com/ValenLebepe/big-data-analysis-7.6-million-data-from-cern-proton-proton-collisions/blob/main/Reports/Report.pdf)

**Report Highlights:**
- Comprehensive theoretical background on particle physics and proton-proton collisions
- Detailed experimental methodology and apparatus description
- Complete error analysis and uncertainty discussion
- Comparison with accepted literature values


## 📁 Repository Structure

A high-level overview of the project organization:
```
big-data-analysis-7.6-million-cern-collisions/
│
├── Data/
│ └── ATLAS Open Data files and processed datasets.
│    - Original .root files from CERN Open Data
│    - Processed CSV files with filtered events
│ 
│
├── Codes/
│ └── The core analysis scripts and notebooks.
│    - zboson_mass_analysis.ipynb: Main Python script for Z boson mass 
│
├── Results_Plots/
│ └── Final publication-quality figures output by the scripts.
│    - Invariant mass distributions with fitted curves
│    - Momentum and pseudorapidity distributions
│    - χ² analysis results
│
├── Reports/
│   └── Project documentation and technical report
│       - Report.pdf
|
└── README.md
```


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
- **Python Data Stack:** `pandas` for large-scale data manipulation, `numpy` for numerical computations, `scipy` for statistical fitting and analysis
- **Data Visualization:** Created professional physics plots with `matplotlib`
- **Big Data Tools:** Processed ROOT files with `uproot` library
- **Reproducible Research:** Jupyter notebooks with complete analysis documentation

### 🎯 Physics Data Analysis
- Particle selection criteria development (transverse momentum, pseudorapidity, charge)
- Invariant mass reconstruction from four-vectors
- Background rejection and signal isolation techniques
- Experimental particle physics methodology

## 👨‍💻 View the Analysis Code

For insight into the big data processing and statistical analysis including event selection criteria, curve fitting methodology, and visualization, see the main analysis notebook:
**[mZ boson_analysis.ipynb](Codes/zboson_mass_analysis.ipynb)**

The code includes detailed explanations of:

- ROOT data file processing with uproot
- Four-vector reconstruction and invariant mass calculation
- Cauchy distribution fitting and χ² minimization
- Uncertainty propagation and result visualization

## 📄 License

**Report:** Copyright © 2025 [Valen Lebepe]. All rights reserved.
This report is provided for viewing purposes only. Redistribution, copying, 
or commercial use is prohibited without explicit permission.

## 👤 Author

**Valen Lebepe**  
- GitHub: [@ValenLebepe](https://github.com/ValenLebepe)
- LinkedIn: [Valen Lebepe](https://www.linkedin.com/in/valenlebepe)  
- Email: valenlebepe@gmail.com
