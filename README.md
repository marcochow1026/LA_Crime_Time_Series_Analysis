# Los Angeles Crime Time Series Analysis

Exploratory time series analysis and forecasting of crime incidents in the City of Los Angeles using publicly available open data.

![Los Angeles skyline at night](https://images.unsplash.com/photo-1540979388789-7cee28a1cdc9?auto=format&fit=crop&w=1200&q=80)

## Project Overview

This project analyzes temporal patterns in crime data reported in Los Angeles from 2020 onward. The main goals are:

- Clean and preprocess the raw crime dataset
- Aggregate incidents into time series (daily / monthly)
- Perform exploratory data analysis → trends, seasonality, decomposition
- Apply time series forecasting models
- Compare model performance and visualize predictions

The analysis is implemented in one consolidated Jupyter notebook:  
**`LA_Crime_Time_Series_Analysis_trim.ipynb`**

## Dataset

**Source**  
Los Angeles Open Data Portal  
[Crime Data from 2020 to Present](https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8)

- Format: CSV
- Coverage: January 2020 → present (updates frequently)
- Key fields used:
  - `DATE OCC` → date of occurrence
  - `TIME OCC` → time (HHMM)
  - `Crm Cd Desc` / `Crm Cd` → crime description & code
  - `AREA NAME` → geographic division
  - `LAT` / `LON` → coordinates
  - Victim demographics (`Vict Age`, `Vict Sex`, `Vict Descent`)

## Notebook Structure & Main Sections

1. **Setup & Library Imports**  
   pandas, numpy, matplotlib, seaborn, plotly, statsmodels, prophet, sklearn, etc.

2. **Data Loading & Initial Cleaning**  
   - Read CSV  
   - Convert date/time columns  
   - Handle missing/invalid values  
   - Filter to relevant records

3. **Feature Engineering & Aggregation**  
   - Extract year, month, day, weekday, hour  
   - Create crime category groupings (violent, property, etc.)  
   - Aggregate to daily and monthly time series

4. **Exploratory Data Analysis**  
   - Overall crime trend over years  
   - Monthly / seasonal patterns  
   - Weekly cycle (weekday vs weekend)  
   - Time-of-day distribution  
   - Decomposition (trend + seasonal + residual) using STL or classical methods  
   - ACF / PACF plots

5. **Time Series Modeling & Forecasting**  
   - Classical approaches:  
     - ARIMA / SARIMA (via statsmodels / pmdarima)  
   - Facebook Prophet (with yearly seasonality + holidays)  
   - Train/test split (e.g. last 12–24 months as test)  
   - Generate point forecasts + uncertainty intervals

6. **Model Evaluation**  
   - Metrics: MAE, RMSE, MAPE  
   - Visual comparison: actual vs predicted values  
   - Residual diagnostics

7. **Visualizations**  
   - Line plots (trends, forecasts)  
   - Seasonal decomposition plots  
   - Heatmaps (weekday × hour)  
   - Bar charts by crime type / area

## Technologies Used

```text
Python 3.9+
pandas
numpy
matplotlib
seaborn
plotly
statsmodels
pmdarima (auto_arima)
prophet
scikit-learn
jupyter
