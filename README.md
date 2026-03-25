# UCT Machine Learning Projects

A collection of end-to-end Machine Learning projects built using Python, covering real-world domains including Smart City infrastructure and Industrial Predictive Maintenance.

---

## 📁 Projects

### 1. 🚦 Smart City Traffic Pattern Forecasting
**Folder:** `smartcity_traffic_forecasting/`

Forecasting hourly traffic volume at 4 city junctions to help governments plan infrastructure and manage peak traffic efficiently.

| Junction | RMSE | MAE | R² |
|----------|------|-----|----|
| Junction 1 | 6.73 | 4.60 | 0.919 |
| Junction 2 | 3.08 | 2.39 | 0.862 |
| Junction 3 | 5.85 | 3.07 | 0.687 |
| Junction 4 | 3.02 | 2.05 | 0.503 |

**Model:** Random Forest Regressor (150 trees)
**Key Feature:** `lag_1` (previous hour traffic) dominates predictions

→ [View Project](./smartcity_traffic_forecasting/)

---

### 2. ✈️ Turbofan Engine RUL Prediction
**Folder:** `TurboRUL_Prediction/`

Predicting the Remaining Useful Life (RUL) of turbofan engines before failure using NASA CMAPSS multivariate time series sensor data.

| Model | RMSE | MAE | R² |
|-------|------|-----|----|
| Linear Regression | 21.03 | 16.70 | 0.7246 |
| Random Forest | 17.89 | 12.57 | 0.8007 |
| Gradient Boosting | **17.37** | **12.14** | **0.8121** |

**Best Model:** Gradient Boosting Regressor
**Dataset:** NASA CMAPSS FD001 (100 engines, 21 sensors)

→ [View Project](./TurboRUL_Prediction/)

---

## 🛠️ Tech Stack

- **Language:** Python 3.10
- **ML Libraries:** Scikit-learn, NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

## 📂 Repository Structure

```
UCT_Machine_Learning_Projects/
├── smartcity_traffic_forecasting/
│   ├── smart_city_traffic_patterns.ipynb
│   ├── README.md
│   └── (plots)
└── TurboRUL_Prediction/
    ├── Turbofan_RUL_Prediction.ipynb
    ├── README.md
    └── Turbofan engine/ (dataset)
```
