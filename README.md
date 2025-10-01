Forecasting fuel demand while accounting for economic factors like inflation enables better operational planning, pricing strategies, and inventory management in the energy sector.

Business Applications:
Demand forecasting for supply chain optimization
Budget planning and resource allocation
Economic impact analysis on consumer behavior
Peak period preparation and capacity planning

Key Results
🎯 Best Model: Triple Exponential Smoothing (lowest MAE: 1.46, RMSE: 2.09)
📊 Forecast Horizon: 52 weeks ahead
📈 Key Insight: Strong negative correlation (-0.68) between inflation rate and fuel demand
📅 Peak Demand: April 2025 (105.69 units)
🎄 Holiday Forecast: 207.64 units during Christmas period

Dataset

Source: Office for National Statistics (ONS)
Period: January 2021 - February 2025 (214 weeks)
Frequency: Weekly observations
Primary Variable: Estimated quantity demand per transaction
Exogenous Variable: Weekly inflation rate (CPI-based)


Methodology
1. Data Preprocessing

Duplicate removal and resampling to weekly frequency
Outlier detection and handling using IQR method
Missing value imputation with linear interpolation
Merging fuel demand with inflation data

2. Exploratory Analysis

Seasonal decomposition (additive & multiplicative)
Trend identification and cyclic pattern analysis
Correlation analysis between fuel demand and inflation
Stationarity testing with Augmented Dickey-Fuller test

3. Data Transformation

First-order differencing to achieve stationarity
ACF/PACF plots for lag identification
Granger causality test for inflation impact validation

4. Model Development
Implemented and compared five forecasting models:
ModelMAERMSEMAPEUse CaseTriple Exponential Smoothing1.462.0991.90%Best overall performanceARIMA(0,0,2)1.393.14123%Baseline univariateSARIMA(1,0,1)(2,0,0)[52]1.682.89119%Seasonal patternsSARIMAX(1,0,1)(2,0,0)[52]1.432.15147%With inflation variableVAR(5)1.433.14217%Multivariate analysis

5. Model Validation
Residual analysis and autocorrelation testing
Ljung-Box test for white noise (p-value: 0.71)
Reverse differencing to original scale
Out-of-sample forecast evaluation


Business Insights
Seasonal Patterns: Regular weekly fluctuations with higher demand on specific days
Trend Analysis: Sharp decrease in mid-2022 followed by peak in mid-2023, indicating sensitivity to economic conditions
Inflation Impact: 10% increase in inflation correlates with approximately 5% reduction in fuel demand
Forecasted Demand:

Next 30 weeks: 3,098.54 total units
Peak week (April 6, 2025): 105.69 units
Christmas period: 207.64 units (indicating seasonal surge)

Key Features
✅ Multivariate forecasting with macroeconomic indicators
✅ Comprehensive model comparison across 5 different approaches
✅ 4+ years of weekly data for robust pattern detection
✅ Business-focused insights with actionable recommendations
✅ Rigorous validation including residual and stationarity testing
