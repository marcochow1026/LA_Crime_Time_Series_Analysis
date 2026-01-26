# LA_Crime_Time_Series_Analysis

# Los Angeles Crime Time Series Analysis

![LA Skyline](https://images.unsplash.com/photo-1540979388789-7cee28a1cdc9?auto=format&fit=crop&w=1200&q=80)  
*(Exploratory time series analysis of crime patterns in Los Angeles)*

## Overview

This project analyzes crime data in the City of Los Angeles using time series techniques to uncover temporal patterns, seasonality, trends, and potential forecasting capabilities.

Main objectives:
- Understand long-term trends in total crime volume
- Identify seasonal and weekly patterns
- Compare crime types (violent vs. property vs. others)
- Evaluate multiple forecasting models
- Provide interpretable insights for urban policy / public safety discussion

## Dataset

**Source**: Los Angeles Open Data Portal  
**Main file**: [Crime Data from 2020 to Present](https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8)  
**Format**: CSV (~1.2M rows as of late 2025 / early 2026)

Key columns used:
- `DATE OCC` / `DATE RPTD` — crime occurrence date
- `TIME OCC` — time (HHMM format)
- `Crm Cd Desc` / `Crm Cd` — crime type & code
- `AREA NAME` / `AREA` — geographic area / division
- `LAT` / `LON` — location coordinates
- `Vict Age`, `Vict Sex`, `Vict Descent` — victim demographics (used in some breakdowns)

## Project Structure

```text
LA_Crime_Time_Series_Analysis/
├── data/
│   ├── raw/                  # original downloaded CSVs (not committed)
│   └── processed/            # cleaned & aggregated time series data
│
├── notebooks/
│   ├── 01_data_exploration.ipynb          # initial EDA, cleaning, geocoding checks
│   ├── 02_time_series_preparation.ipynb   # aggregation to daily/weekly/monthly
│   ├── 03_exploratory_analysis.ipynb      # trends, seasonality, decomposition
│   ├── 04_modeling_arima_prophet.ipynb    # classical & Facebook Prophet models
│   ├── 05_deep_learning_forecast.ipynb    # LSTM / GRU experiments (optional)
│   └── 06_evaluation_comparative.ipynb    # model comparison, metrics
│
├── src/
│   ├── data/
│   │   └── preprocess.py
│   ├── features/
│   │   └── build_features.py
│   ├── models/
│   │   └── forecast_models.py
│   └── visualization/
│       └── plots.py
│
├── reports/
│   └── figures/              # exported high-quality plots
│
├── requirements.txt
├── README.md
└── .gitignore
