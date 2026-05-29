# 🦠 COVID-19 India — Epidemiological Analytics Dashboard

[![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat-square&logo=tableau&logoColor=white)](https://www.tableau.com/)
[![Domain](https://img.shields.io/badge/Domain-Public_Health-red?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)]()

> A state-level epidemiological Tableau dashboard tracking India's COVID-19 trajectory — confirmed cases, recoveries, fatalities, vaccination progress, and testing rates — enabling public health stakeholders to identify regional disparities and monitor pandemic response effectiveness.

---

## 📌 Problem Statement

During the COVID-19 pandemic, decision-makers at state and national levels needed rapid, reliable, and digestible data about case trends, healthcare capacity, and vaccination penetration. Raw government data published in tabular formats was difficult to synthesize across India's 28 states and 8 union territories.

This dashboard was built to make that data accessible, spatial, and interactive — enabling faster situational awareness and evidence-based policy decisions.

---

## 💡 Solution Overview

The COVID-19 India Dashboard consolidates publicly available pandemic data into a unified Tableau workbook. It answers critical public health questions:

- Which states have the highest active case loads?
- How does the case fatality rate (CFR) vary across states?
- What is the recovery rate trend over time?
- How has the vaccination rollout progressed by state?
- What is the testing density relative to case positivity?

---

## ✨ Features

- **State-Wise Case Distribution Map** — Filled map of India with color-encoded confirmed case counts; instantly identifies outbreak hotspots
- **Confirmed / Recovered / Deceased KPI Summary** — Headline numbers with delta from previous period
- **Time-Series Epidemic Curve** — Daily new cases trend (7-day rolling average) showing wave structure
- **Recovery Rate Tracker** — Recovery rate % by state, ranked to show healthcare system effectiveness
- **Case Fatality Rate (CFR) Analysis** — State-wise CFR comparison; flags states with disproportionately high mortality
- **Vaccination Progress** — Doses administered by state; dose-1 vs. dose-2 split
- **Testing Rate vs. Positivity Rate** — Scatter showing correlation between testing density and positivity — a key indicator of true outbreak visibility
- **Interactive Filters** — Date range, state selection, metric toggle

---

## 🏗️ Dashboard Architecture

```
Data Sources:
├── covid19india.org (state-wise time-series case data)
├── MoHFW vaccination data
└── ICMR testing data
          │
          ▼
Tableau Data Layer
├── Calculated Fields:
│   ├── Recovery Rate (%) = [Recovered] / [Confirmed] * 100
│   ├── Case Fatality Rate (%) = [Deaths] / [Confirmed] * 100
│   ├── Active Cases = [Confirmed] - [Recovered] - [Deaths]
│   ├── 7-Day Rolling Average (WINDOW_AVG)
│   └── Test Positivity Rate = [Cases] / [Tests Conducted] * 100
├── Geographic Role: State (India)
└── Date Aggregation: Daily → Weekly → Monthly rollup
          │
          ▼
Dashboard Sheets
├── Sheet 1: India State Map (filled, color = confirmed cases)
├── Sheet 2: KPI Banner (Confirmed, Active, Recovered, Deaths)
├── Sheet 3: Epidemic Curve — daily cases with rolling average
├── Sheet 4: State Recovery Rate Ranked Bar
├── Sheet 5: CFR by State Horizontal Bar
├── Sheet 6: Vaccination Stacked Bar (Dose 1 vs. Dose 2)
└── Sheet 7: Testing vs. Positivity Scatter
          │
          ▼
Interactive Tableau Dashboard (.twb)
```

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| **Tableau Desktop** | Dashboard design, geographic mapping, time-series |
| **COVID-19 India Dataset** | State-level case, recovery, death, testing time-series |
| **Tableau Maps (India)** | Built-in geographic shape for state-level mapping |
| **Table Calculations** | Rolling averages, running totals, period-over-period |

---

## 🚀 Getting Started

### Prerequisites

- [Tableau Desktop](https://www.tableau.com/products/desktop) (2020.3+ recommended for India map support) or [Tableau Public](https://public.tableau.com/)

### Setup

```bash
git clone https://github.com/Shubh1015/Covid-19-in-India.git
cd Covid-19-in-India
```

Open `Covid 19 Analsis of India.twb` in Tableau.

> **Data Source:** COVID-19 India data is available from [covid19india.org](https://www.covid19india.org/) or [data.gov.in](https://data.gov.in/). Reconnect data source if prompted.

---

## 📸 Dashboard Preview

```
[ Screenshot: Covid19_India_Dashboard.png ]
```

---

## 📊 Key Analytical Findings

*(Based on India's COVID-19 data patterns)*

- India experienced **two distinct major waves**: Wave 1 peaked in September 2020; Wave 2 (Delta variant) in May 2021 was significantly more intense
- **Maharashtra, Kerala, and Karnataka** consistently appeared among the highest total case-load states
- The national **case fatality rate** declined from ~3% in early 2020 to under 1.5% by mid-2021, indicating improved clinical management
- States with higher testing rates showed higher reported positivity — reflecting better outbreak visibility rather than necessarily worse outbreaks
- Vaccination drive significantly accelerated after April 2021, with urban states achieving higher dose-2 coverage

---

## 🔮 Future Enhancements

- [ ] Add district-level granularity (where data is available)
- [ ] Integrate hospital capacity / ICU bed occupancy data
- [ ] Build a predictive trend line using Tableau's forecast feature
- [ ] Add variant wave annotation markers on the epidemic curve

---

## ⚠️ Data Disclaimer

This dashboard is built for educational and analytical purposes. All data is sourced from publicly available government and civil society datasets. Numbers may differ slightly from official records due to reporting lags.

---

## 🤝 Contributing

Public health data analysis improvements and new data integrations are welcome. Please open an issue before submitting a PR.

---

## 📄 License

MIT License. Data sourced from public domain COVID-19 datasets.

---

## 🏷️ Topics

`tableau` `covid-19` `public-health` `epidemiology` `india` `data-visualization` `healthcare-analytics` `pandemic-analysis` `business-intelligence`
