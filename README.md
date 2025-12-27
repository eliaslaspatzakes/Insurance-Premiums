# 🏥 Health Insurance Premium Prediction & Pricing Strategy

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![ML](https://img.shields.io/badge/Model-MLP%20Regressor-orange)](https://scikit-learn.org/)
[![Explainability](https://img.shields.io/badge/SHAP-Explainable%20AI-green)](https://shap.readthedocs.io/)
[![Dashboard](https://img.shields.io/badge/View-Live%20Dashboard-red)](https://eliaslaspatzakes.github.io/Insurance-ML-Analysis/insurnace_ml.html)

## 📋 Project Overview
This project builds an end-to-end Machine Learning pipeline to predict annual health insurance premiums. By analyzing customer behavior and health metrics, we developed a **Neural Network (MLP)** model to calculate fair pricing strategies.

The solution includes a full **ETL pipeline** (SQL → Python), rigorous **EDA**, model training, and a **SHAP-based explainability layer** to justify pricing decisions to stakeholders.

### 🔗 [View the Interactive Dashboard](https://eliaslaspatzakes.github.io/Insurance-ML-Analysis/insurnace_ml.html)

---

## 🔍 Key Findings (EDA)

* **Smoking is the #1 Cost Driver:** Smokers pay **~35% more** (€742 vs €550) than non-smokers.
* **Income ≠ Risk:** High-risk customers are distributed evenly across all income levels. Pricing cannot be based on income alone.
* **Chronic Diseases:** There is a non-linear surge in premiums for customers with 2+ chronic conditions.
* **Medical History:** Customers with high past medical costs pay **3x more** than low-cost customers.

---

## 🛠️ Methodology

### 1. Data Engineering
* Extracted raw data from **PostgreSQL**.
* Feature Engineering: Created `risk_score_group`, `chronic_count`, and grouped continuous variables (BMI, Age) into business-friendly bins.

### 2. Machine Learning Model
* **Model:** Multi-Layer Perceptron Regressor (Neural Network).
* **Preprocessing:** `StandardScaler` for numerics, `OneHotEncoder` for categoricals.
* **Optimization:** Tuned hidden layers and learning rate using `RandomizedSearchCV`.

### 3. Model Performance
| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **R² Score** | **0.76** | Explains 76% of price variance. |
| **MAE** | **€95.82** | Average error is ~16.5% of the premium. |

### 4. Explainability (SHAP)
Used SHAP (SHapley Additive exPlanations) to create **Waterfall plots** for individual customers, proving exactly *why* a specific price was charged (e.g., "+€446 due to High Medical Cost history").

---

## 💻 Tech Stack
* **Database:** PostgreSQL
* **Analysis:** Python (Pandas, NumPy, SQLAlchemy)
* **ML:** Scikit-Learn (MLPRegressor, RandomForest), XGBoost
* **Viz:** Matplotlib, Seaborn, SHAP
* **Dashboard:** HTML5, Tailwind CSS, Chart.js
