# The Burden of Lower Respiratory Infections Attributable to Air Pollution (1990–2021)

**Repository Overview**  
This repository contains all data, code, and results used to quantify and visualize the global burden of lower respiratory infections (LRIs) attributable to air pollution from 1990 to 2021. Analyses adhere to GBD 2021 methodology and follow GATHER guidelines for transparent health‐estimate reporting.

---

## Table of Contents

1. [Project Description](#project-description)  
2. [Folder Structure](#folder-structure)  
3. [Data Sources](#data-sources)  
4. [Key Outputs & Results](#key-outputs--results)  
5. [Dependencies](#dependencies)  
6. [Citation](#citation)  

---

## Project Description

Air pollution—both ambient particulate matter (PM₂.₅) and household air pollution (HAP)—remains a major contributor to morbidity and mortality worldwide. Lower respiratory infections (LRIs) account for a substantial portion of air‐pollution‐attributable health burden. Although the Global Burden of Disease (GBD) Initiative has provided periodic updates on LRI trends, a focused, reproducible analysis of age‐standardized LRI mortality and DALY rates attributable to air pollution from 1990 through 2021 has not been published.

**Aims**  
- Quantify age‐standardized death rates (ASDR) and DALY rates for LRIs attributable to air pollution in 1990 vs. 2021.  
- Estimate Estimated Annual Percentage Change (EAPC) and Average Annual Percentage Change (AAPC) in LRI ASDR and DALY rates by country, SDI quintile, and GBD super‐region.  
- Visualize trends (e.g., SDI vs. DALY trajectories, choropleth of EAPC).  
- Highlight geographic and sociodemographic disparities in LRI burden.

---

## Folder Structure

```

├── Code/
│   ├── EAPC.R              # Scripts to generate key figures (SDI vs. DALY plot, EAPC map, etc.)

├── Data/
│   ├── eapc.csv        # GBD 2021 table (filtered for LRI + air pollution)
│   ├── nation.csv         # GBD 2021 “DALYs” table (filtered for LRI + air pollution, and in a nation level)
│   ├── SDI.csv           # Country‐year SDI values (1990–2021)
└── README.md                              # This file

````

---

## Data Sources

1. **Global Burden of Disease (GBD) 2021**  
   - _Deaths_ table: cause‐specific death counts and age‐standardized death rates (ASDR) for “Lower Respiratory Infections,” stratified by risk factor (Air Pollution), location, sex, and age group.  
   - _DALYs_ table: cause‐specific DALYs (Disability‐Adjusted Life Years) for LRIs attributable to air pollution.  
   - _Population Attributable Fraction (PAF)_: Provided by GBD 2021 for ambient PM₂.₅ and household air pollution.  
   - For detailed metadata on input sources (e.g., satellite‐ and monitor‐based PM₂.₅ estimates, solid‐fuel use surveys), see:  
     > GBD 2019 Risk Factors Collaborators. “Global Burden of 87 Risk Factors in 204 Countries and Territories, 1990–2019.” Lancet 396.10258 (2020): 1223–1249.  

2. **Sociodemographic Index (SDI)**  
   - Country‐year SDI values (1990–2021), composed of per‐capita income, average educational attainment, and fertility under age 25.  
   - Quintile thresholds:  
     - Low (≤ 0.454743)  
     - Low‐middle (0.454743–0.607679)  
     - Middle (0.607679–0.689504)  
     - High‐middle (0.689504–0.805129)  
     - High (> 0.805129)  
   - Source: GBD 2019 SDI Collaborators. “Measuring Socio‐Demographic Index (SDI) for All Countries and Territories, 1990–2019.” Population Health Metrics 18 (2020): 12.

3. **Country-to-Region Mapping**  
   - GBD 2021 geographic hierarchy: 21 regions (e.g., Tropical Latin America, Central Sub‐Saharan Africa), aggregated into 7 super‐regions (e.g., Latin America & Caribbean, Sub‐Saharan Africa).  
   - See `Data/raw/country_region_mapping.csv` for mapping details.

---


## Key Outputs & Results

1. **Global LRI Burden Trends (1990–2021)**

   * ASDR dropped from 18.7 deaths/100 000 (95% UI 8.5–32.1) in 1990 to 6.5 deaths/100 000 (95% UI 3.2–11.4) in 2021 (EAPC –2.35%, 95% CI –2.68 to –2.23).
   * ASDALY rate declined from 2 100/100 000 (95% UI 850–3 920) to 760/100 000 (95% UI 300–1 400) (EAPC –2.12%, 95% CI –2.45 to –1.89).

2. **SDI‐Stratified Patterns**

   * High‐SDI countries experienced slight increases in ASDR (EAPC +0.89%, 95% CI +1.13 to +0.58).
   * Middle‐SDI: EAPC –3.64% (95% CI –4.17 to –3.67).
   * Low‐SDI: EAPC –4.24% (95% CI –4.39 to –4.14).

3. **Super‐Region Highlights**

   * East Asia: EAPC –6.55% (95% CI –7.53 to –6.29).
   * Sub‐Saharan Africa (Central): ASDR 273.4/100 000 in 2021 (95% UI 49.2–474.8) despite EAPC –1.61% (95% CI –2.27 to –1.49).
   * Latin America & Caribbean: Consistently > 70% DALY reduction as SDI increased from \~0.50 to \~0.75.

4. **Figure Summaries**

   * **Figure A (SDI vs. DALY)**: Inverse relationship across all super‐regions; highest 2021 burdens remain in South Asia and Sub‐Saharan Africa.
   * **Figure C (EAPC Map)**: Widespread declines (green) across Europe, East Asia, and Latin America; pockets of slower decline or modest increases (red) in high‐SDI countries and certain Central‐Asian locations.

---

## Dependencies

* **R (≥ 4.0.3)**

* R Packages:

  * `tidyverse` (≥ 1.3.0)
  * `readr`
  * `sf` (≥ 1.0-7)
  * `viridis`
  * `ggplot2`
  * `kableExtra`

* **Tableau (optional)**

  * For interactive choropleth visualizations (provided as supplementary `.twbx` if available).

---

## Citation

If you use this repository or any of its outputs, please cite:

> Chen, K., et al. “The Burden of Lower Respiratory Infections Attributable to Air Pollution: An Analysis of Global Data from 1990 to 2021.” *\[Journal/Platform]* (Year).

Additionally, acknowledge the underlying GBD data sources:

> GBD 2021 Risk Factors Collaborators. “Global Burden of 87 Risk Factors in 204 Countries and Territories, 1990–2021: a systematic analysis for the Global Burden of Disease Study 2019.” *Lancet* 396.10258 (2020): 1223–1249.
> GBD 2021 SDI Collaborators. “Measuring Socio-Demographic Index (SDI) for all countries and territories, 1990–2021: methodology and key findings.” *Population Health Metrics* 18 (2020): 12.

---


