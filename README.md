# Anomaly Detection in Financial Transactions

## 📌 **Project Overview**

This project applies multiple anomaly detection models to detect fraudulent or anomalous financial transactions:

* **Minimum Covariance Determinant (MCD)**
* **Isolation Forest (IF)**
* **One-Class SVM (OCSVM)**
* **Local Outlier Factor (LOF)**

An **ensemble voting mechanism** is implemented to combine model outputs for robust detection.

Additionally, explainability methods such as **SHAP values** and **Decision Trees** are used to interpret how features contribute to anomaly classification, ensuring both accuracy and interpretability.

## 📂 **Dataset**

* **Source**: Kaggle — Financial transaction dataset.
* **Features**: Transactional, customer, and device-related attributes (e.g., `TransactionAmount`, `AccountBalance`, `LoginAttempts`).
* **Target**: Ensemble anomaly labels (0 = Normal, 1 = Anomaly).

## ⚙️ **Methodology**

### Exploratory Data Analysis (EDA)

* Univariate Analysis (Categorical Features)
* Bivariate Analysis (Numeric vs Categorical)
* Temporal Analysis
* Correlation & Relationships

### Feature Engineering

* Normalized and scaled numerical features.
* Applied Principal Component Analysis (PCA) to reduce dimensionality while retaining variance.
* Applied dimensionality reduction (t-SNE) for visualization of anomalies.

### Anomaly Detection Models

1. **Minimum Covariance Determinant (MCD)** — models multivariate distribution.
2. **Isolation Forest (IF)** — isolates anomalies through recursive partitioning.
3. **One-Class SVM (OCSVM)** — finds the hyperplane separating normal vs anomalies.
4. **Local Outlier Factor (LOF)** — measures local density deviation.

### Ensemble Voting

* Each model produces an anomaly label (0 or 1).
* Ensemble anomaly label is the **majority vote** across all models.

### Explainability

* **SHAP values** (via XGBoost surrogate model): Measures feature importance driving anomalies.
* **Decision Tree**: Provides **human-readable rules** for anomaly identification.

## 🛠️ **Model Architecture**

* **Base Anomaly Models**: MCD, IF, OCSVM, LOF (unsupervised anomaly scores).
* **Ensemble Mechanism**: Voting strategy across individual model predictions.
* **Surrogate Classifier**: XGBoost trained on ensemble outputs to generate SHAP explanations.
* **Decision Tree**: Extracted interpretable rules for anomaly classification.

---

## 🖼️ **Visualizations**

* **t-SNE Scatterplots**: Anomalies highlighted in red, normal points in blue.
<div align="left">
  <img src="https://github.com/amsyarzulkifly/bank-fraud-detection/raw/main/attachment/ensemble%20anomaly%20detection%20visual.png" alt="Plot" width="600" height="450"/>
  <p><em>t-SNE visualization of anomalies vs normal transactions using ensemble anomaly detection.</em></p>
</div>  

* **SHAP Plot**: Beeswarm visualizations showing top features influencing anomalies.
<div align="left">
  <img src="https://github.com/amsyarzulkifly/bank-fraud-detection/raw/main/attachment/shap%20beeswarm.png" alt="SHAP Beeswarm" width="600" height="450"/>
  <p><em>SHAP beeswarm plot showing the overall impact of each feature on anomaly classification.</em></p>
</div>

* **Decision Tree for Anomaly Classification**: Hierarchical rules for anomaly classification.
<div align="left">
  <img src="https://github.com/amsyarzulkifly/bank-fraud-detection/raw/main/attachment/decision%20tree%20for%20anomaly%20classification.png" alt="Decision Tree" width="600" height="450"/>
  <p><em>Decision Tree visualization used to classify anomalies vs. normal transactions.</em></p>
</div>

---

## 🚀 **Conclusion**

* Ensemble anomaly detection improves robustness over single models.
* SHAP values highlight which features contribute most to anomalies (e.g., unusually high `TransactionAmount` or excessive `LoginAttempts`).
* Decision Trees provide interpretable rules, bridging the gap between **black-box anomaly detection** and **human understanding**.
* This project demonstrates the importance of combining **unsupervised models with explainability tools** for financial anomaly detection.

## 📌 **Tools Used**

* **Python**
* **scikit-learn**
* **XGBoost**
* **SHAP**
* **Matplotlib & Seaborn**
* **Pandas & NumPy**
