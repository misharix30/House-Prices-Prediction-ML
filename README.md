# House-Prices-Advanced-Regression-Techniques
The goal of this repository is to provide a comprehensive analysis and prediction model for Kaggle's House Prices competition: https://www.kaggle.com/c/house-prices-advanced-regression-techniques

My best score on the Kaggle Leaderboard: 0.11658

Description
1. EDA and Data Tidying:
Target Variable: Analysis of SalePrice distribution (Skewness: ~1.88, Kurtosis: ~6.54).

Transformation: Log transformation applied to SalePrice to handle right-skewness.

Feature Classification: Systematic separation of 36 numerical and 43 categorical features.

Outlier Handling: Identification and removal of extreme outliers to improve model robustness.

2. Feature Engineering & Preprocessing:
Handling Missing Values: * Categorical: Imputing 'None' for facilities not present in the house.

Numerical: Imputing 0 or median where appropriate.

Encoding Strategies:

Ordinal Encoding: Applied to features with natural rankings (Quality/Condition scales).

Target Encoding: Used for the Neighborhood feature to capture location-based price trends.

Feature Scaling: Standardization applied to ensure features are on a comparable scale for linear models.

3. Modelization:
The project utilizes an ensemble approach combining different regression techniques:

Ridge Regression:.

CatBoostRegressor.

GradientBoostingRegressor.

4. Training and Blending:
Weight Optimization: Final predictions are generated using a weighted blend:

0.50 * Ridge + 0.30 * CatBoost + 0.20 * GradientBoosting

Outlier Clipping: Predictions are clipped between the 0.5th and 99.25th percentiles to eliminate extreme prediction errors.

Inverse Transformation: Converting log-scaled predictions back to original currency values using expm1.