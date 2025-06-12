# Energy Forecasting for Smart Homes: Driving Real-Time Efficiency and Solar Optimization

## 1. **Executive Summary**

This project delivers short-term electricity consumption forecasts for smart homes using smart meter and weather sensor data. By applying a structured machine learning pipeline, a LightGBM model was trained and achieved a **mean absolute error (MAE) of 0.068 kW**, substantially outperforming a statistical VAR baseline (0.63 kW).

Beyond predictive accuracy, the model enables **practical smart home features** like high-usage warnings and solar self-consumption tracking—laying the groundwork for smarter energy use and reduced grid dependence.

## 2. **Business Problem & Objective**

While smart homes collect detailed consumption and weather data, households often lack actionable insights. This project aims to turn data into foresight by enabling **accurate short-term energy forecasts** that empower users to:

- Optimize appliance scheduling
- Maximize solar self-consumption
- Reduce peak-time electricity costs

### Value Delivered

- Forecast precision: **MAE = 0.068 kW** (LGBM), outperforming **0.63 kW** (VAR baseline)  
- Enabled smart home use cases: usage warnings, solar tracking, SHAP-driven transparency  
- Foundation for CO₂-aware and cost-optimized decision support

## 3. **Data & Methodology**

The project follows the **CRISP-DM** framework and uses a modular notebook pipeline inspired by the **FTI architecture** (separation of pipeline steps in feature, training and inference pipelines):

### Process Overview:
- `01_data_description.ipynb`: Initial structure, summary stats, correlations
- `02_exploratory_data_analysis.ipynb`: Trends, conditions, and anomalies
- `03_data_cleaning.ipynb`: Resampling, renaming, merging, time features
- `04_data_encoding.ipynb`: One-hot encoding
- `05_time_series_analysis.ipynb`: Seasonality, temporal profiles, Granger tests
- `06_train_test_split.ipynb`: Chronological 80/20 split
- `07_var_forecast.ipynb`: Baseline using autoregression
- `08_lgbm_forecast.ipynb`: Tuned LightGBM with SHAP explainability
- `09_smart_home_use_cases.ipynb`: Real-world applications using model predictions

### Key Technologies

- **Pandas, NumPy, Matplotlib, Seaborn**  
- **LightGBM, Optuna, SHAP**  
- **Scikit-learn, Statsmodels**  
- **Joblib, PyOD**  

## 4. **Results & Business Insights**

### Forecast Accuracy
- **VAR baseline MAE:** 0.6263 kW
- **LightGBM MAE:** 0.0680 kW → strong foundation for smart energy control

### Model Explainability (SHAP)
- Key drivers: `furnace`, `fridge`, `winecellar`, and `temperature`
- Increases user and stakeholder trust in predictions

### Use Case Snapshots

**1. Grid Load & Self-Sufficiency Monitoring**  
→ Identify when solar generation exceeds predicted demand  
→ Highlight time windows for maximizing self-consumption

**2. High Consumption Alerts**  
→ Detect forecasted spikes > 1.5 kW  
→ Prototype warning system for user feedback or automation

**3. Appliance Influence Over Time**  
→ Track SHAP values across time for appliances like `furnace`

**4. Model Baseline Comparison**  
→ Quantify uplift versus naive forecasts

**5. Daily Usage Patterns**  
→ Profile typical consumption by hour and weekday

Exemplary use cases are implemented in `09_smart_home_use_cases.ipynb`.

## 5. **Conclusion & Next Steps**

### Summary
- Accurate short-term forecasts unlock **tangible value** for smart energy systems
- SHAP explainability builds confidence and auditability
- Use-case driven outputs highlight real-world readiness

### Current Limitations
- No real-time deployment pipeline (e.g. API, dashboard)
- Solar input assumed known – no independent PV forecast
- No appliance-specific modeling (e.g. NILM)

### Roadmap
- Deploy API or Streamlit app for live consumption forecasting
- Extend horizon to multi-day forecasts with solar prediction modules
- Integrate pricing, CO₂ intensity, and comfort constraints
- Expand to appliance disaggregation via classification or deep learning

---

## Development Setup 

Setup is done with astral uv
https://docs.astral.sh/uv/

### Setup virtual environment with UV

```bash
uv venv .venv
```

activate your venv, then continue with the next step

```bash
uv init
```

```bash
uv add pip ipykernel
```

add packages from pyproject.toml

```bash
uv pip install .
```

add single packages

```bash
uv add scikit-learn
```

### Install Pre-Commit Hooks

on CLI run:

```bash
pre-commit install
pre-commit run --all-files
```
