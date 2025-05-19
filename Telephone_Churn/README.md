# Churn Prediction and Retention Intelligence Framework

## Overview
This project implements an end-to-end predictive modeling pipeline to forecast customer churn for a telecommunications provider and design actionable retention strategies. Following the CRISP-DM methodology, we progress through:

1. **Business Understanding**: Define objectives—reduce churn by identifying at-risk customers and applying targeted interventions.  
2. **Data Understanding**: Analyze a customer dataset (8,243 records, 12 features) covering demographics, usage, and billing.  
3. **Data Preparation**: Clean data, transform dates into age and tenure, apply one-hot encoding, and scale inputs.  
4. **Modeling & Evaluation**: Train and compare Logistic Regression (with GridSearchCV) and SVM; address class imbalance via Random Oversampling; evaluate using Accuracy, ROC AUC, and AUC.  
5. **Deployment & Retention Strategies**: Deploy proactive retention campaigns, smart bundles, and dynamic promotions driven by churn scores.  

## Data
- **Records**: 8,243 customers  
- **Features**:  
  - **Categorical**: gender (male/female/enterprise), online billing, premium data plan  
  - **Numerical**: total billing, overdue days, total minutes, age, contract tenure (months), device tenure (months)  
  - **Target**: churn flag (1 = churn, 0 = no churn).  

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
## Results Comparison:
| ![SVM](https://github.com/camilodel02/Supervised-Learning/blob/main/Telephone_Churn/SVM.jpg) | ![LogR](https://github.com/camilodel02/Supervised-Learning/blob/main/Telephone_Churn/LogR.jpg) |
|:---------------------------:|:---------------------------:|
| SVM ROC curve and AUC score | LogR ROC curve and AUC score |

**Best Model**: SVM (Accuracy: 0.7549, AUC: 0.82).  

## Deployment & Retention Strategies
1. **Proactive Retention Program**: Automatically trigger VIP support and personalized offers for high-risk customers.  
2. **Smart Bundles**: Recommend modular service packages based on individual usage profiles.  
3. **Dynamic Pricing Promotions**: Generate real-time, behavior-driven offers to incentivize retention :contentReference[oaicite:8]{index=8}.  

## How to Run
1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/churn-retention.git
   cd churn-retention
## References: 
[Kaggle Competion 2025-01 Churn](https://www.kaggle.com/competitions/retencion-en-telefonia-movil-2501) 
## Authors:
María Narváez - Camilo Delgado | Pontificia Universidad Javeriana
