# 💳 Credit Card Fraud Detection

> An end-to-end Machine Learning classification project for detecting fraudulent credit card transactions, with a focus on **imbalanced data, model comparison, and fraud-oriented evaluation metrics**.

---

##  Project Overview

Credit card fraud detection is a **binary classification problem** where the number of legitimate transactions is significantly higher than fraudulent transactions.

This project builds a complete machine learning pipeline to identify fraudulent transactions while focusing on metrics such as **Precision, Recall, F1-Score, and ROC-AUC**, rather than relying only on accuracy.

The project covers the complete workflow from **data exploration and preprocessing to model training, evaluation, and hyperparameter optimization**.

---

##  Problem Statement

Given information about a credit card transaction, predict whether the transaction is:

* `0` → Legitimate
* `1` → Fraudulent

The main objective is to detect as many fraudulent transactions as possible while minimizing false fraud alerts.

---

##  Dataset

The dataset contains transaction-level information including features related to:

* Transaction amount
* Transaction time
* Merchant category
* Foreign transaction indicator
* Location mismatch
* Device trust
* Transaction velocity
* Cardholder information
* Fraud label

### Target Variable

`is_fraud`

---

##  Exploratory Data Analysis

The analysis includes:

* Dataset structure and data types
* Missing-value analysis
* Target distribution
* Fraud vs. legitimate transaction analysis
* Numerical feature distributions
* Categorical feature analysis
* Correlation analysis
* Identification of class imbalance

A major focus of the EDA was understanding why **accuracy alone is not an appropriate metric** for this problem.

---

##  Data Preprocessing

The preprocessing pipeline includes:

* Handling missing values
* Separating numerical and categorical features
* One-Hot Encoding categorical variables
* Train/Test splitting
* Feature preprocessing using Scikit-learn pipelines
* Handling class imbalance

For models supporting class weighting, balanced class weights were explored.

For XGBoost, `scale_pos_weight` was used to account for the imbalance between legitimate and fraudulent transactions.

---

##  Models Implemented

Several classification algorithms were compared:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting
5. AdaBoost
6. XGBoost

This makes the project more than a single-model implementation and allows different model families to be evaluated on the same problem.

---

##  Evaluation Metrics

Because fraud detection is an imbalanced classification problem, the following metrics were used:

| Metric           | Purpose                                                   |
| ---------------- | --------------------------------------------------------- |
| Accuracy         | Overall classification correctness                        |
| Precision        | How many predicted fraud cases were actually fraud        |
| Recall           | How many actual fraud cases were detected                 |
| F1-Score         | Balance between Precision and Recall                      |
| ROC-AUC          | Ability to distinguish fraud from legitimate transactions |
| Confusion Matrix | Detailed classification breakdown                         |

### Why Recall Matters

Missing a fraudulent transaction can be significantly more costly than incorrectly flagging a legitimate transaction.

Therefore, **Recall is an important metric for this problem**, while Precision is also important because excessive false positives can negatively affect legitimate customers.

---

##  Model Performance

### XGBoost — Test Set

| Metric    |      Score |
| --------- | ---------: |
| Accuracy  | **99.95%** |
| Precision | **90.00%** |
| Recall    | **82.65%** |
| F1-Score  | **86.17%** |
| ROC-AUC   | **97.16%** |

XGBoost achieved the strongest overall performance among the evaluated models based on the balance between Precision, Recall and F1-Score.

> **Note:** These results are specific to this dataset and test split and should not be interpreted as production-level fraud detection performance.

---

##  Key Takeaways

* Accuracy can be misleading for highly imbalanced datasets.
* Recall is particularly important when missing positive cases is costly.
* Precision becomes important when false fraud alerts have a business cost.
* Ensemble methods can significantly outperform simpler baseline models on tabular data.
* Model evaluation should be driven by the **business problem**, not simply by the highest accuracy.

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

---

##  Project Structure

```text
Credit Card Fraud Detection/
│
├── analysis.ipynb
├── FraudDetection.ipynb
├── creditcard.csv
└── README.md
```

---

##  How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd "Credit Card Fraud Detection"
```

### 2. Install dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks and run the cells sequentially.

---

##  Resume Highlights

* Developed an end-to-end **credit card fraud detection classification pipeline** addressing severe class imbalance.
* Compared **6 classification algorithms** using Precision, Recall, F1-Score and ROC-AUC.
* Implemented preprocessing pipelines and class-imbalance handling techniques including `class_weight` and XGBoost `scale_pos_weight`.
* Achieved **86.17% F1-Score, 82.65% Recall and 97.16% ROC-AUC** on the held-out test set using XGBoost.

---

##  Author

**Rishu Ranjan Choudhary**

Machine Learning | Deep Learning | NLP

[GitHub]https://github.com/developrishu-cell • [LinkedIn]https://www.linkedin.com/in/rishu-ranjan-choudhary-665150358/
