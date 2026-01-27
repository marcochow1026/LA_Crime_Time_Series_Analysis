# Los Angeles Violent Crime Time Series Analysis

**Repository:** [marcochow1026/LA_Crime_Time_Series_Analysis](https://github.com/marcochow1026/LA_Crime_Time_Series_Analysis)

This project performs a time series analysis on **Part I Violent Crimes** in the City of Los Angeles, using publicly available crime data from 2010 to early 2024. The focus is on identifying long-term trends, seasonal patterns (especially summer peaks), and out-of-sample forecasting performance.

![Monthly Violent Crimes in Los Angeles (2010–Feb 2024)](https://raw.githubusercontent.com/marcochow1026/LA_Crime_Time_Series_Analysis/main/figures/monthly_violent_crimes.png)  
*(Example time series plot of monthly violent crime counts – generated from the notebook)*

## Project Overview

Main objectives:
- Combine historical (2010–2019) and recent (2020–present) crime datasets
- Filter to **Part I Violent Crimes** (FBI Uniform Crime Reporting Part I offenses)
- Clean data and aggregate to monthly counts
- Visualize trends and seasonality
- Evaluate forecasting models on held-out test data (last 24 months)
- Provide actionable insights for law enforcement

**Key finding**: Violent crime shows clear seasonal spikes in summer months. Forecasting models achieve reasonable accuracy (MAE ≈ 171.5 crimes/month, MAPE ≈ 7.09%, RMSE ≈ 203 crimes/month on the test set).

## Dataset

**Sources**:
- [Crime Data from 2010 to 2019](https://data.lacity.org/Public-Safety/Crime-Data-from-2010-to-Present/63jg-8b9z) (historical)
- [Crime Data from 2020 to Present](https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8) (ongoing)

**Filtering criteria** — Part I Violent Crimes (FBI codes):
- Homicide: 110, 113
- Rape/Sexual Assault: 121, 122, 815, 820, 821
- Robbery: 210, 220
- Aggravated Assault: 230, 231, 235, 236, 250, 251, 761, 926

Data after **March 2024** is excluded due to a reported change in federal reporting requirements (new law mandating centralized government database storage), which caused an artificial drop in recorded counts (Okpako, 2025).

Processed data is saved as `violent_crimes.csv` (not committed to repo due to size; generate it locally).

## Notebooks

- **`LA_Crime_Time_Series_Analysis_1.ipynb`**  
  Main analysis notebook (with outputs). Covers:
  - Data loading & filtering (past code commented out)
  - Monthly aggregation and time series plotting
  - Out-of-sample forecast evaluation (last 24 months held out)
  - Metrics & recommendation

- **`LA_Crime_Time_Series_Analysis_trim.ipynb`** (or similar original version without outputs)  
  A cleaned/trimmed version without large cell outputs, making it render faster and more cleanly on GitHub. Use this for quick viewing in the browser.

Both notebooks are designed to be run in Jupyter / Colab. The full version may include additional exploratory steps or model training cells not shown in the trimmed file.

## Key Results

- **Trend**: Violent crime counts show post-pandemic recovery patterns with noticeable seasonal peaks (especially summer months).
- **Forecasting performance** (on last 24 months test set):
  - MAE: 171.5 crimes/month
  - MAPE: 7.09%
  - RMSE: 203 crimes/month
- These metrics indicate good predictive accuracy for monthly violent crime volume.

**Recommendation for LAPD**:
Increase police presence and resources during summer months, particularly in high-risk areas and known hotspots, to address seasonal spikes in violent crime.

## Technologies & Requirements

```text
Python 3.8+
pandas
numpy
matplotlib
seaborn
jupyter
