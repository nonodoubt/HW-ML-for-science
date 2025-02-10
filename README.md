# README.md

## Customer Churn Prediction Project

This project focuses on predicting customer churn for a telecommunications company using machine learning techniques. The dataset contains information about customers, including their demographic details, services subscribed to, and tenure with the company. The goal is to build a model that accurately predicts whether a customer will churn (leave the service) or not.

### Key Features of the Project:
- **Dataset Overview**: The dataset includes both numerical and categorical features such as `ClientPeriod`, `MonthlySpending`, `TotalSpent`, `Sex`, `IsSeniorCitizen`, and various service-related flags like `HasPhoneService`, `HasInternetService`, etc. <button class="citation-flag" data-index="1">.
- **Preprocessing**: 
  - Missing values in the `TotalSpent` column were handled by replacing empty strings with `0` and converting the column to a float type.
  - Categorical variables were encoded using one-hot encoding for compatibility with machine learning models.
- **Exploratory Data Analysis (EDA)**:
  - Visualizations such as histograms, boxplots, and pie charts were used to understand the distribution of features and identify patterns.
  - Correlation analysis was performed using both linear (Pearson) and non-linear (PHIK) methods to explore relationships between features and the target variable `Churn`.
- **Modeling**:
  - Several machine learning models were trained and evaluated, including Logistic Regression, Random Forest, and XGBoost.
  - Hyperparameter tuning was conducted using GridSearchCV for Random Forest and Optuna for XGBoost to optimize performance.
  - The evaluation metric used was ROC-AUC, which measures the ability of the model to distinguish between churned and non-churned customers.
- **Results**:
  - The best-performing model was XGBoost, achieving an ROC-AUC score of 0.8246 on the validation set and 0.8475 on the test set when submitted to Kaggle <button class="citation-flag" data-index="2">.
  - Feature importance analysis using permutation importance and SHAP values revealed that factors such as contract type (`HasContractPhone`), payment method (`PaymentMethod`), and tenure (`ClientPeriod`) significantly influence churn predictions.

### File Structure:
- **train.csv**: Training dataset containing labeled data for model training.
- **test.csv**: Test dataset for making predictions.
- **submission.csv**: Final predictions submitted to Kaggle for evaluation.

### Installation and Usage:
To replicate the results or further develop the project, follow these steps:
1. Install required libraries:
   ```bash
   !pip install pandas scikit-learn xgboost optuna matplotlib seaborn phik
