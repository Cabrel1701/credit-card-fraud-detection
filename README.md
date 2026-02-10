# Credit Card Fraud Detection

## Project Overview

This project aims to build a machine learning model capable of detecting fraudulent credit card transactions in a highly imbalanced dataset.
The objective is to compare different strategies for handling class imbalance and identify the best trade-off between fraud detection performance and false positive rate.

---

## Business Context

Credit card fraud detection is a critical task in the financial industry:

* Fraudulent transactions are *rare but costly*
* Missing fraud cases leads to financial losses
* Excessive false alerts negatively impact customer experience

The main challenge is therefore to find the *right balance between recall and precision*.

---

## Dataset

The dataset contains anonymized credit card transactions.

### Characteristics

* Highly imbalanced dataset
* Fraudulent transactions represent ~0.2% of all observations
* Most variables (V1–V28) are PCA-transformed features
* Includes transaction amount and time information

### Target

* Class = 0 → Normal transaction
* Class = 1 → Fraudulent transaction

---

## Exploratory Data Analysis (EDA)

Key findings:

* Strong class imbalance
* Skewed distribution of transaction amounts
* Presence of outliers
* Clustered transaction behaviors
* Overlap between fraudulent and normal transactions

A PCA projection showed that fraud cases are dispersed and sometimes mixed with normal transactions, making the classification task challenging.

---

## Data Preprocessing & Feature Engineering

Main transformations:

* Log transformation of the Amount variable
* Creation of temporal features:

  * Hour
  * Is_Night
* Behavioral feature:

  * Mean_amount_hour
* Removal of redundant or non-informative variables
* Final dataset contains only relevant numerical features
* No missing values

---

## Handling Class Imbalance

Several techniques were evaluated:

### Baseline (No Resampling)

* High precision
* Moderate recall

### Class Weight Adjustment

* Strong increase in recall
* Significant increase in false positives

### Tomek Links (Boundary Cleaning)

* Minimal impact (dataset already clean)

### Random Oversampling

* Higher recall
* Lower precision

### SMOTE and Tomek + SMOTE

* High fraud detection
* Large number of false alerts

---

## Model Used

*Logistic Regression*

Chosen because:

* Interpretable
* Robust baseline for classification
* Common in fraud detection systems

---

## Results Summary

| Method              | Recall    | Precision | PR-AUC         | Observation              |
| ------------------- | --------- | --------- | -------------- | ------------------------ |
| Baseline            | Medium    | High      | Best           | Best overall balance     |
| Class Weight        | Very High | Very Low  | Slight drop    | Too many false positives |
| Tomek Links         | No change | No change | No change      | Dataset already clean    |
| Random Oversampling | Very High | Very Low  | Similar        | Over-sensitive model     |
| Tomek + SMOTE       | Very High | Very Low  | Slightly lower | No added benefit         |

---

## Key Insights

* Class imbalance does not necessarily mean poor performance
* PCA features are highly discriminative
* Resampling mainly shifts the decision boundary
* Cleaning methods are only useful when significant noise exists
* Model selection depends on business trade-offs

---

## Final Model Choice

The baseline Logistic Regression model provides:

* Best precision
* Highest PR-AUC
* Acceptable fraud detection rate
* Lowest number of false alerts

It represents the most stable solution for a realistic operational context.

---

## Possible Improvements

* Decision threshold optimization
* Advanced models (Random Forest, XGBoost)
* Cost-sensitive learning
* Anomaly detection approaches
* Real-time deployment pipeline

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Imbalanced-learn
* Seaborn & Matplotlib
* Jupyter Notebook

---

## Project Structure


credit-card-fraud-detection/
│
├── Credit_Card_Fraud_Detection_Final.ipynb
├── README.md
├── .gitignore
└── figures/


---

## Author

Cabrel

---

## Conclusion

Fraud detection is a complex and highly imbalanced classification problem.
This project demonstrates that improving recall often increases false positives, requiring a careful balance between statistical performance and operational constraints.