<h1 align="center">🏗️ U.S. Construction Spending Forecasting</h1>
<p align="center">
An end-to-end time series forecasting analysis using R's fable framework <br>
to model and predict U.S. total construction spending from 2002 to 2023.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/R-%23276DC3?logo=R&logoColor=white" alt="R">
  <img src="https://img.shields.io/badge/Tidyverse-999999?logo=rstudio&logoColor=white" alt="Tidyverse">
  <img src="https://img.shields.io/badge/fpp3-TimeSeries-blueviolet" alt="fpp3">
  <img src="https://img.shields.io/badge/fable-Forecasting-success" alt="fable">
  <img src="https://img.shields.io/badge/ggplot2-Visualization-orange" alt="ggplot2">
</p>

---

## 🎯 Objective

This project aims to:
- Analyze monthly trends in **U.S. construction spending**
- Decompose the time series into **trend, seasonality, and noise**
- Apply and compare models such as **ARIMA**, **ETS**, and **Naïve Seasonal**
- Forecast the next 12 months with **confidence intervals**
- Deliver actionable insights through visuals and statistical metrics

---

## 📊 Dataset Overview

| Attribute        | Value                                  |
|------------------|------------------------------------------|
| **Source**       | [FRED](https://fred.stlouisfed.org/) (Federal Reserve Economic Data) |
| **Series**       | `TLRESCON` – Total U.S. Construction Spending |
| **Frequency**    | Monthly |
| **Range**        | Jan 2002 – Dec 2023 |
| **Unit**         | Millions of USD |
| **Transform**    | Log transformation for variance stabilization |

---

## 🧰 Tech Stack

| Tool / Library     | Description                             |
|--------------------|------------------------------------------|
| ![R](https://img.shields.io/badge/R-%23276DC3?logo=R&logoColor=white) | Language used for analysis |
| ![fpp3](https://img.shields.io/badge/fpp3-TidyTimeSeries-blueviolet) | Forecasting framework (`fable`, `feasts`, `tsibble`) |
| ![fable](https://img.shields.io/badge/fable-Modeling-green) | ARIMA, ETS models |
| ![tsibble](https://img.shields.io/badge/tsibble-TimeSeriesTibble-blue) | Time-indexed data structures |
| ![ggplot2](https://img.shields.io/badge/ggplot2-Visualization-orange) | Visualizations |
| ![Quarto](https://img.shields.io/badge/Quarto-HTML_Report-lightgrey?logo=quarto&logoColor=black) | For generating HTML analysis |

---

## 🔁 Forecasting Workflow

### 📌 Step 1: Data Preprocessing
- Converted FRED CSV into a `tsibble` object
- Applied `log()` transformation to stabilize increasing variance
- Handled missing or irregular time points

### 🔎 Step 2: Decomposition
- Applied **STL decomposition**:
  - 🔺 Trend component
  - 🔁 Seasonal component
  - ✨ Remainder (noise)
- Clear seasonal spikes visible across yearly cycles

### 📈 Step 3: Stationarity Check
- Applied both **regular and seasonal differencing**
- Used **ACF/PACF** to check lags
- Confirmed stationarity visually and statistically

---

## 📦 Models Compared

| Model              | Description                                 |
|-------------------|---------------------------------------------|
| **ARIMA (1,1,1)(0,1,1)[12]** | Seasonal ARIMA model using `fable::ARIMA()` |
| **ETS (M,A,M)**    | Exponential Smoothing with automatic selection |
| **Naïve Seasonal** | Benchmarked using `SNAIVE()` for seasonal trend |

---

## 📉 Model Evaluation

| Metric              | ARIMA        | ETS          | Naïve Seasonal |
|---------------------|--------------|--------------|----------------|
| RMSE                | ✅ Lowest     | Moderate     | ❌ Highest     |
| MAE                 | ✅ Best       | Good         | ❌ Poor        |
| Residual ACF        | ❌ No lags    | Few lags     | Significant autocorrelation |
| Ljung-Box p-value   | ✅ > 0.05     | Acceptable   | ❌ < 0.05       |

✅ **ARIMA outperformed** ETS and Naïve models on residual diagnostics and forecasting accuracy.

---

## 🔮 Final Forecast Output

- Forecasted **log construction spending** for 12 months ahead
- Back-transformed to original scale
- Plotted **95% confidence intervals**
- Captured seasonality and growth without overfitting

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/FRED_logo.svg/320px-FRED_logo.svg.png" width="180" />
</p>

---

## 📌 Key Insights

- Strong **seasonal patterns** around late spring and summer months
- Evidence of **post-2020 volatility** stabilizing in 2023
- Log-transformation and seasonal differencing were crucial
- **ARIMA is the most reliable model** for forecasting cyclical economic indicators like construction spending

---

## 🧠 Learnings & Concepts Used

- Classical decomposition & STL
- ARIMA diagnostics (stationarity, residual analysis)
- Seasonality handling via differencing & SARIMA
- Cross-model comparison using RMSE, MAE, Ljung-Box
- Importance of **forecast interpretability** for decision-makers

---

## 📁 Deliverables

| File Name                                  | Description                         |
|--------------------------------------------|-------------------------------------|
| `CONSTRUCTION SPENDING FINAL ANALYSIS.html` | Quarto-based HTML report with all visuals, model summaries, and insights |

---

## 👨‍🎓 Author

**Sarath Sai Sujith Srinivas Grandhe**  
M.S. Business Analytics  
University of Cincinnati  
📧 grandhss@mail.uc.edu

---

## 📜 License

This project is licensed for academic, educational, and research purposes. Please credit appropriately.

---

⭐️ *If this project helped you understand time series forecasting, feel free to star the repository and fork it for your own applications!*
