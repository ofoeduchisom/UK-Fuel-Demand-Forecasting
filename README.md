# Fuel Demand Forecasting

Forecasting fuel demand while accounting for macroeconomic factors such as inflation enables accurate operational planning, pricing strategies, and inventory management across the energy sector. This project presents the dataset, methodology, models, key results, and business-focused recommendations.

---

## 📌 Business Applications

* Demand forecasting for supply chain optimization
* Budget planning & resource allocation
* Economic impact analysis on consumer behavior
* Peak-period preparation & capacity planning

---

## 🎯 Key Results

* **Best Model:** Triple Exponential Smoothing → *MAE: 1.46, RMSE: 2.09*
* **Forecast Horizon:** 52 weeks ahead
* **Key Insight:** Negative correlation between inflation & fuel demand (**r = −0.68**)
* **Peak Demand:** April 2025 → **105.69 units**
* **Holiday Surge:** Christmas period → **207.64 units**

---

## 📊 Dataset

* **Source:** Office for National Statistics (ONS)
* **Period:** Jan 2021 – Feb 2025 (214 weeks)
* **Frequency:** Weekly
* **Primary Variable:** Estimated demand per transaction
* **Exogenous Variable:** Weekly inflation rate (CPI-based)

---

## ⚙️ Methodology

### 1. Data Preprocessing

* Removed duplicates, resampled to weekly frequency
* Outlier handling (IQR method)
* Missing values filled using linear interpolation
* Merged demand with inflation data

### 2. Exploratory Analysis

* Seasonal decomposition (additive & multiplicative)
* Trend & cyclic pattern analysis
* Correlation analysis with inflation
* Stationarity testing (ADF test)

### 3. Data Transformation

* First-order differencing for stationarity
* ACF/PACF plots for lag identification
* Granger causality test (inflation impact validation)

### 4. Model Development

Five models compared:

| Model                            | MAE  | RMSE | MAPE  | Use Case       |
| -------------------------------- | ---- | ---- | ----- | -------------- |
| **Triple Exponential Smoothing** | 1.46 | 2.09 | 1.90% | Best overall   |
| ARIMA (0,0,2)                    | 1.39 | 3.14 | 23%   | Baseline       |
| SARIMA (1,0,1)(2,0,0)[52]        | 1.68 | 2.89 | 11.9% | Seasonal       |
| SARIMAX (1,0,1)(2,0,0)[52]       | 1.43 | 2.15 | 14.7% | With inflation |
| VAR (5)                          | 1.43 | 3.14 | 21.7% | Multivariate   |

### 5. Validation

* Residual analysis → white noise confirmed (Ljung–Box p = 0.71)
* Reverse differencing for original scale forecasts
* Out-of-sample evaluation

---

## 📈 Forecast Summary

* **Next 30 weeks total:** 3,098.54 units
* **Peak Week:** April 6, 2025 → 105.69 units
* **Christmas Surge:** 207.64 units

---

## 🔎 Business Insights

* **Seasonality:** Weekly fluctuations with holiday peaks
* **Trend:** Demand dip in mid-2022, recovery & peak in 2023
* **Inflation Effect:** 10% rise in inflation → ~5% drop in demand

---

## ✅ Key Features

* Multivariate forecasting with macroeconomic indicators
* 5 model comparison with performance metrics
* 4+ years of weekly data
* Business-driven insights
* Rigorous validation & diagnostics

---

## 📌 Recommendations

1. Deploy **Triple Exponential Smoothing** for planning pipelines
2. Use inflation elasticity for scenario analysis
3. Prepare surge capacity for forecasted peak periods
4. Retrain models monthly with updated inflation data

---

**Prepared by:** Forecasting & Analytics Team
