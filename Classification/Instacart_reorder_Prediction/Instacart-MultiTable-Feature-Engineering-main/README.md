# Instacart Multi-Table Feature Engineering & Reorder Prediction

Author: Mutian He · 2026

This project builds a machine learning model to predict whether a user will reorder
a product based on historical purchase behavior in the Instacart online grocery dataset.

The main focus of this project is **multi-table feature engineering**, combining
user-level, product-level, and user–product interaction features for prediction.

---

## Project Overview

- Task: Binary classification (predict `reordered`)
- Dataset: Instacart Online Grocery Shopping Dataset
- Techniques:
  - Multi-table feature engineering
  - Model comparison (Logistic Regression, KNN, Random Forest)
  - Threshold tuning based on precision–recall trade-off
  - Model persistence using joblib

---

## Dataset

The original dataset is provided by Instacart and contains multiple relational tables,
including orders, products, users, and order-product interactions.

Due to GitHub file size limits, the raw CSV files are **not included** in this repository.

You can download the dataset from Kaggle:
https://www.kaggle.com/c/instacart-market-basket-analysis/data

After downloading, place the following files into a local `datasets/` directory:
- orders.csv  
- order_products__prior.csv  
- order_products__train.csv  
- products.csv  
- aisles.csv  
- departments.csv  

---

## Feature Engineering

Features are constructed from multiple tables:

### User-level features
- Total number of orders
- Average days between orders
- Average order hour
- Most frequent order day of week

### Product-level features
- Product purchase count
- Product reorder rate
- Number of unique users per product

### User–Product interaction features
- Number of times a user purchased a product
- Last order index of a user–product pair
- User–product purchase ratio

---

## Models

The following models are trained and evaluated:

- Logistic Regression (with standardization)
- K-Nearest Neighbors
- Random Forest

Evaluation metrics include accuracy, precision, recall, and F1-score.

Random Forest achieved the best overall performance.

---

## Threshold Tuning

Instead of using the default probability threshold (0.5), multiple thresholds were
evaluated. A threshold of **0.4** was selected to achieve a better balance between
precision and recall.

---

## Final Model

- Model: Random Forest
- Decision threshold: 0.4
- The trained model is saved using `joblib` for reuse without retraining.

---

## Project Structure

```text
Instacart-MultiTable-Feature-Engineering/
│
├── Instacart_Online_Grocery.ipynb   # Main notebook for feature engineering and modeling
├── datasets/                        # Dataset description (raw data not included)
├── models/                          # Saved trained models
├── README.md
└── requirements.txt
```

© 2026 Mutian He. Released for educational and non-commercial use.
