# Credit Risk Prediction with Machine Learning

Author: Mutian He · 2026

This project builds and evaluates machine learning models to identify high-risk (bad) credit card applicants using demographic and credit behavior data.  
The primary goal is to **rank customers by risk level** rather than to make a single hard approval decision.

---

## 📌 Problem Description

Credit risk datasets are typically **highly imbalanced**, with bad customers representing only a small fraction of the population.  
In such scenarios, traditional metrics like accuracy can be misleading.

This project focuses on:
- Identifying high-risk customers
- Comparing different machine learning models
- Evaluating models using **ROC-AUC and Recall**, which are more appropriate for imbalanced classification problems

---

## 📊 Dataset

The dataset consists of **two related tables**:

- **Application Records**  
  Demographic and personal information (e.g., income, education, family status, housing type)

- **Credit Records**  
  Monthly credit behavior and repayment status

These two tables are merged using a unique customer ID.

### Target Construction
- Customers are labeled as **bad (1)** if they have ever shown serious delinquency status (`2–5`)
- All other customers are labeled as **good (0)**

This labeling approach follows common practices in credit risk modeling.

---

## ⚙️ Feature Engineering & Preprocessing

Key preprocessing steps include:

- Merging multi-table data into a single modeling table
- One-hot encoding of categorical features
- Handling extreme values and missing data
- Log transformation of highly skewed numerical features (e.g., income)
- Removing constant or non-informative features
- Addressing class imbalance during model training

---

## 🤖 Models Trained

Three models were implemented and compared:

1. **Logistic Regression**  
   - Used as a baseline model  
   - RobustScaler applied to mitigate the impact of outliers  

2. **Random Forest**  
   - Tree-based ensemble model  
   - Handles nonlinearity and feature interactions  

3. **XGBoost (Extreme Gradient Boosting)**  
   - Boosting-based tree ensemble  
   - Designed to focus on hard-to-classify samples  
   - Includes class imbalance handling via `scale_pos_weight`

---

## 📈 Evaluation Metrics

Given the imbalanced nature of the dataset, the following metrics were prioritized:

- **ROC-AUC**  
  Measures the model’s ability to rank bad customers ahead of good customers  
- **Recall (True Positive Rate)**  
  Measures how many actual bad customers are correctly identified  

Accuracy and F1-score were reported for reference but were not used as primary selection criteria.

---

## 🏆 Model Performance (Test Set)

| Model | ROC-AUC | Recall | Accuracy |
|-----|--------|--------|---------|
| Logistic Regression | ~0.59 | ~0.46 | ~0.62 |
| Random Forest | ~0.73 | ~0.38 | ~0.97 |
| **XGBoost** | **~0.77** | **~0.55** | ~0.87 |

**XGBoost achieved the best overall performance**, demonstrating strong discriminative power and the highest ability to capture high-risk customers.

---

## 📉 ROC Curve

The ROC curve shows that the XGBoost model rises steeply in the low false-positive-rate region, indicating that a significant portion of risky customers can be identified while keeping misclassification of good customers relatively low.

---

## 🔍 Key Takeaways

- ROC-AUC and Recall are more informative than accuracy for credit risk problems
- Tree-based ensemble models significantly outperform linear baselines
- XGBoost provides the strongest ranking ability for identifying high-risk customers
- Threshold tuning can further optimize business-specific trade-offs (future work)

---

## 🚀 Future Improvements

- Threshold optimization based on business cost considerations
- Precision-Recall curve analysis
- Feature importance and model interpretability analysis
- Cost-sensitive evaluation

---

## 📄 License & Copyright

© 2026 Mutian He. All rights reserved.

This project is for educational and demonstration purposes only.
