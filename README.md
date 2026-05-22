# 🍷 Ordinal Regression with a Tabular Wine Quality Dataset

This project focuses on predicting wine quality using tabular data, developed as part of the Playground Series - Season 3, Episode 5. Since wine quality ratings are ordered categories, the study emphasizes ordinal regression techniques and the optimization of the Quadratic Weighted Kappa metric.

### 🚀 Live Demo
You can explore the prediction model here: https://huggingface.co/spaces/bdaser/Wine

### 📊 Dataset Overview
The dataset consists of physicochemical properties of wine, with 2056 entries in the training set and 1372 entries in the test set.

### 🛠️ Feature Engineering
To improve model accuracy, several domain-specific features were engineered:
* Total Acidity: Calculated as the sum of fixed acidity and volatile acidity.
* Free Sulfur Ratio: The ratio of free sulfur dioxide to total sulfur dioxide.
* Acidity to pH Ratio: The ratio of total_acidity to pH.
* Outlier Handling: An remove_outliers_iqr function was implemented to refine the dataset based on the Interquartile Range.

### 🏆 Model Performance
Various regression models were evaluated based on R_Squared, RMSE, and MAE. Ridge and Linear Regression models demonstrated the most promising initial results.

| Model | R_Squared | RMSE | MAE |
| :--- | :--- | :--- | :--- |
| Ridge | 0.273003 | 0.732873 | 0.579432 |
| Linear | 0.272652 | 0.733050 | 0.579364 |
| Gradient Boosting | 0.255417 | 0.741685 | 0.576949 |
| XGBRegressor | 0.143619 | 0.795420 | 0.617267 |

### 📈 Optimization Strategy
Since the evaluation metric is Quadratic Weighted Kappa, the raw predictions were optimized by finding the best boundaries to map continuous outputs back into discrete quality classes (3 through 8).
