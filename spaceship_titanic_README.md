# Spaceship Titanic - Enhanced Solution

This repository contains an enhanced solution for the Kaggle Spaceship Titanic competition, designed to improve upon your current score of 0.79.

## Files Included

1. **spaceship_titanic_enhanced.py** - Standalone Python script with the complete solution
2. **spaceship_titanic_enhanced.ipynb** - Jupyter notebook with detailed explanations and visualizations
3. **feature_importance_enhanced.csv** - Analysis of most important features (generated after running)
4. **submission_enhanced.csv** - Submission file for Kaggle (generated after running)

## Key Improvements Implemented

### 1. Advanced Feature Engineering
- **Group Features**: Extract group size, position, and family indicators from PassengerId
- **Cabin Features**: Decode deck level, cabin region, port/starboard side
- **Name Features**: Identify family members through last names
- **Spending Features**: Create spending ratios, categories, and luxury indicators
- **Interaction Features**: Capture relationships between features (e.g., CryoSleep × Spending)
- **Anomaly Features**: Identify unusual patterns (e.g., CryoSleep passengers with spending)

### 2. Smart Data Imputation
- KNN imputer for numerical features (considers similar passengers)
- Strategic filling for categorical variables
- Group-based imputation for age and spending

### 3. Ensemble Methods
The solution uses a weighted voting ensemble of:
- Random Forest (captures non-linear patterns)
- Extra Trees (additional randomness)
- Gradient Boosting (sequential improvement)
- XGBoost (powerful gradient boosting)
- LightGBM (fast and efficient)
- CatBoost (handles categoricals well)

### 4. Cross-Validation
- 5-fold stratified cross-validation
- Ensures model generalizes well
- Prevents overfitting

## How to Use

### Prerequisites
```bash
pip install pandas numpy scikit-learn xgboost lightgbm catboost matplotlib seaborn
```

### Running the Script
1. Place your `train.csv` and `test.csv` files in the same directory as the script
2. Run the Python script:
```bash
python spaceship_titanic_enhanced.py
```
3. The script will generate `submission_enhanced.csv` for Kaggle submission

### Running the Notebook
1. Open `spaceship_titanic_enhanced.ipynb` in Jupyter
2. Run all cells sequentially
3. The notebook provides detailed explanations and visualizations

## Expected Performance

Based on the implemented techniques, you should see:
- Cross-validation score: ~0.805-0.815
- Kaggle public leaderboard: >0.80

## Critical Insights Exploited

1. **CryoSleep Rule**: Passengers in cryosleep shouldn't have any spending
2. **Group Patterns**: Families/groups tend to have similar outcomes
3. **Cabin Structure**: Different decks have different transportation rates
4. **Age Groups**: Children and elderly have distinct patterns
5. **VIP Correlations**: VIP status correlates with cabin location and spending

## Further Improvements

To push beyond 0.81:

1. **Neural Networks**: Add a deep learning model to the ensemble
2. **Stacking**: Use a meta-learner instead of voting
3. **Feature Engineering**: Create polynomial features for top predictors
4. **Hyperparameter Tuning**: Use Optuna for Bayesian optimization
5. **Pseudo-labeling**: Use confident test predictions as training data

## Troubleshooting

- If you get memory errors, reduce n_estimators in the models
- If CatBoost installation fails, you can comment it out (minimal impact)
- Ensure all required CSV files are in the correct directory

## Competition Link
https://www.kaggle.com/c/spaceship-titanic

Good luck with your improved submission! 