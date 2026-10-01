# Spaceship Titanic – Tuned XGBoost

Kaggle Getting Started competition: predict which passengers were
transported to an alternate dimension.

## Results
- Kaggle public score: 0.80243
- Validation accuracy: 0.8097 (early-stopped XGBoost)
- Train/validation gap reduced from 0.056 (tuned) to 0.042

## Pipeline
1. Cleaning: imputation (CryoSleep passengers have zero spend; median and mode for the rest)
2. EDA: target balance (about 50/50) and feature distributions
3. Winsorization of spending and age at the 1st and 99th percentiles, fit on train only
4. Feature engineering: total, luxury and non-luxury spend, zero-spender flag,
   group size, cabin deck/number/side, age group, route
5. Leak-safe rank encoding of categorical features
6. Multicollinearity checks (correlation heatmap and VIF)
7. Models compared: Logistic Regression (0.788), Lasso (0.788),
   XGBoost (0.806), tuned XGBoost (0.807), early-stopped XGBoost (0.810)
8. Overfitting reduction: stronger regularization and early stopping

## Tools
Python, pandas, NumPy, scikit-learn, XGBoost, statsmodels, matplotlib, seaborn

## Data
Not included. Download from
https://www.kaggle.com/competitions/spaceship-titanic/data
and place train.csv and test.csv next to the notebook.

## Author
Aarthi Murugan
