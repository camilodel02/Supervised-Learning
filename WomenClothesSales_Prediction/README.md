# Linear Regression Modeling Framework

## Overview
This project implements a modular framework to compare different linear regression techniques on a real-world dataset. We follow a clear pipeline:

1. **Data Loading**: import training, test, and solution sets.
2. **Exploratory Data Analysis (EDA)**: inspect distributions, correlations, and key patterns.
3. **Data Preprocessing**: clean missing values, engineer features, and scale inputs.
4. **Modeling**: train and evaluate multiple regression models including:
   - **Ordinary Least Squares (OLS) Linear Regression**
   - **Ridge Regression** (L2 regularization)
   - **Lasso Regression** (L1 regularization)
   - **Elastic Net** (combined L1/L2)
5. **Evaluation**: compare models using MSE, MAE, RMSE, and R² scores on hold-out test data.
6. **Model Selection & Export**: select the best-performing model (Ridge) and save final predictions.

## Data
- **Training set**: features `paginas, telefono, servicio, edadloc` (and variations tested)
- **Test set**: same features, with corresponding `idloc` to identify predictions
- **Solution set**: ground-truth `ropamujer` values for evaluation metrics

## Preprocessing Steps
- **Feature Selection**: multiple feature subsets were trialed to optimize baseline performance.
- **Scaling**: applied `StandardScaler` to ensure zero mean and unit variance on all models.

## Modeling Framework
Each model was integrated in the same workflow to ensure fair comparison:

1. **Fit** on `X_train` / `y_train` after scaling.
2. **Predict** on `X_test`.
3. **Compute** evaluation metrics:
   - Mean Squared Error (MSE)
   - Mean Absolute Error (MAE)
   - Root Mean Squared Error (RMSE)
   - Coefficient of Determination (R²)

### Hyperparameter Settings
- **Linear Regression**: default scikit-learn settings.
- **Ridge**: `alpha=1e6`, `max_iter=100`
- **Lasso**: `alpha=1000`
- **Elastic Net**: `alpha=100`, `l1_ratio=0.4`

## Results
Below is a summary of test-set performance for each model (example values):

| Model                 | MSE           | MAE        | RMSE       | R²         |
|-----------------------|---------------|------------|------------|------------|
| OLS LinearRegression  | 436017342.49  | 16771.99   | 20881.03   | -0.39      |
| Ridge (α=1e6)         | 312485522.71  | 14292.11   | 17677.26   | 9.94e-06   |
| Lasso (α=1000)        | 406714683.04  | 16208.88   | 20167.17   | -0.30      |
| Elastic Net (α=100, ρ=0.4) | 312498215.25 | 14289.29 | 17677.62 | -3.07e-05  |

Ridge Regression achieved the lowest MSE and highest R², and was chosen to generate final predictions.

## Final Output
- **predicciones_ropamujer.csv**: contains columns `idloc` and `ropamujer` (Ridge predictions).

## How to Run
1. Install requirements: `pip install -r requirements.txt`.
2. Launch Jupyter or Colab: `jupyter notebook ColabNotebook.ipynb`.
3. Execute cells in order; final CSV will be saved in the working directory.

## Dependencies
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

---
*This README summarizes the end-to-end framework used to train, compare, and select linear regression models. Adapt hyperparameters and feature sets as needed for new datasets.*
# References
[Kaggle Contest 2025 - 1: Machine Learning Principles: Regression](https://www.kaggle.com/competitions/principios-de-machine-learning-regresion-2501/overview)

