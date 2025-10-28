# Urea Price Prediction — Daily (Data Processing & EDA)

**Notebook:** `Urea_Price_Prediction_Daily_Processed.ipynb`  
**Location:** repository (urea-price-forecasting). :contentReference[oaicite:1]{index=1}

## Summary
This notebook performs data ingestion, cleaning, feature engineering and exploratory data analysis (EDA) on daily urea price data and supporting economic/agricultural indicators. It prepares the processed dataset used by downstream forecasting notebooks.

## Contents
- Load raw datasets (urea prices + external indicators)
- Data cleaning and alignment (dates, missing values)
- Time-based feature engineering (lags, rolling statistics, seasonality indicators)
- Exploratory plots (time series, distribution, correlation matrix)
- Save processed dataset for modeling (CSV/Parquet)

## How to run
1. Clone the repo:
   ```bash
   git clone https://github.com/SamyarZamani/urea-price-forecasting.git
   cd urea-price-forecasting
   ```
2. Start a Python environment (recommended: conda):
   ```bash
   conda create -n urea python=3.10 -y
   conda activate urea
   pip install -r requirements.txt   # or install manually (see below)
   jupyter lab  # or jupyter notebook

   ```
 3.Open `Urea_Price_Prediction_Daily_Processed.ipynb` and run cells top-to-bottom.

### Suggested dependencies

Typical libraries used in the notebook:
- pandas, numpy
- matplotlib, seaborn, plotly (optional)
- scikit-learn
- statsmodels, pmdarima (optional for time-series preprocessing)
- joblib (for saving intermediate artifacts)
Install quickly:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels pmdarima joblib
```
### Outputs

- Cleaned & feature-engineered dataset (recommended to save under `/data/processed/`).
- Diagnostic plots and correlation matrices (for report and README).

### Notes & Recommendations

- Confirm exact file paths used in the notebook (data folder names). I assumed the notebook saves processed outputs for downstream models — if filenames differ, update the export paths accordingly.
- Keep preprocessing deterministic (save random seeds and feature definitions) so the modeling notebooks can reproduce results.

---

# README for `Urea_Price_Forecast_SARIMAX.ipynb`

```markdown
# Urea Price Forecast — SARIMAX Approach
```
**Notebook:** `Urea_Price_Forecast_SARIMAX.ipynb`  
**Location:** repository (urea-price-forecasting). :contentReference[oaicite:3]{index=3}

## Summary
This notebook applies a SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors) model to forecast urea prices. It contains time-series diagnostic steps, model selection (order/seasonal-order), fitting, diagnostics and forecasting with confidence intervals.

## Contents
- Time series diagnostics: ADF / KPSS tests, seasonal decomposition
- Differencing and stationarity handling
- Model selection (manual grid search or information criteria like AIC/BIC)
- Fit SARIMAX with optional exogenous variables (economic/agricultural indicators)
- Model diagnostics (residual plots, Ljung-Box, ACF/PACF)
- Forecast generation and visualization (with prediction intervals)

## How to run
```bash
# create env and install dependencies
pip install pandas numpy statsmodels matplotlib seaborn pmdarima
jupyter notebook Urea_Price_Forecast_SARIMAX.ipynb
```
### Key dependencies

- **statsmodels** (for SARIMAX)
- **pmdarima** *(optional — for automated order selection)*
- **pandas**, **numpy**, **matplotlib** *(for handling and visualization)*

### Outputs

- Fitted SARIMAX model saved *(pickle/joblib)*
- Forecast plots with confidence intervals
- Residual diagnostics and summary table *(AIC/BIC)*

### Notes & Recommendations

- Carefully choose seasonal period `s` *(daily data may require weekly/monthly seasonality depending on the series)*.
- If exogenous regressors are included, ensure they are aligned and preprocessed identically to training period.
- Save model summary and diagnostics to `/results/sarimax/` for reproducibility.

---

### Final note (important)
I generated these READMEs using the notebook filenames and repository metadata you provided (checked the repo and files). :contentReference[oaicite:4]{index=4}

Because the GitHub notebook viewer sometimes loads dynamically, I wrote the READMEs conservatively (clear structure + suggested dependencies) so you can paste them directly. If you want, I can now:

- paste each README into the repo (create/update files) and open a PR, or
- update the READMEs to include exact model names, metric numbers, file paths and final figures after you confirm or paste the exact cells/outputs (or give me permission to read the raw notebooks).



   
