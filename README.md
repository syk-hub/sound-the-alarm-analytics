# Synthetic Sound the Alarm Project (2015–2025)
### Data Storytelling, Descriptive Analytics, and ML-Based Risk Modeling

## Overview
This independent demonstration reproduces the structure of a data-preparation and reporting workflow developed through my fire-safety outreach volunteer work. All data in this repository are synthetic; no confidential operational records are included. The synthetic totals and patterns shown below are demonstration results, not actual American Red Cross program outcomes.

The workflow spans the full analytical arc:

1. **Notebook 1 — Synthetic Data Generation**  
   Programmatically creates a realistic dataset with disturbances (seasonality, anomalies, COVID decline).

2. **Notebook 2 — Cleaning & Structuring**  
   Produces a clean analytical dataset suitable for EDA and modeling.

3. **Notebook 3 — Descriptive Analytics (EDA)**  
   Extracts trends, geographic patterns, program cadence, and KPI relationships.

4. **Notebook 4 — ML Classification Demonstration**  
   Builds a simple Random Forest classifier to identify communities likely to require higher service intensity.

The repository is designed to model a complete data workflow: generation → cleaning → analysis → modeling → insight.

---

## Dataset
**File:** [synthetic_sound_the_alarm_2015_2025_clean.csv](data/synthetic_sound_the_alarm_2015_2025_clean.csv)  
**Nature:** Synthetic (fabricated for demonstration)  
**License:** CC BY 4.0  
**Purpose:** Reproducible EDA + modeling examples  

### How the Data Was Created
The synthetic dataset includes:

- Seasonal peaks and troughs  
- Territory differences in installation and outreach patterns  
- Random noise, outliers, and zero-install events  
- A multi-year COVID dip (2020–2021)  
- Realistic daily operational cadence  

This structure ensures realistic analytical challenges similar to field operations.

---

## Synthetic Dataset Results (2015–2025)

### Scale and Activity
- ~95,000 smoke alarms installed  
- ~111,000 people served  
- ~3,800 operational days  

### Program Patterns
- Strong pre-COVID growth, visible COVID disruption, post-COVID recovery  
- LA Metro dominates in volume (~42% of installs)  
- Central Coast has the highest people-served-per-installation ratio (~1.30 people per install)  
- Weekends outperform weekdays; Sunday highest  
- Installations and people served strongly correlated (r ≈ 0.73)

These patterns reveal how the synthetic campaign evolved geographically and operationally.

---

## Descriptive Analysis (Notebook 3)

Notebook 3 examines trends, geography, timing, and cross-metric relationships.  
Only key figures are linked below; the full set is in:

- [figures](outputs/figures)  
- [tables](outputs/tables)

### Time Trends
- Yearly installs gradually increase 2015–2019  
- Sharp contraction in 2020–2021  
- Recovery afterward through 2025  

**Figure:** [yearly_installs.png](outputs/figures/yearly_installs.png)

### Geographic Patterns
- LA Metro: highest install and outreach volume  
- Inland Empire + Orange County: substantial combined region  
- Central Coast: highest efficiency  

**Figure:** [territory_top15_installs.png](outputs/figures/territory_top15_installs.png)

### Operational Timing
- Weekends consistently stronger  
- Sunday highest activity  

**Figure:** [dow_mean_installs.png](outputs/figures/dow_mean_installs.png)

### Cross-Metric Relationships
- Strong installs ↔ people correlation  
- Weak correlation for escape plans and hazard education  

**Figure:** [corr_behavior_heatmap.png](outputs/figures/corr_behavior_heatmap.png)

These EDA results provide the contextual foundation for the ML component.

---

## ML Classification Demonstration (Notebook 4)

This section demonstrates how descriptive insights transition into predictive analytics.

### Objective
Identify territories likely to require higher outreach intensity (above-median community impact).

### Modeling Steps
1. **Feature Engineering**  
   Transforms operational metrics into structured predictors.

2. **Target Construction**  
   `high_risk = 1` for above-median community impact.

3. **Model Training**  
   - Random Forest classifier  
   - Stratified train/test split  
   - Weighted classes to address imbalance  

4. **Evaluation**  
   ROC-AUC used to measure ranking performance.

5. **Risk Scoring & Ranking**  
   Each territory receives a `predicted_risk` probability.

### Key Outputs
- **Feature Importances:**  
  [ml_feature_importances_notebook4.png](outputs/figures/ml_feature_importances_notebook4.png)  
  [ml_feature_importances_notebook4.csv](outputs/tables/ml_feature_importances_notebook4.csv)

- **Territory Risk Ranking (Styled):**  
  [ml_territory_risk_ranking_notebook4.html](outputs/figures/ml_territory_risk_ranking_notebook4.html)  
  [ml_territory_risk_ranking_notebook4.csv](outputs/tables/ml_territory_risk_ranking_notebook4.csv)

### Interpretation and Limitations

In this synthetic dataset, installation activity is associated with the number of people served, so it helps classify above-median service-volume records. This demonstrates relationships within the generated data rather than establishing real-world community risk.

The project demonstrates data preparation, descriptive analysis, and supervised classification. Forecasting future outreach demand would require a defined future outcome, predictors available before that outcome, and evaluation on later time periods.

---

## Disclaimer
This repository uses synthetic data for educational and demonstration purposes. It is not affiliated with, endorsed by, or representing the American Red Cross. Any references to the Red Cross are contextual only.
