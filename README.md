# Income Classification ML Project

## Project Overview

This project uses supervised machine learning to classify whether a person's income is `<=50K` or `>50K` based on demographic and occupational features. This is a classic **binary classification problem** based on the **UCI Adult Income Dataset**.

---

## Dataset Summary

- **Source**:https://archive.ics.uci.edu/dataset/2/adult
- **Rows**: 32,561
- **Target**: `income` (`<=50K`, `>50K`)
- **Features**: `age`, `education`, `occupation`, `hours-per-week`, `race`, `sex`, and more

▶**Use case**: Predicting income groups can support **tax eligibility estimation**, **policy planning**, and **financial decision-making**.

---

## Project Objective

> Build and compare multiple classification models to accurately predict high-income individuals, with a focus on **recall** for the `>50K` class to minimize false negatives (i.e., avoid missing actual high earners).

---

## Tools & Libraries

- Python, Pandas, NumPy
- Scikit-learn (for models, metrics, tuning)
- Matplotlib & Seaborn (for visualization)

---

## Steps Performed

### 1. **Data Preprocessing**
- Handled missing values (`?` → `NaN`)
- Normalized categorical features (e.g., `.str.strip().str.lower()`)
- Converted numerical columns to proper formats
- Label encoded and scaled features as needed

### 2. **Model Building**
- Built models:
  - Logistic Regression
  - Random Forest
  - Gradient Boosting
  - K-Nearest Neighbors (KNN)
  - LinearSVC

### 3. **Evaluation Metrics**
- `accuracy`, `precision`, `recall`, `f1-score`
- `confusion_matrix` for class-level analysis
-▶ **Precision-Recall Curve (PRC)** for visualizing trade-offs in imbalanced classification
-▶ **F1 Score (macro/weighted)** used for balanced model comparison

### 4. **Hyperparameter Tuning**
- Used `GridSearchCV` and `RandomizedSearchCV`
- Tuned key parameters like:
  - `C`, `penalty`, `class_weight` (for Logistic & SVC)
  - `n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf` (for RF/GB)
-▶Tuning significantly improved **recall** and **f1-score** for minority class (`>50K`)

---

▶ Model Comparison Summary

| Model               | Accuracy | F1 (>50K) | Recall (>50K) | Best Use Case               |
|--------------------|----------|-----------|----------------|-----------------------------|
| Logistic Regression| 0.80     | 0.69      | **0.85**       | High recall on >50K class   |
| Random Forest       | 0.79     | 0.69      | **0.89**       | ▶ Best for tax screening    |
| Gradient Boosting   | 0.86     | 0.72      | 0.67           | Balanced performance        |
| KNN                 | 0.84     | 0.67      | 0.65           | Moderate performance        |
| Linear SVC          | 0.80     | 0.68      | **0.86**       | Lightweight, fast model     |

---

## Visualizations

- 📌 **PRC Curve** for each classifier  
- 📌 **Confusion Matrix** plotted using `ConfusionMatrixDisplay`  
- 📌 **GridSearchCV verbose outputs** to monitor tuning progress

---

🔚 Final Conclusion

- After model tuning and comparison, **Random Forest** showed the **best recall** (0.89) for identifying high-income individuals, making it ideal for applications like **tax assessment** or **eligibility screening**.
- Logistic Regression and Linear SVC also performed well, especially in **precision-recall balance**.
- Hyperparameter tuning proved **essential** for improving model generalization and ensuring fairness across classes.

---


**Radhika P S**  
_Machine Learning Enthusiast
India | 2025  
