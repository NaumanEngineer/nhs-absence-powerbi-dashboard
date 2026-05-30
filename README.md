# 🏥 NHS Staff Absence Power BI Dashboard
### Interactive workforce intelligence dashboard | 75,824 records | NHS-branded

![PowerBI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=flat-square&logo=powerbi)
![DAX](https://img.shields.io/badge/DAX-6%20Measures-orange?style=flat-square)
![NHS](https://img.shields.io/badge/NHS-Official%20Branding-005EB8?style=flat-square)
![Records](https://img.shields.io/badge/Records-75%2C824-green?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

---

## 📋 Project Overview

An NHS-branded interactive Power BI dashboard analysing 75,824 staff absence records across five NHS Trusts for the full calendar year 2023. Built across six structured sessions covering data connection, core visuals, interactivity, DAX measures, NHS branding, and portfolio packaging.

This project is the second in a series of NHS portfolio pieces and directly complements the [NHS Staff Absence SQL Analysis](https://github.com/NaumanEngineer/nhs-staff-absence-sql) project.

---

## 📊 Dashboard Features

### KPI Cards (6 measures)
| Card | Value | Type |
|------|-------|------|
| Total Absences | 75,824 | Count |
| Total Days Lost | 206,014 | Sum |
| Avg Absence Duration | 2.72 days | Average |
| ICB Absence Rate | 8.73% | DAX measure |
| Winter Absence % | 42.76% | DAX measure |
| Unauthorised Rate | 9.19% | DAX measure |

### Visualisations
- **Bar chart** — Absences by trust (5 trusts ranked)
- **Line chart** — Monthly absence trend (January → December)
- **Donut chart** — Absence reasons breakdown with NHS colour coding

### Interactive Slicers
- Filter by **Trust** — instantly filters all visuals
- Filter by **Absence Reason** — drill into sickness, training, maternity etc
- Filter by **Month** — analyse any month in isolation

---

## 🎨 NHS Branding Applied

| Element | Colour | Hex |
|---------|--------|-----|
| Header banner | NHS Dark Blue | #003087 |
| Card borders | NHS Blue | #005EB8 |
| Chart colours | NHS Blue | #005EB8 |
| Sickness segment | NHS Red | #DA291C |
| Unauthorised segment | NHS Amber | #ED8B00 |
| Training segment | NHS Blue | #005EB8 |
| Compassionate segment | NHS Green | #009639 |
| Maternity segment | NHS Purple | #330072 |
| Canvas background | NHS Pale Grey | #F0F4F5 |

---

## 🔢 DAX Measures

### Absence Rate %
```dax
Absence Rate % = DIVIDE(COUNTROWS('nhs_staff_absence'), 2380 * 365, 0) * 100
```

### Winter Absence %
```dax
Winter Absence % = 
DIVIDE(
    CALCULATE(COUNTROWS('nhs_staff_absence'), 'nhs_staff_absence'[is_winter_month] = 1),
    COUNTROWS('nhs_staff_absence'),
    0
) * 100
```

### Unauthorised Rate %
```dax
Unauthorised Rate % = 
DIVIDE(
    CALCULATE(COUNTROWS('nhs_staff_absence'), 'nhs_staff_absence'[absence_reason] = "Unauthorised"),
    COUNTROWS('nhs_staff_absence'),
    0
) * 100
```

### Sickness Rate %
```dax
Sickness Rate % = 
DIVIDE(
    CALCULATE(COUNTROWS('nhs_staff_absence'), 'nhs_staff_absence'[absence_reason] = "Sickness"),
    COUNTROWS('nhs_staff_absence'),
    0
) * 100
```

---

## 🗂️ Repository Structure

```
nhs-absence-powerbi-dashboard/
│
├── 📊 NHS_Absence_Dashboard.pbix          # Power BI dashboard file
├── 📄 NHS_Absence_Dashboard.pdf           # Exported PDF for portfolio
├── 📋 nhs_staff_absence.csv               # Source dataset (75,824 rows)
├── 🖼️ dashboard_overview.png             # Full dashboard screenshot
├── 🖼️ dashboard_wgh_filter.png           # WGH trust filtered view
├── 🖼️ dashboard_december.png             # December month filtered view
├── 🖼️ dashboard_sickness.png             # Sickness reason filtered view
└── 📖 README.md                           # This file
```

---

## 🚀 Getting Started

### Prerequisites
- Power BI Desktop (free download from microsoft.com/power-bi)

### Setup
1. Download the repository
2. Open `NHS_Absence_Dashboard.pbix` in Power BI Desktop
3. The dashboard loads with all data embedded
4. Use slicers to explore the data interactively

---

## 📈 Power BI Sessions Completed

| Session | Focus | Output |
|---------|-------|--------|
| PBI-1 | Data connection + exploration | CSV imported, 75,824 rows verified |
| PBI-2 | Core visuals | 3 cards + bar + line + donut charts |
| PBI-3 | Slicers and interactivity | 3 slicers filtering all visuals |
| PBI-4 | DAX measures | 6 calculated KPI measures |
| PBI-5 | NHS branding and design | Official NHS colour scheme applied |
| PBI-6 | Export and packaging | PDF, screenshots, GitHub |

---

## 🔑 Key Findings

**Every trust exceeds its absence target** — MHT worst at 10.33% against a 5% target, confirmed visually by the absence rate card and trust bar chart.

**Winter generates 42.76% of all absences** — the Winter Absence % DAX measure confirms seasonal pressure is not evenly distributed throughout the year.

**Sickness dominates at 49.45%** — nearly half of all absences are sickness-related, visible in the donut chart and confirmed by the Sickness Rate % measure.

**Unauthorised absence at 9.19%** — one in ten absences has no explanation, a governance red flag surfaced by the Unauthorised Rate % measure.

---

## 🛠️ Technology Stack

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard development |
| DAX | Calculated measures |
| MySQL | Source database (SQL analysis) |
| CSV | Data import format |

---

## 📁 Related Portfolio Projects

| Project | Skills | Link |
|---------|--------|------|
| NHS OPEL Predictor | ML, SHAP, Python, Streamlit | [View](https://github.com/NaumanEngineer/nhs-opel-predictor) |
| NHS Staff Absence SQL | SQL, MySQL, Window functions | [View](https://github.com/NaumanEngineer/nhs-staff-absence-sql) |
| NHS Power BI Dashboard | Power BI, DAX, NHS branding | This repo |

---

## ⚠️ Data Notice

This project uses **synthetic data** generated to reflect realistic NHS operational patterns. No real patient, staff, or organisational data was used.

---

## 🎓 Learning Context

Part of an 18-month NHS Health & Care AI Roadmap targeting Band 7/8a NHS data science and informatics roles. Power BI Week (Sessions 1–6) follows completion of the NHS OPEL Predictor and NHS Staff Absence SQL projects.

---

## 📞 Contact

**Author:** Nauman Ismail Khan
**GitHub:** [NaumanEngineer](https://github.com/NaumanEngineer)

---

## 📜 License

MIT License

---

*Part of the NHS Health & Care AI 18-Month Roadmap — Power BI Week Portfolio Project*
