# Loan Default Prediction – Africa Financial Markets

## 📌 Overview
This project was developed as part of my **first machine learning competition** on [Zindi](https://zindi.africa/competitions/african-credit-scoring-challenge): **African Credit Scoring Challenge**.  

The competition aimed to predict **loan default risk** for customers in African financial markets (Kenya and Ghana). The goal is to build models that generalize well across different countries and economic contexts, helping financial institutions make better lending decisions and reduce risk.  

> **Note:** This was my first competition, and I am still learning. The project reflects my attempt to apply feature engineering, ensemble modeling, and handling imbalanced datasets in a real-world scenario.

---

## 🚀 Approach
- **Models Used**:  
  - CatBoost (20%)  
  - XGBoost (60%)  
  - Ensemble voting/averaging strategy  
- **Dropped**: LightGBM (stability issues during training)  
- **Features Used**:  
  - Loan-level features: amount, repayment, duration, funding ratio  
  - Customer-level aggregated statistics: mean, sum, std, min, max of loan amounts, repayments, durations  
  - Date features: disbursement month, day of week, loan duration  
- **Not Used**: Economic indicators (caused performance degradation due to class imbalance)

---

## ⚖️ Class Imbalance
The dataset was highly imbalanced (majority “No Default” vs minority “Default”).  
Handled via:  
- Class weighting in XGBoost and CatBoost  
- Threshold tuning to maximize F1 score  

---

## 📊 Results
- **Public Leaderboard F1 Score**: `0.7031`  
- **Private Leaderboard F1 Score**: `0.6686`  
- **Rank**: 217 / 900+ participants  

> In simple terms: The model correctly identifies defaults roughly **7 of 10* on public data, which is a strong result for a first competition.

---
