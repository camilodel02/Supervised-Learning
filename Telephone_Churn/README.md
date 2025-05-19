# Churn Prediction and Retention Intelligence Framework

## Overview
This project implements an end-to-end predictive modeling pipeline to forecast customer churn for a telecommunications provider and design actionable retention strategies. Following the CRISP-DM methodology, we progress through:

1. **Business Understanding**: Define objectives—reduce churn by identifying at-risk customers and applying targeted interventions :contentReference[oaicite:0]{index=0}.  
2. **Data Understanding**: Analyze a customer dataset (8,243 records, 12 features) covering demographics, usage, and billing :contentReference[oaicite:1]{index=1}.  
3. **Data Preparation**: Clean data, transform dates into age and tenure, apply one-hot encoding, and scale inputs :contentReference[oaicite:2]{index=2}.  
4. **Modeling & Evaluation**: Train and compare Logistic Regression (with GridSearchCV) and SVM; address class imbalance via Random Oversampling; evaluate using Accuracy, ROC AUC, and AUC :contentReference[oaicite:3]{index=3}.  
5. **Deployment & Retention Strategies**: Deploy proactive retention campaigns, smart bundles, and dynamic promotions driven by churn scores :contentReference[oaicite:4]{index=4}.  

## Data
- **Records**: 8,243 customers  
- **Features**:  
  - **Categorical**: gender (male/female/enterprise), online billing, premium data plan  
  - **Numerical**: total billing, overdue days, total minutes, age, contract tenure (months), device tenure (months)  
  - **Target**: churn flag (1 = churn, 0 = no churn) :contentReference[oaicite:5]{index=5}  

## Preprocessing Steps
- Convert birth date and contract start date into `Age` and `ContractTenure` variables :contentReference[oaicite:6]{index=6}.  
- One-hot encode categorical variables and cast to `int8`.  
- Remove identifier and original date columns.  

## Modeling & Evaluation
- **Algorithms**:  
  - Logistic Regression (GridSearchCV to tune `C`, `penalty`, `solver`)  
  - Support Vector Machine (default parameters)  
- **Imbalance Handling**: Compared Random Oversampling, Undersampling, SMOTETomek; chose Random Oversampling.  
- **Pipeline**:  
  1. Split data 70/30  
  2. Scale features with `StandardScaler`  
  3. Fit models on training data  
  4. Predict on test set  
  5. Compute Accuracy, ROC AUC, AUC
###Results Comparison:
[preview](logR.png)
- **Best Model**: SVM (Accuracy: 0.7549, AUC: 0.82) :contentReference[oaicite:7]{index=7}.  

## Deployment & Retention Strategies
1. **Proactive Retention Program**: Automatically trigger VIP support and personalized offers for high-risk customers.  
2. **Smart Bundles**: Recommend modular service packages based on individual usage profiles.  
3. **Dynamic Pricing Promotions**: Generate real-time, behavior-driven offers to incentivize retention :contentReference[oaicite:8]{index=8}.  

## How to Run
1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/churn-retention.git
   cd churn-retention
