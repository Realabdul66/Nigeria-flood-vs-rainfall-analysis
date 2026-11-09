# 🇳🇬 Nigeria Rainfall vs Flood Analysis Dashboard

**An end-to-end data analytics project investigating whether rainfall volume predicts flood impact in Nigeria — combining Python for data cleaning and exploratory analysis with an interactive Power BI dashboard.**

[![3MTT](https://img.shields.io/badge/3MTT-NextGen%20Cohort-3730A3)](https://3mtt.nitda.gov.ng/)
[![Python](https://img.shields.io/badge/Python-pandas-blue)](https://pandas.pydata.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-DAX%20%7C%20Power%20Query-yellow)](https://powerbi.microsoft.com/)

**Capstone Project DA-16** · 3MTT Data Analytics NextGen Cohort · Group 32 · Blue Sapphire Hub, Kano

Author: **Abdulrahaman Alhaji Rabiu** — Track ID `FE/23/39527929`

---

## 📌 Overview

Nigeria experiences some of the most severe flooding in West Africa. The common assumption is simple: *more rain means more flooding.* This project tests that assumption directly using real data, combining **45 years of CHIRPS satellite rainfall data (1981–2026)** with **EM-DAT international disaster records (1988–2025)**  to find out whether rainfall alone explains Nigeria's flood crisis, or whether something else is driving it.

### 🔑 Key Finding

> **The correlation between annual rainfall and flood impact is r = 0.164 a very weak relationship.**
> Despite South Nigeria receiving **99% more rainfall** than the North, the North accounts for **71.43%** of all recorded flood events. This suggests flood risk in Nigeria is driven less by rainfall volume and more by factors such as **dam releases and infrastructure**  a finding with real implications for how flood early-warning systems should be designed.

---

## 📊 Key Figures

| Metric | Value |
|---|---|
| Total Deaths (1988–2025) | 4,645 |
| Total People Affected | 17.6 million |
| Total Flood Events | 63 |
| Total Economic Damage | $5.4 billion USD |
| Deadliest Year | 2025 (1,390 deaths) |
| Most People Affected (single year) | 2012 (7,000,867 people) |
| Increase in Flood Deaths Since 1988 | +373% |
| Peak Flood Season | July – September |
| Rainfall–Flood Correlation | r = 0.164 (very weak) |

---

## 🛠️ Tech Stack

| Stage | Tools |
|---|---|
| **Data Cleaning & EDA** | Python, pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook |
| **Data Modeling & Dashboard** | Power BI Desktop — Power Query, DAX, Star Schema |
| **Documentation** | Markdown, Microsoft Word |

---

## 🔄 Project Workflow

```
Raw Data (CHIRPS + EM-DAT)
        │
        ▼
┌─────────────────────────┐
│   1. PYTHON CLEANING     │  Jupyter Notebook
│   • 8 rainfall cleaning steps
│   • 8 flood cleaning steps
│   • Region/zone classification (regex-based)
└─────────────────────────┘
        │
        ▼
┌─────────────────────────┐
│   2. EXPLORATORY ANALYSIS │  6 Research Questions
│   • Rainfall by state & region
│   • Flood deaths & impact trends
│   • Seasonal patterns
│   • Correlation analysis
└─────────────────────────┘
        │
        ▼
┌─────────────────────────┐
│   3. POWER BI DASHBOARD   │  Star Schema Model
│   • 3 dimension tables
│   • 4 fact tables
│   • 8 DAX measures
│   • 3 interactive pages
└─────────────────────────┘
```

---

## 📁 Repository Structure

```
├── notebooks/
│   └── Nigeria_Rainfall_Flood_Analysis.ipynb   # Full cleaning + EDA pipeline
├── data/
│   ├── Nigeria_Flood_Annual.csv
│   ├── Nigeria_Flood_Clean.csv
│   ├── Nigeria_Rainfall_By_State.csv
│   └── Nigeria_Rainfall_Monthly.csv
├── dashboard/
│   └── Capstone_3MTT.pbix                      # Power BI dashboard file
├── docs/
│   ├── Insight_Summary.docx                    # 1-page findings summary
│   └── Demo_Video_Script.docx
├── screenshots/
│   ├── executive_summary.png
│   ├── flood_impact.png
│   └── rainfall_analysis.png
└── README.md
```

---

## 🧹 Data Cleaning Summary

**Rainfall data** (CHIRPS, 1981–2026, 1,048,575 raw rows) — 8-step cleaning pipeline covering type correction, missing value handling, outlier checks, and aggregation into state-level and monthly summaries.

**Flood data** (EM-DAT, 1988–2025, 63 events) — 8-step cleaning pipeline, including a custom **Step 8: Location Standardization** — a regex-based classifier that matches all 36 Nigerian states + FCT mentioned in each event's free-text location field, maps them to their geopolitical zone, and derives:
- `Flood_Broad_Region` (North / South)
- `Primary_Zone` (6-zone geopolitical classification)
- `Single_State_Event` (populated only for genuinely single-state events — never a misleading guess)
- `Multi_Region_Event` (flag for events spanning multiple zones)

---

## 📈 Dashboard Pages

### 1️⃣ Executive Summary
KPI cards, interactive slicers (Year / Region / Month / State), state-level rainfall map, annual deaths trend, and top-10 rainfall states.

### 2️⃣ Flood Impact Analysis
Deaths by year, people affected over time, worst flood events table, monthly flood pattern, and North vs South regional comparison.

### 3️⃣ Rainfall Analysis
Rainfall by state, monthly seasonal pattern, regional rainfall trends, rainfall-vs-flood correlation scatter plot, and key insight summary.

---

## ▶️ How to Reproduce

1. Clone this repository
2. Open `notebooks/Nigeria_Rainfall_Flood_Analysis.ipynb` in Jupyter Notebook
3. Run all cells (**Kernel → Restart & Run All**) to regenerate the 4 cleaned CSVs
4. Open `dashboard/Capstone_3MTT.pbix` in Power BI Desktop
5. Refresh the data model (**Home → Refresh**) to load the latest CSVs

**Requirements:** Python 3.9+, `pandas`, `numpy`, `matplotlib`, `seaborn` · Power BI Desktop (latest version)

---

## 📚 Data Sources

- **Rainfall:** [CHIRPS Satellite Rainfall Data](https://data.humdata.org/) via Humanitarian Data Exchange (HDX), 1981–2026
- **Floods:** [EM-DAT — The International Disaster Database](https://www.emdat.be/), 1988–2025

---

## 🙏 Acknowledgements

This project was completed as part of the **3MTT (3 Million Technical Talent) Data Analytics NextGen Cohort**, under **Blue Sapphire Hub**, Kano. Special thanks to Group 32 for collaborative support throughout the capstone.

---

## 📄 License

This project is submitted for educational purposes as part of the 3MTT Capstone program. Data sourced from HDX and EM-DAT under their respective open-data licenses.

---

**Contact:** Abdulrahaman Alhaji Rabiu · Track ID `FE/23/39527929` · 3MTT NextGen Cohort, Group 32
