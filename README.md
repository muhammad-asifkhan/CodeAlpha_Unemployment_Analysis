# Unemployment Analysis with Python

![Python](https://img.shields.io/badge/Python-3.14-blue?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-2.x-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Domain](https://img.shields.io/badge/Domain-Economic%20Analysis-informational)

> **CodeAlpha Data Science Internship — Task 2**  
> Rigorous time-series analysis of India's unemployment crisis — quantifying the catastrophic impact of COVID-19 with Welch's t-tests, Cohen's d effect sizes, moving averages, and state-level decomposition.

---

## Problem Statement

Analyse India's unemployment landscape from 2019–2020, investigating:
1. The **catastrophic impact of the COVID-19 lockdown** (March 24, 2020) on employment.
2. **Regional disparities** — which states were most vulnerable.
3. **Structural differences** between Rural and Urban labour markets.
4. **Seasonal and monthly patterns** in unemployment cycles.

---

## Datasets

| Dataset | Rows | Features | Description |
|---------|------|----------|-------------|
| `Unemployment_in_India.csv` | 740 (cleaned) | 7 | State-level monthly unemployment with area breakdown |
| `Unemployment_Rate_upto_11_2020.csv` | 267 | 9 | National-level rates with geo-coordinates |

**Date range:** January 2019 – November 2020  
**COVID cutoff:** 24 March 2020 (India national lockdown)

---

## Methodology

```
Raw Data (2 CSVs)
   │
   ├── Data Cleaning
   │     ├── Drop 28 completely blank rows
   │     ├── Strip whitespace from column names
   │     ├── Parse dates (dd-MM-yyyy format)
   │     └── Engineer: Period (Pre/Post-COVID), DaysSinceLockdown
   │
   ├── Exploratory Data Analysis
   │     ├── Descriptive statistics by period
   │     └── Missing value audit
   │
   ├── Time-Series Trend Analysis
   │     ├── Monthly mean ± 1 SD confidence band
   │     ├── Min-Max range shading
   │     ├── Savitzky-Golay smoothed trend line
   │     └── Peak annotation (lockdown spike)
   │
   ├── Statistical Significance Testing
   │     ├── Welch's t-test (Pre vs Post-COVID, unequal variance)
   │     ├── Cohen's d effect size
   │     └── Phase comparison (Pre / Lockdown / Post-Lockdown)
   │
   ├── Regional Analysis
   │     ├── State-wise grouped bar chart (Pre vs Post)
   │     ├── % change ranking
   │     └── Top 10 most-affected states
   │
   ├── Rural vs Urban Analysis
   │     ├── Time-series overlay
   │     ├── Welch's t-test (post-COVID urban vs rural)
   │     └── Split violin plot (Pre/Post × Area)
   │
   └── Month × State Heatmap
```

---

## Key Statistical Findings

| Metric | Pre-COVID | Post-COVID | Change |
|--------|:---------:|:----------:|:------:|
| Mean Unemployment | ~7.3% | ~23.5% | **+16.2 pp (+222%)** |
| Median | ~6.7% | ~20.5% | **+13.8 pp** |
| Cohen's d | — | — | **Large (d > 1.5)** |
| Welch t-test | — | — | **p < 0.001** |

### Key Insights

1. India's unemployment rate **tripled within weeks** of the March 2020 lockdown — the steepest shock in recorded data.
2. Peak unemployment reached **~23.5%** (April–May 2020) from a pre-crisis baseline of ~7.3%.
3. **Urban areas** were disproportionately hit (+260%) vs Rural (+180%) — urban service sectors collapsed.
4. States with large **informal economies** (Tripura, Haryana, Jharkhand) showed the sharpest spikes.
5. Recovery began **June 2020** but stayed above pre-COVID baseline — suggesting scarring effects.
6. **Welch's t-test** confirms the difference is statistically significant (p < 0.001) with a **large Cohen's d** — not a random fluctuation.

---

## Project Structure

```
2_Unemployment_Analysis/
├── Unemployment_Analysis.ipynb   # Full analysis notebook
├── data/
│   ├── Unemployment_in_India.csv
│   └── Unemployment_Rate_upto_11_2020.csv
├── reports/
│   ├── 01_trend.png              # Time-series with confidence band
│   ├── 02_covid_impact.png       # Statistical comparison
│   ├── 03_regional.png           # State-wise bar chart
│   ├── 04_rural_urban.png        # Rural vs Urban analysis
│   └── 05_heatmap_top10.png      # Month × State heatmap
└── README.md
```

---

## How to Run

```bash
.\venv\Scripts\Activate.ps1
jupyter notebook 2_Unemployment_Analysis/Unemployment_Analysis.ipynb
```

---

## Technologies

| Library | Purpose |
|---------|---------|
| `pandas` / `numpy` | Data manipulation & feature engineering |
| `matplotlib` / `seaborn` | Advanced visualisation |
| `scipy.stats` | Welch's t-test, Cohen's d |
| `scipy.signal.savgol_filter` | Trend smoothing |

---

## Policy Recommendations

| Priority | Action |
|----------|--------|
| Immediate | Emergency income support for urban informal workers |
| Short-term | MGNREGA expansion & skill retraining in disrupted sectors |
| Long-term | Real-time unemployment monitoring infrastructure |
| Structural | Reduce urban-rural mobility barriers |

---

## Author

**Mudassir** — CodeAlpha Data Science Intern  
[GitHub](https://github.com) · [LinkedIn](https://linkedin.com)
