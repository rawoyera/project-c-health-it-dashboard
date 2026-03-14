# 🏥 Health IT Dashboard — Wearable Fitness Data
**Tools:** Python (Pandas) · Tableau · Power BI  
**Data:** 36,500 rows · 100 users · Daily wearable metrics · Full year 2023

---

## 📌 Project Overview

This project simulates a health informatics use case: translating daily wearable device data into an executive-level dashboard that supports preventive care decision-making. The dashboard surfaces population-level patterns in activity, sleep, heart rate, and stress — the kinds of signals that health systems and digital health teams monitor to identify risk before clinical deterioration occurs.

---

## 📂 Dataset

| Attribute | Detail |
|---|---|
| **Rows** | 36,500 |
| **Users** | 100 individuals |
| **Time Period** | Full calendar year 2023 (daily granularity) |
| **Source** | Simulated wearable fitness tracking data |

**Columns included:**  
`User_ID`, `Full Name`, `Date`, `Age`, `Gender`, `Height (cm)`, `Weight (kg)`, `Steps_Taken`, `Calories_Burned`, `Hours_Slept`, `Water_Intake (Liters)`, `Active_Minutes`, `Heart_Rate (bpm)`, `Workout_Type`, `Stress_Level (1–10)`, `Mood`

---

## 🛠️ Tools Used

- **Python (Pandas)** — data cleaning, missing value handling, feature engineering, CSV exports
- **Tableau Public** — interactive dashboard with KPI tiles, trend lines, and behavioral scatter plots
- **Power BI Desktop** — parallel dashboard build demonstrating DAX measures and Power BI-specific formatting

---

## 🧹 Data Cleaning Summary

The raw dataset contained missing values across several columns. The following strategy was applied using Python (Pandas):

| Column | Missing Value Strategy | Rationale |
|---|---|---|
| `Workout_Type` | Filled with `"Rest/None"` | Absence of a logged workout logically indicates a rest day |
| `Hours_Slept` | Filled with **per-user median** | Preserves individual sleep patterns rather than overwriting with population average |
| `Water_Intake (Liters)` | Filled with **per-user median** | Same rationale — individual hydration habits vary significantly |
| `Active_Minutes` | Filled with **per-user median** | Activity levels differ substantially across users |
| `Heart_Rate (bpm)` | Filled with **per-user median** | Resting heart rate is highly individual; population-level fill would distort user profiles |

After cleaning: **0 missing values** across all 36,500 rows.

**Additional feature engineering:**
- Converted `Date` column to datetime format
- Extracted `Month` and `Quarter` columns for time-series aggregation

**Exported files:**
- `cleaned_fitness_data.csv` — row-level data for scatter plots and behavioral analysis
- `monthly_trends.csv` — monthly averages for trend line charts
- `kpi_summary.csv` — single-row population KPIs for executive snapshot tiles

---

## 📊 Dashboard Sections

### 1. Executive Snapshot — KPI Tiles
Five population-level KPIs displayed as summary cards, giving leadership an at-a-glance health status for the cohort:
- Avg Daily Steps · Avg Hours Slept · Avg Heart Rate · Avg Stress Level · % Weeks Meeting Activity Guidelines (≥150 min/week)

### 2. Trends Over Time
Line charts tracking monthly averages for steps, sleep, heart rate, and stress across the full year. Enables identification of seasonal patterns, sustained declines, or stress spikes at the population level.

### 3. Behavioral Relationships
Scatter and bar charts exploring how behaviors interact:
- Sleep vs. Stress Level
- Active Minutes vs. Heart Rate
- Average Mood by Workout Type

These views surface whether activity types are associated with improved mood and whether sleep quality correlates with reported stress.

### 4. Health IT Narrative Panel
> *"Wearable-derived data enables early identification of declining sleep, rising stress, and reduced activity — signals that can support preventive interventions before clinical deterioration."*

This framing panel connects the dashboard to real-world Health IT applications: population health management, risk stratification, and digital health program design.

---

## 💡 Key Insights

- **Activity levels are strong across the cohort** — the population averaged **11,035 steps/day** and **74.4 active minutes/day**, with 100% of user-weeks meeting the recommended 150 active minutes/week threshold
- **Sleep is consistently below recommended levels** — average sleep across the year was **6.49 hours/night**, below the 7–9 hour adult guideline; this is a population-level risk signal worth monitoring
- **Stress levels sit at a moderate-high midpoint** — average stress of **5.5 out of 10** was stable across all 12 months with minimal seasonal variation, suggesting a chronic rather than acute pattern
- **Heart rate averaged 79.6 bpm** — within normal range, but individual variation visible in scatter analysis; active minutes show a meaningful relationship with cardiovascular response
- **Mood distribution is nearly equal across all four categories** (Happy, Neutral, Sad, Stressed), with workout type data providing actionable segmentation for behavioral health interventions

---

## 🏥 Health IT Framing

This dashboard was designed with a digital health and population health informatics lens. In real-world Health IT contexts, wearable data pipelines like this one feed into:

- **Chronic disease prevention programs** — flagging users with declining activity or rising stress before conditions escalate
- **Population health management platforms** — aggregating individual signals into cohort-level risk views for care coordinators
- **Patient engagement tools** — surfacing personalized trends to support behavior change

The ability to move from raw sensor data → cleaned dataset → executive dashboard demonstrates the full data-to-decision pipeline that health systems and digital health organizations are actively building.

---

## 📸 Dashboard Screenshots

### Tableau Dashboard
![Tableau Dashboard](tableau_screenshot.png
> *Executive snapshot, trend lines, and behavioral relationship charts built in Tableau Public*

### Power BI Dashboard
![Power BI Dashboard](visuals/powerbi_screenshot.png)
> *Parallel build in Power BI Desktop using DAX measures and Card visuals*

---

## 📁 Repository Structure

```
project-c-health-it-dashboard/
├── data/
│   ├── cleaned_fitness_data.csv
│   ├── monthly_trends.csv
│   └── kpi_summary.csv
├── notebooks/
│   └── data_cleaning.ipynb
├── visuals/
│   ├── tableau_screenshot.png
│   └── powerbi_screenshot.png
└── README.md
```

---

## 👩🏽‍💻 About This Project

Part of a Health Data Analytics portfolio targeting **Health Data Analyst**, **Population Health Analyst**, and **Digital Health Informatics** roles.  
Projects A and B available in the same portfolio repository.
