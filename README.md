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
- Converted numerical columns to proper formats.
- Applied One-Hot Encoding to categorical variables and scaled numerical features as needed to prepare the data for model training.

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

## Visualizations

- 📌 **PRC Curve** for each classifier  
- 📌 **Confusion Matrix** plotted using `ConfusionMatrixDisplay`  
- 📌 **GridSearchCV verbose outputs** to monitor tuning progress

---

### ▶ Model Comparison Summary

| Model               | Accuracy | Precision (>50K) | Recall (>50K) | F1 (>50K) | Best Use Case               |
|---------------------|----------|------------------|----------------|-----------|-----------------------------|
| Logistic Regression | 0.80     | 0.57             | **0.84**       | 0.68      | High recall on >50K class   |
| Random Forest       | 0.79     | 0.56             | **0.89**       | 0.69      | ▶ Best for tax screening    |
| Gradient Boosting   | 0.86     | 0.77             | 0.67           | 0.71      | Balanced performance        |
| K-Nearest Neighbors | 0.84     | 0.69             | 0.65           | 0.67      | Moderate performance        |
| Linear SVC          | 0.80     | 0.57             | **0.86**       | 0.68      | Lightweight, fast model     |

---

🔚# **Final Conclusion**.

After thorough **model development**, **hyperparameter tuning**, and **performance evaluation**, the **Random Forest Classifier** emerged as the **most effective model**, achieving the **highest recall (0.89)** for identifying *high-income individuals (>50K)*.

🎯 **Best Use Case**:  
Ideal for real-world applications such as:  
- **Tax eligibility screening** . 
- **Policy targeting**.  
- **Income-based resource allocation**.

Both **Logistic Regression** and **Linear SVC** demonstrated **competitive performance**, showing a strong balance between **precision** and **recall**. These models are excellent for scenarios requiring:
- **Interpretability**.
- **Lightweight deployment**.

 **Hyperparameter tuning** played a key role in improving:
- Generalization.
- Fairness across income classes.
- Class-specific performance (especially for the minority class).


**Radhika P S**  
_Machine Learning Enthusiast
India | 2025  
