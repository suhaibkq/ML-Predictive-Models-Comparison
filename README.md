# 🧠 EasyVisa ML Predictive Modeling Project

## 📌 Overview

This project focuses on building a robust machine learning solution for **EasyVisa**, a visa services provider, to predict the outcome of U.S. visa applications (Certified or Denied). The model aims to optimize client screening, improve operational decision-making, and drive business insights.

---

## 🎯 Objective

To develop a predictive model using advanced machine learning techniques that:

- Classifies visa applications as **Certified** or **Denied**
- Identifies the most influential factors affecting certification
- Assists EasyVisa in prioritizing strong applications

---

## 📊 Data Summary

- **Source**: Internal records from EasyVisa  
- **Size**: 25,480 visa applications  
- **Target Variable**: `case_status` (Certified = 1, Denied = 0)  
- **Features**: Education level, job experience, wage, employer size, employment region, full-time status, continent of origin, etc.

---

## 🔧 Methodology

### 🧹 Data Preprocessing

- No missing or duplicate values
- Fixed negative values and standardized wage units
- Handled outliers through capping or log transformation
- Feature engineering: One-hot encoding, binary flags, company age derivation

### ⚖️ Class Imbalance Handling

- **Oversampling**: SMOTE  
- **Undersampling**: RandomUnderSampler

### 🧠 Model Building

- Algorithms Used:
  - Decision Tree
  - Random Forest
  - Bagging Classifier
  - AdaBoost
  - Gradient Boosting (GBM)
  - XGBoost
- Evaluation Metrics: Accuracy, Recall, Precision, F1 Score, ROC AUC
- Cross-validation: Stratified K-Fold

### 🔍 Hyperparameter Tuning

Used `RandomizedSearchCV` to optimize:
- `n_estimators`, `learning_rate`, `max_depth`, `min_samples_leaf`, etc.

---

## 🏆 Final Model: Gradient Boosting (GBM)

### ✅ Validation Performance

| Metric     | Score   |
|------------|---------|
| Recall     | 0.8104  |
| F1 Score   | 0.7968  |
| Precision  | 0.7836  |
| Accuracy   | 0.7239  |
| ROC AUC    | 0.7239  |

**Why GBM?**

- Balanced performance across all metrics  
- Excellent generalization  
- High interpretability

---

## 🔍 Key Insights

- 🎓 **Education**: Higher degrees (Master's, Doctorate) improve approval odds
- 👨‍💼 **Experience**: Prior job experience is a strong predictor
- 🌍 **Geography**: South & Midwest regions yield better certification rates
- 💵 **Wage**: Higher and yearly wages are linked to approval
- 🧾 **Full-Time Status**: Full-time jobs are more likely to be approved

---

## 🚀 Business Recommendations

- Implement a **pre-screening tool** using GBM to flag high-risk applications
- Educate clients about factors that influence approval
- Focus resources on candidates with high approval likelihood
- Deploy a **visa risk dashboard** for internal triage
- **Retrain model periodically** to adapt to policy changes

---

## 📈 Future Enhancements

- Include job titles, industry, employer history, and application types
- Use application-level metadata (e.g., service center, benefits)
- Develop a dynamic **risk scoring system** to prioritize cases

---

## 🗂️ Project Structure

