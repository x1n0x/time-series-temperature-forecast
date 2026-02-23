# Winter Temperature Forecasting: Lag-Based Regression and Structural Time-Series Analysis

## 1. Project Overview

This project investigates short-term temperature forecasting using winter-only daily observations (December–February) across five consecutive seasons.

The objective was to:

- Explore temporal dependencies in winter temperature data  
- Construct lag-based forecasting models  
- Compare baseline, linear, and regularized approaches  
- Evaluate structural behavior under recursive forecasting  

The project follows a complete research-style workflow from exploratory data analysis to model diagnostics.

---

## 2. Dataset

The dataset contains daily average temperatures for five winter seasons:

- 2021–2022  
- 2022–2023  
- 2023–2024  
- 2024–2025  
- 2025–2026  

Each season spans approximately 90 days (December–February).

Important limitation:

Only winter months are available. Spring, summer, and autumn data are not included.

---

## 3. Methodology

### 3.1 Feature Engineering

Temporal predictors were constructed:

- Lag features (`lag_1` to `lag_7`)  
- Rolling mean statistics  
- Rolling standard deviation  

All rolling features were shifted to ensure no future information was used (no data leakage).

---

### 3.2 Baseline Models

Two simple benchmarks were implemented:

- Naive forecast (last observed value)
- Rolling mean forecast

These serve as minimum performance references.

---

### 3.3 Machine Learning Models

The following models were evaluated:

- Linear Regression (lag-based)
- Ridge Regression
- Lasso Regression
- Random Forest
- Gradient Boosting

All models were evaluated using RMSE under a chronological train/test split.

---

### 3.4 Final Model Selection

Lag-based Linear Regression achieved competitive performance with:

- Low RMSE  
- High interpretability  
- Minimal complexity  

Regularization provided negligible improvement, and tree-based models did not outperform linear regression.

---

## 4. Why Winter 2026–2027 Was Not Forecasted

A long-horizon winter forecast was intentionally not included as a final result.

Reason:

The dataset contains only winter observations. There is no continuous data between February 2026 and December 2026.

Lag-based and seasonal models require uninterrupted temporal continuity.  
Forecasting the next winter would require predicting unseen spring, summer, and autumn months, which introduces structural instability and accumulated recursive error.

Such a forecast would not be methodologically sound.

Therefore, the project intentionally stops at model evaluation and structural analysis rather than producing an artificial long-term prediction.

---

## 5. Key Lessons Learned

1. Simple models can outperform complex ensembles in structured temporal data.
2. Recursive forecasting amplifies structural model assumptions.
3. Seasonality cannot be inferred without observing the full annual cycle.
4. Forecasting requires alignment between data availability and model structure.
5. Choosing not to forecast can be the correct analytical decision.

---

## 6. What This Project Demonstrates

- Proper time-aware validation  
- Feature engineering without data leakage  
- Model comparison under controlled conditions  
- Structural reasoning in time-series forecasting  
- Awareness of modeling limitations  

---

## 7. Technologies Used

- Python  
- pandas  
- scikit-learn  
- matplotlib  
- seaborn  
- statsmodels (exploratory analysis)

---

## 8. Conclusion

This project emphasizes methodological correctness over artificial prediction.

Rather than forcing a long-horizon forecast unsupported by the dataset, the analysis demonstrates how model structure and data availability determine what can and cannot be predicted.

Understanding limitations is a core part of responsible data science.