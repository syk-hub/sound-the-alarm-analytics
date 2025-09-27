# 🔥 Synthetic *Sound the Alarm* Project (2015–2025)


## Motivation
This project was born out of my work with the Red Cross Information & Planning group, where I helped analyze data from the *Sound the Alarm* fire safety campaign. Because the real operational data is confidential, I created a synthetic dataset that **approximates** its structure and behavior without revealing sensitive details.

The dataset was built in two stages:
- **Notebook 1:** Synthetic data generation with added realistic disturbances (seasonality, anomalies, COVID dip).  
- **Notebook 2:** Data wrangling and cleaning to produce a structured dataset ready for analysis.  

The idea was simple: show how a decade of program data can be turned into insight. From synthetic generation and cleaning, to descriptive analysis, and later predictive and prescriptive modeling. This repository demonstrates the full arc of data storytelling.

This repository highlights both the technical workflow and the real-world program context behind the analysis.

---

## Key Findings
- Nearly **95,000 alarms installed** and **111,000 people served** across a 10-year period.  
- Clear **COVID-era dip (2020–2021)** in installs and outreach, followed by recovery.  
- **LA Metro dominates** (42% of installs), raising equity and resource allocation questions.  
- **Central Coast most efficient** region (~1.30 people per install).  
- **Weekends stronger than weekdays**, with Sunday highest — aligning with volunteer mobilization.  
- **Installs and people served strongly correlated (0.73)**, making installs a reliable proxy KPI.

Together, these analyses reveal clear patterns in how the program operated and evolved over a decade. The highlights are summarized below.
 

---

## Dataset
- **File:** `data/processed/synthetic_sound_the_alarm_2015_2025_clean.csv`  
- **Size:** ~1.2 MB  
- **Nature:** Synthetic (fabricated for demonstration; no real individuals or events)  
- **Purpose:** Reproducible EDA + modeling examples  
- **License (data):** CC BY 4.0  
- **SHA256:** (to be added)  

### How the data was generated
The dataset was generated programmatically to mimic Red Cross field operations. To avoid being “too clean,” realistic **disturbances** were added:
- Random variation in installs per household.
- Seasonal and monthly effects (spring peaks, winter troughs).
- Geographic differences across territories.
- A **COVID-era dip (2020–2021)** to mirror real-world disruptions.
- Small anomalies (zero-alarm visits, outlier ratios) to reflect the messiness of field data.

This ensures the dataset feels authentic and forces the same kind of wrangling and analysis steps needed in real-world analytics projects.

---

## Key Results (KPIs)
Scale of synthetic program (2015-01-01 → 2025-09-20):
- **94,956 installs**
- **111,341 people served**
- **3,884 active days**

Efficiency & cadence:
- **~1.17 people per install**
- Near-daily operations across ten years
- **Weekends ≈ +14% vs weekdays**; Sunday strongest
- **LA Metro = 42% of installs**
- **Central Coast leads in efficiency** (~1.30 people per install)

📂 See [reports/artifacts/eda/kpis.csv](reports/artifacts/eda/kpis.csv)  
📈 See figures in `reports/figures/eda/`

---

## Descriptive Analysis (EDA)

### Trends Over Time
From **2015–2019**, yearly installs grew steadily (8.4k → 9.5k), with people served climbing in parallel.  
In **2020–2021**, activity dipped sharply (COVID effect), before recovering in **2022–2025**. By September 2025, the program had already logged **6,734 installs and 8,172 people served**.  

- **Charts:**  
  - Yearly installs & people served (`yearly_installs.png`)  
  - Monthly people served (`monthly_people_served.png`)  

---

### Geographic Reach
Not all territories contributed equally:
- **LA Metro dominates (40,036 installs, 45,391 people)**  
- **Inland Empire** and **Orange County** together add ~35k installs and ~42k people  
- **Central Coast** is smaller in size but most efficient (1.30 people per install)  

- **Chart:** Top 15 territories by installs (`territory_top15_installs.png`)

---

### Timing of Effort
Daily averages:
- **Weekdays:** ~3.6 installs, ~4.1 people served/day  
- **Weekends:** ~3.8 installs, ~4.7 people served/day  
- **Sunday strongest overall**  

- **Charts:**  
  - Day-of-week averages (`dow_mean_installs.png`)  
  - Weekend vs weekday (`weekend_means.png`)  

---

### Cross-Metric Relationships
- **Installs ↔ People served:** correlation **0.73** (strong positive)  
- **Installs ↔ Fire escape plans:** ~0 (independent)  
- **People served ↔ Hazard education:** ~0 (independent)  

- **Charts:**  
  - Scatterplot installs vs people (`scatter_installs_vs_people_monthly.png`)  
  - Correlation heatmap (`corr_heatmap.png`)  

**Installs vs people served (monthly)**
![Installs vs people served (monthly)](reports/figures/eda/scatter_installs_vs_people_monthly.png)

**Correlation heatmap (numeric features)**
![Correlation heatmap](reports/figures/eda/corr_heatmap.png)


- [Numeric correlation matrix](reports/artifacts/eda/numeric_correlation.csv)
- [Behavior-only correlation (if created)](reports/artifacts/eda/numeric_correlation_behavior_only.csv)

---

## Story of a Decade
This synthetic dataset captures the arc of a real campaign:
- A decade of steady growth.
- A sharp but temporary COVID disruption.
- Geographic concentration in major metros, balanced by smaller regions.
- Volunteer mobilization patterns strongest on weekends.
- A reliable proxy KPI: **alarms installed** as shorthand for total program impact.

---

## Disclaimer
This repository uses synthetic data for demonstration and learning. It is not affiliated with, endorsed by, or representing the American Red Cross. Any references to the Red Cross are for contextual, nominative use only.

---

## Next Steps: Predictive & Prescriptive (Notebook 4)
With descriptive analytics complete, the next phase of this project will add:
- **Predictive modeling:** forecasting installs and people served using time-series ML.  
- **Prescriptive analytics:** optimizing resource allocation (territories, weekdays vs weekends) to maximize impact.  

This layered progression — **descriptive → predictive → prescriptive** — demonstrates not only technical capability, but also the ability to tell a data-driven story from end to end.
