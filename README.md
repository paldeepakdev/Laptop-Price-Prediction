# Project Summary

## Overview

This project involves predicting laptop prices based on various features. The dataset includes attributes like company, type, RAM, and more. Several regression models were applied to forecast the price, and their performance was compared.

## Data Preparation

1. **Data Transformation:**
   - Applied log transformation to the target variable (`Price`) to stabilize variance and normalize the distribution.
   - The transformed target variable `y` is `np.log(df['Price'])`.

2. **Feature Encoding:**
   - Categorical variables were encoded using one-hot encoding:
     - `Company`
     - `TypeName`
     - `Cpu brand`
     - `Gpu brand`
     - `os`
   - Dropped the first category in each categorical variable to avoid multicollinearity.

3. **Feature Correlation:**
   - Correlation analysis showed significant relationships between features and `Price`. For instance, `SSD` showed a strong positive correlation with `Price`.

## Model Training and Evaluation

1. **Linear Regression:**
   - Model performed with an R² score of 0.807 and MAE of 0.210.

2. **Ridge Regression:**
   - Applied Ridge regression with `alpha=10`.
   - Achieved an R² score of 0.813 and MAE of 0.209.

3. **Lasso Regression:**
   - Used Lasso regression with `alpha=0.001`.
   - Obtained an R² score of 0.807 and MAE of 0.211.

4. **Decision Tree Regressor:**
   - Set `max_depth=8`.
   - Delivered the best R² score of 0.847 and MAE of 0.181.

5. **Random Forest Regressor:**
   - Configured with `n_estimators=100`, `max_samples=0.5`, `max_features=0.75`, and `max_depth=15`.
   - Provided an R² score of 0.887 and MAE of 0.159, the best among the models.

6. **Gradient Boosting Regressor:**
   - Configured with `n_estimators=500`.
   - Provided an R² score of 0.882 and MAE of 0.159.

7. **XGBoost Regressor:**
   - Used `n_estimators=45`, `max_depth=5`, and `learning_rate=0.5`.
   - Achieved an R² score of 0.881 and MAE of 0.165.

## Model Export

- The final trained model and dataset were saved using `pickle` for future use:
  - `df` was saved as `df.pkl`.
  - The trained pipeline was saved as `pipe.pkl`.

## Notes

- The results indicate that Random Forest Regressor provides the best performance in predicting laptop prices.
- Future work could involve tuning hyperparameters further or exploring additional features to improve model accuracy.
