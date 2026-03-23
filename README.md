# Nigeria Systemic Shocks Analysis: Climate, Conflict, and Macroeconomic Degradation (2010–2024)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data_Processing-green.svg)
![Status](https://img.shields.io/badge/Status-Complete-success.svg)
![Academic Level](https://img.shields.io/badge/Level-Master's_Research-purple.svg)

## 📌 Project Overview
This repository contains the end-to-end Extract, Transform, and Load (ETL) pipelines and analytical master datasets for researching the **Causal Chain of Systemic Shocks in Nigeria**. 

The primary objective of this project is to analyze the intersection of environmental triggers (droughts/floods) and sociopolitical conflict, and measure their cascading impacts on localized food security (staple market prices) and ultimate macroeconomic well-being (GDP per capita).

### The Causal Hypothesis
`Environmental Shock (Drought) ➔ Market Shock (Food Inflation) ➔ Societal Unrest (Riots) ➔ Macroeconomic Impact (GDP Decline)`

---

## 🗄️ Data Provenance & Methodology
To ensure high academic distinction and triangulation, this project integrates four independent data sources:

1. **Environmental (EM-DAT & Meteorological Data):** Disaster episodes recorded by CRED, heavily augmented with peer-reviewed meteorological indices (Shiru et al., 2020) to capture "hidden" agricultural dry spells affecting 21 frontline states.
2. **Market Economics (WFP):** Longitudinal staple food price monitoring (Maize, Rice) normalized to standardize unit weights.
3. **Societal Conflict (ACLED):** Filtered explicitly for civil unrest (Riots, Protests) and violence against civilians to isolate economic grievances from state-on-state military operations.
4. **Macroeconomics (World Bank):** GDP per capita (Current USD) to measure the ultimate degradation of national purchasing power and currency devaluation.

---

## 📂 Repository Structure

```text
nigeria-systemic-shocks-analysis/
│
├── data/                          
│   ├── 01_raw/                    # Original, untouched source files (Excluded via .gitignore if >100MB)
│   ├── 02_processed/              # Cleaned and standardized intermediate files
│   └── 03_master/                 # Dashboard-ready integrated datasets
│       ├── nigeria_analytical_master.csv
│       └── data_provenance_audit.csv
│
├── notebooks/                     # Jupyter Notebooks for ETL processing
│   ├── 01_WFP_Staple_Prices_ETL.ipynb
│   ├── 02_ACLED_conflict.ipynb
│   ├── 03_nigeria_drought_master.ipynb
│   ├── 04_etl_pipeline_world_bank_gdp_2010_2024.ipynb
│   └── 05_Grand_Merge_.ipynb
│
├── dashboard/                     # BI Artifacts and Data Visualizations
├── docs/                          # Academic documentation and data dictionaries
├── requirements.txt               # Python dependencies
└── README.md                      # Project documentation