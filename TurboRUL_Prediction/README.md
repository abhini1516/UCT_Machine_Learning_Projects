# Project 6: Turbofan Engine RUL Prediction

### Problem Statement
Predict the Remaining Useful Life (RUL) of turbofan engines — i.e., how many operational cycles are left before failure — using multivariate time series sensor data from a fleet of engines.

### Dataset
- Source: NASA CMAPSS (Commercial Modular Aero-Propulsion System Simulation)
- 4 sub-datasets (FD001–FD004) with increasing complexity
- 26 columns: unit number, cycle, 3 operational settings, 21 sensor measurements

| Dataset | Train Engines | Test Engines | Conditions | Fault Modes |
|---------|--------------|--------------|------------|-------------|
| FD001   | 100          | 100          | 1          | 1 (HPC Degradation) |
| FD002   | 260          | 259          | 6          | 1 (HPC Degradation) |
| FD003   | 100          | 100          | 1          | 2 (HPC + Fan Degradation) |
| FD004   | 248          | 249          | 6          | 2 (HPC + Fan Degradation) |

### Approach
- Exploratory Data Analysis (engine lifetimes, sensor trends, correlation heatmap)
- Feature Engineering (RUL labels with piecewise linear clipping at 125 cycles, drop low-variance sensors, rolling mean/std over 5 cycles)
- Models compared: Linear Regression (baseline), Random Forest, Gradient Boosting
- Evaluation Metric: RMSE, MAE, R²

### Results (FD001 Test Set)

| Model | RMSE | MAE | R² |
|-------|------|-----|----|
| Linear Regression | 21.03 | 16.70 | 0.7246 |
| Random Forest | 17.89 | 12.57 | 0.8007 |
| Gradient Boosting | **17.37** | **12.14** | **0.8121** |

> Gradient Boosting achieves the best performance with RMSE of 17.37 cycles on FD001 test set.

### Key Findings
1. 7 sensors (sensor_1, 5, 6, 10, 16, 18, 19) had near-zero variance and were dropped as uninformative
2. 14 useful sensors retained: sensor_2, 3, 4, 7, 8, 9, 11, 12, 13, 14, 15, 17, 20, 21
3. Rolling statistics (mean/std over 5 cycles) significantly boost prediction accuracy
4. Piecewise linear RUL clipping at 125 cycles improves model convergence
5. Average engine lifetime in FD001 is 206.3 cycles (range: 128–362 cycles)
6. Gradient Boosting outperforms both Random Forest and Linear Regression

### Files
- `Turbofan_RUL_Prediction.ipynb` — main notebook with full pipeline
- `Turbofan engine/` — dataset folder containing all train/test/RUL text files
- `Turbofan engine/Damage Propagation Modeling.pdf` — original NASA research paper

### How to Run
1. Clone this repo
2. Place the `Turbofan engine/` data folder in the same directory as the notebook
3. Install dependencies:
```bash
pip install numpy pandas scikit-learn matplotlib seaborn
```
4. Open and run `Turbofan_RUL_Prediction.ipynb` top to bottom

### Tech Stack
- Python 3.10
- Scikit-learn (Random Forest, Gradient Boosting, Linear Regression)
- Pandas, NumPy (data processing)
- Matplotlib, Seaborn (visualization)


