# Walmart Weekly Sales Forecasting

Author: 2026 · Mutian He

A machine learning project to predict **weekly sales** at the Store–Department level using historical sales data and external economic indicators.

## Overview
- Merged sales, store attributes, and macroeconomic features
- Performed time-aware train/test split to avoid data leakage
- Applied log transformation to stabilize skewed sales distribution
- Compared multiple regression models

## Features
- Store & department identifiers
- Store size and type (one-hot encoded)
- Cyclical time features (week/month sine & cosine)
- Economic indicators (CPI, unemployment, fuel price)
- Promotional markdown signals

## Models & Results
- Models: Linear Regression, Ridge, Random Forest, XGBoost
- Best model: **Random Forest**
  - R² ≈ 0.93
  - RMSE ≈ \$3,900 (weekly sales, original scale)

## Tech Stack
Python, pandas, numpy, scikit-learn, xgboost

## License
© 2026 He Mutian. All rights reserved.
