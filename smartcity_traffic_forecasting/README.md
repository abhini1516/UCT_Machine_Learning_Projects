# Project 9: Smart City Traffic Pattern Forecasting

## UCT Machine Learning Internship

### Problem Statement
Forecast hourly traffic volume at 4 city junctions to help the government
plan infrastructure and manage peak traffic for a smart city initiative.

### Dataset
- Source: [Kaggle - Smart City Traffic Patterns](https://www.kaggle.com/utathya/smart-city-traffic-patterns)
- Training: 48,120 rows | 4 junctions | Nov 2015 to Jun 2017
- Features: DateTime, Junction, Vehicles (target)

### Approach
- Exploratory Data Analysis (hourly patterns, day-of-week, heatmaps)
- Feature Engineering (cyclic encoding, lag features, rolling averages)
- Model: Random Forest Regressor with 150 trees

### Results
| Junction | MAE | RMSE | R2 |
|----------|-----|------|----|
| Junction 1 | 4.41 | 6.37 | 0.928 |
| Junction 2 | 3.31 | 4.49 | 0.706 |
| Junction 3 | 3.14 | 5.91 | 0.681 |
| Junction 4 | 2.17 | 3.17 | 0.451 |

### Files
- `smart_city_traffic_patterns.ipynb` — main notebook
- `*.png` — EDA and model evaluation plots

### How to Run
1. Download dataset from Kaggle link above
2. Place CSV files in the same folder as the notebook
3. Run all cells top to bottom
