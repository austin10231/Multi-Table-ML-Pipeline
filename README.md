# Multi-Table ML Pipeline

## Author

**Mutian He**  
2026


## Overview

This repository contains a collection of end-to-end machine learning projects
built on **multi-table relational datasets**.  
Each project focuses on transforming normalized transactional data into
model-ready features through systematic **multi-table feature engineering**.

The repository includes both **classification** and **regression** tasks,
with a strong emphasis on:
- relational data modeling
- temporal feature extraction
- aggregation across multiple tables
- reproducible machine learning pipelines

---

## Repository Structure

```
Multi-Table-ML-Pipeline/
├── Classification/
│ ├── Project-specific folders
│ └── README.md
│
├── Regression/
│ ├── Project-specific folders
│ └── README.md
│
└── README.md
```


---

## Classification Projects

The `Classification` directory contains projects focused on predicting
categorical outcomes using multi-table datasets.

Typical problem settings include:
- binary classification (e.g., delay vs. no delay)
- user behavior prediction
- reorder or churn prediction

Each project generally includes:
- raw and processed datasets
- feature engineering pipelines
- model training and evaluation
- visualizations (ROC curves, confusion matrices, etc.)

---

## Regression Projects

The `Regression` directory contains projects focused on predicting continuous
values from multi-table datasets.

Typical problem settings include:
- delivery time estimation
- sales or demand forecasting
- numerical outcome prediction based on transactional history

Each project follows a similar pipeline structure:
- multi-table joins and aggregations
- feature construction
- regression modeling
- performance evaluation

---

## Core Techniques

Across all projects, the following techniques are commonly applied:

- Multi-table joins and relational modeling
- Temporal feature extraction (hour, weekday, month, lag features)
- Aggregation-based feature engineering
- Handling class imbalance and skewed distributions
- Threshold tuning for classification tasks
- Model evaluation using appropriate metrics

---

## Tech Stack

- **Language**: Python
- **Data Processing**: Pandas, NumPy
- **Modeling**: scikit-learn
- **Visualization**: Matplotlib, Seaborn
- **Environment**: Jupyter Notebook

---

## Copyright

© 2026 Mutian He. All rights reserved.
