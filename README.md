# Epidemic Duration Prediction (Flask + Machine Learning)

## Overview
This project is a **Flask-based web application** that analyzes COVID-19 data and uses machine learning to predict the **duration of an epidemic**.  
It demonstrates the full workflow from **data collection → cleaning → feature engineering → model training → deployment as a web app**.  

The project highlights how data science and ML can support **public health planning, pharmaceutical research, and insurance risk assessment**.

---

## Features
- Data collection and preprocessing  
- Exploratory data analysis (EDA) and visualization  
- Machine learning models (Random Forest, Gradient Boosting, KMeans)  
- Feature importance analysis with SHAP  
- Flask web app for data interaction and prediction  

---

## Dataset
The dataset includes COVID-19 statistics from multiple countries:  
- **Country** – Country name  
- **first_seq / last_seq** – First and last sequence dates  
- **variant** – Variant type  
- **num_seqs** – Number of sequences  
- **censure_date** – Censure date  
- **duration** – Epidemic duration  
- **censored** – Indicator for censored data  
- **mortality_rate** – Mortality rate  
- **total_cases / total_deaths** – Case and death counts  
- **growth_rate** – Case growth rate  

---

## Technologies Used
- **Flask** – Web application framework  
- **Python**: Pandas, NumPy, SciPy  
- **Visualization**: Matplotlib, Seaborn, GeoPandas  
- **Machine Learning**: Scikit-learn (RandomForestRegressor, GradientBoostingRegressor, KMeans)  
- **Model Interpretation**: SHAP  
- **Model Persistence**: Joblib  

---

## Data Processing
- **Cleaning**: handled missing values with forward fill, removed duplicates  
- **Feature Engineering**:  
  - `mortality_case_ratio = total_deaths / (total_cases + 1)`  
  - Log transformation of `total_cases` and `total_deaths`  
  - Selected features: `num_seqs, mortality_case_ratio, total_cases, total_deaths, growth_rate, censored`  

---

## Model Training & Evaluation
1. Split dataset into training/testing sets  
2. Scaled features with `StandardScaler`  
3. Trained a **Random Forest Regressor**  
4. Evaluated model performance:  

```bash
MAE: 12.5
RMSE: 18.2
R2 Score: 0.87
