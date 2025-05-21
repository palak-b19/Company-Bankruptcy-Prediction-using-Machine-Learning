# Company Bankrupcy Prediction
**Course:** [CSE343 / ECE363: Machine Learning](https://techtree.iiitd.edu.in/viewDescription/filename?=ECE363)  
**Instructor:** [Dr. Jainendra Shukla](https://scholar.google.es/citations?user=QCZleNQAAAAJ&hl=en)  
**Institution:** IIIT-Delhi  
**Semester:** Monsoon 2024  
**Dataset:** [Company Bankruptcy Prediction Dataset – Taiwan Economic Journal](https://www.kaggle.com/datasets/fedesoriano/company-bankruptcy-prediction)

---

## Project Overview

This project explores the application of machine learning models to predict the financial sustainability of enterprises. Given a high-dimensional dataset with 96 financial indicators from Taiwanese firms (1999–2009), we built a classification framework to predict whether a company is at risk of bankruptcy. Our motivation stems from the need for early financial distress warning systems that aid policymakers, investors, and stakeholders in mitigating risks.

---

## Objectives

- Analyze financial health indicators to predict bankruptcy risks.
- Handle real-world challenges such as class imbalance and multicollinearity.
- Evaluate and compare multiple ML models including ensemble and deep learning methods.
- Identify key financial features through statistical feature selection techniques.

---

## Dataset Description

- **Source:** Taiwan Economic Journal (1999–2009)
- **Size:** 6819 records, 96 features
- **Target Variable:** `Bankrupt?` (binary classification: 0 or 1)
- **Feature Types:** Financial ratios (e.g., ROA, Asset Growth, Revenue/Share)
- [Kaggle Dataset](https://www.kaggle.com/datasets/fedesoriano/company-bankruptcy-prediction)

---

## Methodology

### Exploratory Data Analysis (EDA)
- Detected severe class imbalance (only ~100 bankrupt firms)
- Identified multicollinearity via correlation matrix
- Outlier detection in critical financial features

### Data Preprocessing
- Class imbalance handled using:  
  `RandomOverSampler`, `RandomUnderSampler`, `SMOTE`, `ADASYN`, `CondensedNearestNeighbor`, and `Tomek Links`
- Multicollinearity resolved using correlation-based feature pruning
- Feature selection via `ANOVA` (numerical) and `Chi-square` (categorical)

---

## Models Implemented

| Model                | Highlights |
|---------------------|-----------|
| **Logistic Regression** | Baseline linear model |
| **Random Forest**        | Robust ensemble method with good generalization |
| **Naive Bayes**          | Probabilistic model assuming independence |
| **SVM (Linear, RBF, Poly)** | Effective in high-dimensional space |
| **MLP Classifier**       | Feed-forward neural network for non-linearity |
| **Custom ANN**           | Custom deep learning implementation |
| **XGBoost**              | Gradient boosting decision trees for accuracy & speed |

---

## Results (Test Set Highlights)

| Model             | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|------------------|----------|-----------|--------|----------|---------|
| Logistic Regression | 80.5%  | 0.49      | **0.88** | 0.63     | 0.88    |
| Random Forest       | 89.4%  | 0.74      | 0.67   | **0.70** | **0.91** |
| XGBoost             | **88.5%** | **0.69** | **0.69** | **0.69** | 0.91    |
| MLP Classifier      | **85.4%** | 0.64     | 0.50   | 0.56     | 0.89    |

> **Note:** Due to the critical nature of predicting bankruptcies, recall was prioritized over precision.

---

## Key Takeaways

- High recall models (SVMs, Logistic Regression) are crucial for real-world bankruptcy risk minimization.
- Feature selection significantly improved performance and interpretability.
- Sampling strategies (especially CondensedNearestNeighbor) helped handle severe class imbalance.
- XGBoost and Random Forest provided the best trade-off between performance and generalization.

---

## References

- Barboza et al., *Machine learning models and bankruptcy prediction*, ESWA, 2017  
- Nanxi Wang, *Bankruptcy Prediction Using ML*, JMF, 2017  
- Danilov, *Corporate Bankruptcy: Assessment & Prediction*, MIT Sloan  
- [Kaggle Dataset](https://www.kaggle.com/datasets/fedesoriano/company-bankruptcy-prediction)


