# Customer Churn Classifier

## Overview
This project builds a machine learning classifier to predict customer churn using a telecommunications customer dataset. The analysis includes exploratory data analysis (EDA), feature engineering, and model development with baseline comparisons.

## Dataset
The project uses [data/customer_churn_dataset.csv](data/customer_churn_dataset.csv), found at https://www.kaggle.com/datasets/sonalshinde123/customer-churn-prediction-dataset which contains 
**20,000 customer records** with **11 features**:

### Numerical Features
- **tenure** (1-72 months): Customer relationship duration
  - Mean: 36.47 months
  - Range: 1-72 months
- **monthly_charges** ($20-$120): Monthly service cost
  - Mean: $70.01
  - Range: $20.00-$120.00
- **total_charges** ($20.23-$8,629.92): Cumulative charges
  - Mean: $2,543.98
  - Range: $20.23-$8,629.92
- **support_calls** (0-8): Number of support interactions
  - Mean: 1.51 calls
  - Range: 0-8 calls

### Categorical Features
- **contract**: Contract type (Month-to-month, One year, Two year)
- **payment_method**: Payment option (Credit, Debit, Cash, UPI)
- **internet_service**: Service type (DSL, Fiber, Unknown Service)
- **tech_support**: Whether customer has tech support (Yes/No)
- **online_security**: Whether customer has online security (Yes/No)

### Target Variable
- **churn**: Whether customer churned (Yes/No); Churn rate approximately 34% (Churn refers to customers who have discontinued their service)

## Data Quality

### Missing Values
- Initial dataset had **2,013 missing values** in `internet_service` field (~10% of data)
- Missing values filled with "Unknown Service" rather than dropped to preserve dataset size
- No missing values in final cleaned dataset

## Project Files

| File | Description |
|------|-------------|
| [EDA.ipynb](EDA.ipynb) | Exploratory Data Analysis with visualizations and statistical insights |
| [model.ipynb](model.ipynb) | Model development, training, and evaluation |
| [model_baselines.csv](model_baselines.csv) | Baseline model performance metrics and comparison |
| [requirements.txt](requirements.txt) | Python package dependencies |
| [data/customer_churn_dataset.csv](data/customer_churn_dataset.csv) | Raw customer dataset (20,000 records) |

## Dependencies

Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. **Exploratory Analysis**: Open [EDA.ipynb](EDA.ipynb) to understand data distributions, correlations, and patterns
2. **Model Development**: See [model.ipynb](model.ipynb) for model training, hyperparameter tuning, and evaluation
3. **Compare Baselines**: Review [model_baselines.csv](model_baselines.csv) for performance comparison across different models

## Model Training

- **Primary Model**: XGBoost classifier for best accuracy of ~84.975%
- **Other Models**: HistGradientBoosting, AdaBoostClassifier, GradientBoostingClassifier, RandomForestClassifier, BaggingClassifier, LightGBM, CatBoost TensorFlow sequential model
- **Hyperparameter Tuning**: Optuna used for hyperparameter optimization across models

## Version

- **Python**: 3.11.9