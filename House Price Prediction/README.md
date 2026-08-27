# 🏠 House Price Prediction

> An end-to-end Machine Learning regression project for predicting residential property prices using **feature engineering, preprocessing pipelines, model comparison, and hyperparameter optimization**.

---

##  Project Overview

House price prediction is a regression problem where the goal is to estimate the selling price of a property based on its characteristics.

This project develops a complete machine learning workflow starting from raw housing data and progressing through:

**EDA → Data Cleaning → Feature Engineering → Preprocessing → Model Comparison → Hyperparameter Tuning → Final Model**

The project uses multiple regression algorithms to understand which approaches perform best on structured/tabular data.

---

##  Problem Statement

Given information about a residential property, predict its expected **Sale Price**.

The model uses information such as:

* Overall house quality
* Living area
* Basement area
* Garage characteristics
* Bathrooms
* Neighborhood
* Lot characteristics
* Construction features
* Exterior features
* Other property attributes

### Target Variable

`SalePrice`

---

##  Dataset

The project uses the **Ames Housing Dataset**, containing detailed information about residential properties and their corresponding sale prices.

The dataset provides a large number of numerical and categorical features, making it a good example of a real-world tabular regression problem.

---

##  Exploratory Data Analysis

The analysis covers:

* Dataset dimensions
* Data types
* Missing-value analysis
* Target distribution
* Numerical feature distributions
* Categorical feature analysis
* Correlation analysis
* Relationship between important features and `SalePrice`

### Important Relationships

The analysis identified strong relationships between sale price and variables such as:

* Overall Quality
* Ground Living Area
* Total Square Footage
* Basement Area
* Garage Capacity
* Neighborhood

The target variable is also **right-skewed**, which is important when selecting appropriate evaluation metrics and transformations.

---

##  Data Cleaning

Missing values were handled based on the meaning of individual features rather than applying one generic strategy.

Examples include:

* Median imputation for numerical variables
* Mode/category-based imputation for categorical variables
* `"NA"` categories where missingness represents the absence of a feature
* Domain-based treatment of property-related missing values

---

##  Feature Engineering

Several domain-informed features were created to provide models with more meaningful representations of the data.

### Engineered Features

* `TotalSF`
* `Total_sqr_footage`
* `TotalBathrooms`
* `TotalPorchSF`
* `GarageAge`

For example, combining multiple floor-area variables into total square footage allows the model to directly capture the overall size of the property.

---

##  Preprocessing Pipeline

The project uses Scikit-learn preprocessing pipelines to ensure that transformations are applied consistently.

Techniques include:

* `ColumnTransformer`
* `OneHotEncoder`
* `OrdinalEncoder`
* `StandardScaler`
* Numerical feature preprocessing
* Categorical feature preprocessing
* `handle_unknown='ignore'`

Using pipelines helps prevent preprocessing inconsistencies between training and prediction data.

---

##  Models Implemented

The following regression algorithms were compared:

### Linear Models

* Linear Regression
* Ridge Regression
* Lasso Regression

### Tree-Based Models

* Decision Tree Regressor
* Random Forest Regressor

### Boosting Models

* AdaBoost Regressor
* Gradient Boosting Regressor
* XGBoost Regressor
* LightGBM Regressor
* CatBoost Regressor

### Instance-Based Model

* K-Neighbors Regressor

In total, **11 regression approaches** were explored.

---

##  Hyperparameter Optimization

Several ensemble models were further optimized using:

`RandomizedSearchCV`

Models tuned include:

* Random Forest
* Gradient Boosting
* XGBoost
* LightGBM
* CatBoost

Hyperparameters such as:

* Number of estimators
* Learning rate
* Tree depth
* Subsampling
* Regularization
* Other model-specific parameters

were explored to improve model performance.

---

##  Evaluation Metrics

The project evaluates regression models using:

| Metric | Purpose                                                 |
| ------ | ------------------------------------------------------- |
| MAE    | Average absolute prediction error                       |
| RMSE   | Penalizes larger errors more strongly                   |
| RMSLE  | Measures relative error and handles skewed targets well |
| R²     | Measures explained variance                             |

RMSLE is particularly useful for this housing problem because it evaluates relative differences and reduces the influence of extremely expensive properties.

---

##  Final Model

The final workflow uses an **XGBoost Regressor combined with the preprocessing pipeline**.

The overall architecture is:

```text
Raw Data
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
ColumnTransformer
   ↓
Encoded / Scaled Features
   ↓
XGBoost Regressor
   ↓
House Price Prediction
```

---

##  Key Takeaways

* Real-world ML performance depends heavily on data preparation.
* Domain-based feature engineering can provide more useful representations to models.
* Different algorithms behave differently on structured/tabular data.
* Ensemble boosting methods are particularly effective for complex nonlinear relationships.
* `Pipeline` and `ColumnTransformer` make ML workflows more reproducible and production-friendly.
* Hyperparameter tuning can improve performance beyond default model configurations.

---

##  Tech Stack

**Languages & Tools**

* Python
* Jupyter Notebook

**Libraries**

* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost
* LightGBM
* CatBoost

---

##  Project Structure

```text
House Price Prediction/
│
├── House_price_analysis.ipynb
├── House_price_model.ipynb
├── train.csv
├── test.csv
├── modified_train.csv
├── submission.csv
├── data_description.txt
└── README.md
```

---

##  How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd "House Price Prediction"
```

### 2. Install dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost lightgbm catboost jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks and run the cells sequentially.

---

##  Resume Highlights

* Built an end-to-end **house price prediction regression pipeline** covering EDA, data cleaning, feature engineering and model evaluation.
* Engineered domain-specific features including **total square footage, total bathrooms, total porch area and garage age**.
* Compared **11 regression algorithms** and optimized ensemble models using `RandomizedSearchCV`.
* Built a reproducible **Scikit-learn preprocessing + XGBoost pipeline** for final house price prediction.

---

##  Author

**Rishu Ranjan Choudhary**

Machine Learning | Deep Learning | NLP

[GitHub]https://github.com/developrishu-cell • [LinkedIn]https://www.linkedin.com/in/rishu-ranjan-choudhary-665150358/
