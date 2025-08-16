# Support Vector Machine (SVM) – Retention in Scholastic Travel Company

📌 **Author:** Camilo Delgado Burbano  

## 📖 Project Description
This project implements a Support Vector Machine (SVM) model to predict student retention based on a dataset with 68 features and 2388 records.  
The workflow includes Exploratory Data Analysis (EDA), preprocessing, categorical variable encoding, model training, hyperparameter tuning with GridSearchCV, and performance evaluation.

## 📂 Files
- `SVM_CamiloDelgado.ipynb`: Main notebook with full project development.
- `STC_dataset.csv`: Dataset used.

## 🔄 Workflow
1. **Exploratory Data Analysis (EDA)**
   - Variable inspection and cleaning
   - Handling missing values
   - Boxplots for outlier detection (e.g., FPP vs Retention)

2. **Preprocessing**
   - Data normalization with `StandardScaler`
   - Train-test split

3. **Model Training**
   - Implementation of SVM with linear and radial kernels

4. **Hyperparameter Optimization**
   - GridSearchCV for tuning C and γ parameters
   - Cross-validation for model selection

5. **Evaluation**
   - Confusion matrix
   - Accuracy, Sensitivity, Specificity
   - ROC curve and AUC score

## 📊 Key Results
- Best model: **SVM with GridSearchCV (C=1, γ=0.1, kernel=rbf)**
- Accuracy: **83%**
- ROC AUC: **86%**
- Balanced sensitivity and specificity, reducing false positives.

## 🚀 Insights
- FPP variable showed higher values for retained students.
- GridSearchCV significantly improved performance over default parameters.
- This kind of model could help institutions predict dropout risks.

## ⚡ Personal Note
Through this project, I strengthened my understanding of SVMs, hyperparameter tuning, and the importance of preprocessing categorical data.
