---

# 💰 Medical Insurance Cost Prediction

This project aims to **predict medical insurance charges** based on demographic and health-related factors such as age, BMI, number of children, smoking habits, and region.
It uses multiple regression models and compares their performance to identify the most accurate algorithm.

---

## 📁 **Dataset Overview**

* **Source:** Kaggle / Insurance dataset
* **Rows:** 1338
* **Columns:** 7
* **Target Variable:** `charges` (Medical insurance cost)

### **Feature Description**

| Feature    | Type   | Description                                   |
| ---------- | ------ | --------------------------------------------- |
| `age`      | int    | Age of the individual                         |
| `sex`      | object | Gender (male/female)                          |
| `bmi`      | float  | Body Mass Index                               |
| `children` | int    | Number of dependents                          |
| `smoker`   | object | Smoking status (yes/no)                       |
| `region`   | object | Residential area (northeast, northwest, etc.) |
| `charges`  | float  | Target variable — Medical insurance charges   |

---

## 🧹 **Data Preprocessing & Cleaning**

* Checked **missing values** → none found ✅
* Found **1 duplicate record** → removed
* Checked for **inconsistency** in data types (int, float, object) — all consistent
* Applied **Label Encoding** on categorical columns (`sex`, `smoker`, `region`)

---

## 📊 **Exploratory Data Analysis (EDA)**

* Created **histograms** for target variable (`charges`)
* Analyzed **skewness (1.51)** and **kurtosis (1.60)** → data was right-skewed
* Used **pairplots, scatterplots, catplots, and countplots** to visualize relationships
* Applied **log transformation** to normalize skewed `charges` distribution
* Rechecked distribution → became more symmetrical and near-normal

---

## 🔍 **Feature Correlation**

| Feature  | Correlation with `charges` |
| -------- | -------------------------- |
| smoker   | 0.74                       |
| age      | 0.53                       |
| children | -0.10                      |
| bmi      | -0.23                      |
| sex      | -0.38                      |
| region   | -0.52                      |

**Top 3 positively correlated:**

* `smoker`, `age`, `bmi`

**Least correlated:**

* `region`, `sex`, `children`

---

## 🤖 **Model Training**

Split the dataset into **80% training** and **20% testing** using `train_test_split()`

### **Models Used**

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. Gradient Boosting Regressor
5. Support Vector Regressor (SVR)

Each model was trained and evaluated using **R² Score**, **MAE**, **MSE**, and **RMSE** metrics.

---

## 📈 **Model Performance Summary**

| Model                 | R² Score (%) | MAE      | MSE      | RMSE     |
| --------------------- | ------------ | -------- | -------- | -------- |
| Linear Regression     | 71.21        | 0.30     | 0.24     | 0.49     |
| Decision Tree         | 54.52        | 0.29     | 0.38     | 0.62     |
| Random Forest         | 72.97        | 0.23     | 0.22     | 0.47     |
| **Gradient Boosting** | **74.43**    | **0.22** | **0.21** | **0.46** |
| SVR                   | 30.26        | 0.45     | 0.58     | 0.76     |

---

## 🏆 **Best Model: Gradient Boosting Regressor**

* Highest accuracy: **74.43%**
* Lowest error (MAE & RMSE)
* Handles complex relationships effectively
* Reduces overfitting and improves generalization

---

## 📊 **Visualization**

* **Bar Chart:** Model Accuracy Comparison
* **Pie Chart:** Accuracy Percentage by Model
* **Heatmap:** Feature Correlation Matrix
* **Distribution Plot:** Before & After Log Transformation

---

## 🔚 **Conclusion**

* The dataset was clean and balanced after preprocessing.
* The target variable (`charges`) was right-skewed, fixed by log transformation.
* Among all models, **Gradient Boosting Regressor** achieved the best performance with **74.43% R² Score**.
* The model can be used to **predict insurance charges accurately** for new applicants.

---

## 🧠 **Tech Stack**

* **Language:** Python
* **Libraries:**
  `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`

---
