# Machine Learning for Heart Attack Screening  
### Can We Identify Risk Before a Crisis Occurs?

**Author:** Tran (Theresa) Huyen Le  
Master of Science in Analytics – Georgia State University  

---

## 📊 Project Overview

Heart disease remains one of the leading causes of death in the United States.  
Approximately **805,000 Americans experience a heart attack annually** (CDC, 2023).  
Traditional screening methods may fail to capture complex, interacting risk factors.

This project builds an **interpretable machine learning screening prototype** to identify high-risk individuals in a low-prevalence population using survey-based data.

The goal is early detection and preventive insight — not clinical diagnosis.

---

## 📁 Dataset

- Source: Kaggle (U.S. Behavioral Risk Factor Surveillance System survey data)
- Sample Size: 237,630 U.S. adults
- Heart attack prevalence: **5.6%**

### Features include:
- Demographics (Age, Sex, Race)
- Clinical conditions (Diabetes, Kidney Disease, COPD)
- Behavioral risks (Smoking, Alcohol)
- Self-reported health status
- Mobility limitations

---

## ⚠️ Challenges

1. **Severe Class Imbalance**
   - Only 5.6% reported prior heart attack
   - Accuracy alone is misleading

2. **Self-Reported Survey Data**
   - Potential bias
   - Limited direct clinical generalization

3. **Interpretability Requirement**
   - Screening tools must be explainable

---

## 🧠 Methodology

### 1️⃣ Data Processing
- Removed ID and leakage variables
- Encoded categorical features using OneHotEncoder
- Median imputation for numeric features
- Stratified train-test split
- Class-weighted modeling

### 2️⃣ Models Compared
- Logistic Regression (interpretable baseline)
- Random Forest (non-linear benchmark)

### 3️⃣ Evaluation Metrics
- ROC-AUC
- Recall (Sensitivity)
- Precision
- F1 Score
- Confusion Matrix
- Precision-Recall Curve

---

## 🏆 Final Model Selection

**Logistic Regression was selected.**

Why?

- High interpretability (odds ratios)
- Strong discrimination (**ROC-AUC ≈ 0.83**)
- Better recall performance for screening use case

### Threshold Tuning

Default threshold (0.5) → Lowered to **0.35**

- Recall improved from **0.775 → 0.888**
- Prioritized sensitivity over accuracy

Screening must minimize false negatives.

---

## 🔎 Key Insights

Significant risk factors (Odds Ratio > 1):

- Chest-related medical history (~2.3x odds)
- Poor general health (~2.0x odds)
- Kidney disease (~1.5x odds)
- Mobility limitations
- COPD

Comorbidity burden strongly increases risk.

---

## 📈 Model Performance Summary

| Model | ROC-AUC | Strength |
|-------|---------|----------|
| Logistic Regression | ~0.83 | High interpretability + strong recall |
| Random Forest | Comparable AUC | Lower recall under imbalance |

---

## 📌 Key Takeaway

> Heart attack doesn’t only hit “high-risk” patients.  
> It often hits the unprepared.  
> Small risk today can become a crisis tomorrow.

Machine learning can enhance preventive screening by identifying subtle, interacting risk signals in low-prevalence populations.

---

## 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

---

## 🚀 How to Run

1. Clone repository:
