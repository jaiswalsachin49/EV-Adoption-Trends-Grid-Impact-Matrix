# EV Adoption Trends & Grid Impact Matrix

Welcome to the **EV Adoption Trends & Grid Impact Matrix** project. This repository contains a data-centric analysis built for a regional electrical utility company to track the rapid integration of Electric Vehicles (EVs) in Washington State and understand its subsequent impact on electricity grid load.

## Business Problem

As Electric Vehicles adoption surges—and state mandates push for further electrification of transportation—regional electrical utility companies face unprecedented peak load demands. By analyzing vehicle registration density and vehicle types across zip codes, utilities can proactively:

1. **Manage Grid Load:** Prevent localized brownouts by identifying high EV growth clusters.
2. **Influence Policy:** Guide investments into public Level-2 and Level-3 charging infrastructure.
3. **Forecast Energy Demand:** Model power demands based on BEV (Battery Electric) vs. PHEV (Plug-in Hybrid) distributions.

## Tech Stack

- **Data Engineering (ETL):** Python (Pandas, Numpy)
- **Exploratory Data Analysis (EDA):** Matplotlib, Seaborn, Plotly
- **Data Visualization & Dashboard:** Tableau (Coming Soon)
- **Environment:** Jupyter Notebooks (`requirements.txt` included)

## Repository Structure

- `datasets/raw_dataset/`: Raw CSV file of EV population data.
- `datasets/cleaned_dataset/`: Cleaned, ETL-processed data exported for Tableau connection.
- `notebooks/`: 
  - `01_etl_and_cleaning.ipynb` - Data extraction, parsing spatial data, and transforming variables.
  - `02_eda_and_statistical_analysis.ipynb` - Data visualizations, YoY adoption growth calculations, and statistical insights.
- `dashboard/`: Dashboard Image
- `report/`: Executive Summary & insights for non-technical stakeholders.


## How to Run locally

1. Clone the repository natively or open it up in your local VS Code / DataSpell environment.
2. Ensure you have the datasets downloaded.
3. Run `pip install -r requirements.txt`.
4. Run `01_etl_and_cleaning.ipynb` to generate the final analytical flat file under `datasets/cleaned_dataset/`.
5. Connect your BI tool to the generated output!
