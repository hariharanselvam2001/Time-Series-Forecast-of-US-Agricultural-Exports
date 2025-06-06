# 🌾 U.S. Agricultural Exports Forecasting (1975–2024)

This project utilizes agricultural trade data from 1975 to 2024 to forecast **U.S. agricultural exports** using **time series modeling**. It analyzes key features such as **imports, exports, and trade balances**, and applies advanced techniques to overcome challenges like **seasonality, volatility**, and **global trade dynamics**.

---

## 🎯 Objective

- 📈 Forecast U.S. agricultural exports accurately.
- 🧭 Support strategic trade planning for policymakers.
- 🌍 Capture the influence of global trade dynamics.
- 📊 Equip stakeholders with actionable insights for better decision-making.

---

## 📚 Dataset Overview

- **Source**: [USDA ERS – U.S. Agricultural Trade Data Update](https://www.ers.usda.gov/)
- **Span**: 1975–2024
- **Granularity**: Monthly data
- **Raw Format**: No seasonal adjustments

---

## 🔄 Project Flow

1. **Analyzing Trade Trends** – Initial exploration of exports and imports.
2. **Pre-processing** – Handling missing values, transforming variables.
3. **Stabilizing Variance** – Using Log and Box-Cox transformations.
4. **Stationarity Check** – Differencing and statistical tests.
5. **Model Building** – SARIMA and SARIMA-EXO (with Imports).
6. **Evaluation & Forecasting** – Model performance, visualizations, and interpretation.

---

## 📊 Trend Analysis – Exports

### 🔹 Before Log Transformation
- High variance, non-stationary, seasonal patterns.
  
### 🔹 After Log Transformation
- Variance stabilized.
- Better identification of patterns.
- Suitable for time series modeling.




## 🧩 Export Variable Decomposition

Using **classical multiplicative decomposition**, exports were broken down into:

- **Original**: Upward trend with seasonal fluctuations.
- **Trend**: Long-term growth, impacted by external events.
- **Seasonality**: Peaks in Mar–Sep, increases again Nov–Dec.
- **Residuals**: Irregular, non-patterned variations.

---

## 📈 Seasonal Patterns Across Years

- Export levels rose significantly from 1980s to 2020s.
- Consistent annual patterns.
- Spikes in trade aligned with agricultural production cycles.

---

## 🧠 Model Building: SARIMA

- Addressed seasonality & stationarity.
- Analyzed ACF & PACF of differenced exports.
- Chose **SARIMA(1,1,1)(2,1,5)[12]** based on lowest AIC/BIC.

### 📌 Diagnostics

- ✅ Stationarity achieved
- ✅ Seasonality detected (lag 12)
- ✅ Residuals passed Ljung-Box test
- 📉 MAPE: **2.34%**

---

## 🧪 SARIMA vs SARIMA-EXO (with Imports)

### 🔸 Imports as Exogenous Variable
- Imports strongly correlate with exports.
- Box-Cox used for variance stabilization.
- Adds external explanatory power to the model.

### 📊 Comparison

| Metric         | SARIMA         | SARIMA-EXO     |
|----------------|----------------|----------------|
| MAE            | 435M           | **420M**       |
| RMSE           | 592M           | **579M**       |
| MAPE           | 2.34%          | **Lower**      |

**SARIMA-EXO improves forecasting accuracy** and better reflects trade dynamics.

---

## ✅ Conclusion

- SARIMA models effectively capture seasonal and temporal dependencies.
- Adding **Imports** as an exogenous variable further enhances predictive power.
- The model supports better economic and trade policy formulation.

---

## 🛠 Tech Stack

- Python, Pandas, NumPy, Statsmodels
- Matplotlib, Seaborn
- Time Series Modeling: SARIMA, SARIMA-EXO
- Box-Cox, Differencing, ACF/PACF, Ljung-Box Test



