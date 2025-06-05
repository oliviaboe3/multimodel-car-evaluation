# Car Evaluation Classification Project

This project explores and compares multiple classification models to predict car evaluation categories using the UCI Car Evaluation Dataset. The goal is to predict the final evaluation of cars—`unacceptable`, `acceptable`, `good`, or `very good`—based on six car characteristics.

---

## 📂 Dataset Overview

- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Car+Evaluation)
- **Instances**: 1,728
- **Features**:
  - Buying Price
  - Maintenance Cost
  - Number of Doors
  - Capacity in Persons
  - Luggage Boot Size
  - Safety Level
- **Target Variable**: Car Evaluation (`unacc`, `acc`, `good`, `vgood`)

---

## ⚙️ Project Goals

1. Apply and compare multiple classification techniques:
   - Decision Tree
   - k-Nearest Neighbors (k-NN)
   - Logistic Regression
   - Naive Bayes
   - Support Vector Machine (SVM)

2. Tune parameters and evaluate model performance using:
   - Accuracy
   - Precision, Recall, F1 Score
   - Matthews Correlation Coefficient (MCC)
   - Confusion Matrix analysis

3. Compare modeling results based on:
   - Binary vs Ordinal encoding of input features
   - Class imbalance
   - Per-class performance

---

## 🔎 Methodology

- **Data Preprocessing**:
  - Binary inputs: one-hot encoded
  - Ordinal inputs: label-mapped with increasing numeric scales
  - SMOTE applied for imbalanced target distributions

- **Model Training**:
  - Cross-validation used for hyperparameter tuning (e.g., GridSearchCV)
  - Main scoring metric: **MCC** (to balance class performance)

- **Final Evaluation**:
  - Best-performing model selected based on MCC and F1
  - Confusion matrices plotted to visualize prediction performance

---

## 🏆 Results Summary

| Model               | Encoding Type | Accuracy | F1 Score | MCC Score |
|--------------------|----------------|----------|----------|-----------|
| SVM (Best)          | Binary         | 0.987    | 0.994    | 0.987     |
| SVM                 | Ordinal        | 0.968    | 0.986    | 0.968     |
| Logistic Regression | Ordinal        | ...      | ...      | ...       |
| Decision Tree       | Binary         | ...      | ...      | ...       |
| k-NN                | Ordinal        | ...      | ...      | ...       |

- The SVM with binary-encoded features achieved the best performance overall.
- Ordinal models performed well, but slightly below the binary approach.
- MCC was used to ensure fair evaluation across all target classes.

---

## 📌 Key Insights

- **Binary encoding + SVM** yielded the most balanced and accurate predictions.
- **Ordinal encoding** is interpretable but may skew scale-sensitive models.
- MCC was essential in evaluating models on imbalanced multi-class outputs.
- Some models (e.g., Naive Bayes) were less effective due to data distribution.

---

## 📁 Files

- `Car_Predictions.ipynb`: Full modeling workflow (data prep, training, evaluation)
- `requirements.txt`: List of Python dependencies (scikit-learn, imbalanced-learn, pandas, numpy, matplotlib)
- `car.data`: Raw dataset (if included)

---

## 🧠 Next Steps

- Explore ensemble methods (e.g., Random Forest, Gradient Boosting)
- Try ordinal classification models (e.g., Ordinal Logistic Regression)
- Implement explainability tools (e.g., SHAP or LIME)

---

## 👩‍💻 Author

Olivia Boe
MSBA Candidate, Carlson School of Management  
