# EV Adoption Trends & Grid Impact Matrix

A comprehensive data analytics project built to provide actionable intelligence for a regional electrical utility company, tracking the rapid integration of Electric Vehicles (EVs) in Washington State and measuring its subsequent impact on the municipal electricity grid.

![Tableau Dashboard Preview](dashboard/dashboard.png)

---

## Problem Statement and Stakeholder Context

As Electric Vehicle adoption surges—driven by state mandates and consumer trends—regional electrical utility companies are facing unprecedented peak load demands. The stakeholders for this project are **Infrastructure Planners and Grid Operators**. 

By analyzing vehicle registration density and vehicle types across zip codes, utilities must proactively:
1. **Manage Grid Load:** Prevent localized brownouts by identifying high EV growth clusters.
2. **Influence Policy:** Guide data-driven investments into public Level-2 and Level-3 charging infrastructure.
3. **Forecast Energy Demand:** Model power demands based on BEV (Battery Electric) vs. PHEV (Plug-in Hybrid) distributions.

---

## Dataset Source and Scope

* **Source:** Washington State Department of Licensing (DOL) open data portal.
* **Scope:** Analyzed over 150,000+ active EV registrations. 
* **Key Variables:** Vehicle Location (Spatial coordinates), Electric Range, Clean Alternative Fuel Vehicle (CAFV) Eligibility, Make, and Model Year.

---

## Cleaning and Transformation Summary

A programmatic ETL pipeline (`01_etl_and_cleaning.ipynb`) was built using `pandas` to prepare the raw data for Tableau:
1. **Spatial Parsing:** Extracted raw WKT (Well-Known Text) string formats `POINT (Long Lat)` into robust, distinct numerical `Latitude` and `Longitude` columns for mapping.
2. **Binary Transformation:** Simplified verbose CAFV eligibility rules into a clean `1`/`0` boolean flag for streamlined statistical grouping.
3. **Geographic Filtering:** Removed out-of-bounds outliers and constrained the scope strictly to Washington (`WA`), validating the utility's regional boundaries.

---

## KPI Framework

To monitor grid impact dynamically, the dashboard tracks the following core Key Performance Indicators (KPIs):
* **Total Active EV Registrations:** Snapshot of absolute load potential.
* **YoY Adoption Growth Rate (%):** Calculates momentum to predict short-term localized surges.
* **BEV vs. PHEV Ratio:** Identifies heavy power draw (BEV) vs. moderate power draw (PHEV) populations.
* **CAFV Compliance Rate:** Measures adherence to clean energy mandates.

---

## 3-5 Key Insights

Based on the Exploratory Data Analysis (`02_eda_and_statistical_analysis.ipynb`):
1. **Exponential YoY Growth:** Registrations show sustained double-digit percentage growth over the last 5 years, confirming that grid stress is an escalating curve, not a static problem.
2. **BEV Demand Density:** Battery Electric Vehicles (BEVs), which draw entirely from the grid without a secondary combustion engine, make up the vast majority. This fundamentally alters neighborhood load capacities.
3. **Tesla's Historic Monopoly:** Tesla has historically dominated the 'Clean' category, representing the bulk of the infrastructure impact, though legacy automakers are beginning to dilute this.
4. **Range Expansion:** Overall minimum battery range continues to increase across models. Higher range unlocks "long-haul" capacity, indirectly shifting consumer charging behavior into overnight windows.

---

## Recommendations and Expected Impact

1. **Targeted Substation Upgrades:** 
   * *Recommendation:* Use geospatial clustering to identify the top 5% of zip codes with the highest BEV density.
   * *Impact:* Priority transformer upgrades in these zones will prevent localized brownouts and improve grid reliability.
2. **Incentivize Off-peak Charging (TOU Rates):** 
   * *Recommendation:* Given the high concentration of fully electric fleets, aggressively market Time-of-Use rates between 10 PM and 6 AM.
   * *Impact:* Shifting charging schedules will significantly alleviate PM (5 PM - 8 PM) peak loading.

---

## Tech Stack & Repository Structure

* **Language/Libraries:** Python 3 (Pandas, Numpy, Matplotlib, Seaborn, Plotly)
* **Visualization:** Tableau

```text
EV-Adoption-Trends-Grid-Impact-Matrix/
│
├── datasets/
│   ├── raw_dataset/             # Original uncleaned CSV data
│   └── cleaned_dataset/         # Processed data, optimized for Tableau
│
├── notebooks/
│   ├── 01_etl_and_cleaning.ipynb            # Extraction & Transformation pipeline
│   └── 02_eda_and_statistical_analysis.ipynb # Statistical insights & visualization
│
├── dashboard/                   # Tableau dashboard screenshots
│
├── report/
│   └── Executive_Summary.md     # In-depth executive summary for managers
│
└── README.md                    # Project documentation
```

### How to Run Locally
1. Clone the repository and navigate to the project directory.
2. Run `pip install -r requirements.txt`.
3. Open and run `notebooks/01_etl_and_cleaning.ipynb` to generate the finalized `Cleaned_EV_Population_Data.csv`.
4. Import the resulting CSV into Tableau to interact with the geographic distributions!
