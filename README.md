# **Kaggle - House Prices Advanced Regression (Top Rank: 177)**

This repository contains my complete, high-performing solution for the [House Prices: Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques) competition on Kaggle. The goal was to predict the final sale price of residential homes in Ames, Iowa.

This notebook implements a robust pipeline for data cleaning, feature engineering, and modeling, which achieved a final rank of **177** on the private leaderboard.

## **Methodology & Key Features**

The success of this project comes from a systematic and detailed approach to data preparation and modeling.

### 1. **Comprehensive Data Cleaning & Imputation**
* Methodically handled missing values by analyzing the contextual meaning of `NaN` for over 30 features. For example, `NaN` in `PoolQC` was correctly imputed as "None," while numerical features were filled with appropriate defaults like 0 or the mode.
* Corrected erroneous data points, such as an outlier in the `GarageYrBlt` feature.

### 2. **Intelligent Feature Engineering**
* **Time-Based Features:** Converted year-based columns (`YearBuilt`, `YearRemodAdd`, `GarageYrBlt`) into "age" features relative to the year of sale, making them more intuitive for the model.
* **Consolidated Features:** Combined multiple features into more powerful ones, such as `TotalBaths` (sum of all bathrooms) and `TotalFlrSF` (total square footage of all floors).
* **Ratio Features:** Created meaningful ratios like `GarageAreaPerCar` to capture more nuanced information.

### 3. **Advanced Preprocessing**
* **Handling Skewness:** Identified and corrected for highly skewed numerical features using a `log1p` transformation. This is a critical step for improving the performance of many regression models.
* **Sophisticated Categorical Encoding:** Differentiated between ordinal and nominal features.
    * **Ordinal features** (e.g., `ExterQual`, `BsmtQual`) were manually mapped to preserve their inherent order.
    * **Nominal features** were one-hot encoded to create a machine-readable format without implying a false order.

### 4. **Modeling and Hyperparameter Tuning**
* The final models were built using powerful gradient boosting libraries: **XGBoost** and **CatBoost**.
* **Optuna**, an automated hyperparameter optimization framework, was used to systematically search for the best-performing parameters for each model. This was a crucial step in maximizing the predictive accuracy and achieving a high rank.

## **Tools and Libraries**
* **Data Manipulation:** `Pandas`, `NumPy`
* **Data Visualization:** `Seaborn`, `Matplotlib`
* **Machine Learning:** `Scikit-learn`, `XGBoost`, `CatBoost`
* **Hyperparameter Optimization:** `Optuna`
