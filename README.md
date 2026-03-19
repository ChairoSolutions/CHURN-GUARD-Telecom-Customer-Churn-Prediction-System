# 📊 SyriaTel Customer Churn Prediction

## Setup section
pip install -r requirements.txt

## 🧠 Project Overview
Customer churn is a critical problem for telecom companies, as losing customers directly impacts revenue. This project aims to build a machine learning model to predict customer churn and identify key drivers behind customer attrition.

---

## 🎯 Business Understanding
The objective of this project is to help SyriaTel reduce customer churn by:

- Identifying customers likely to leave
- Understanding the factors driving churn
- Providing actionable recommendations for retention

---

## 📂 Data Understanding

The dataset contains 3,333 customer records with 21 features, including:

- Customer demographics (state, account length)
- Service usage (day, evening, night minutes)
- Account features (international plan, voicemail plan)
- Customer interactions (customer service calls)

### 🎯 Target Variable:
- `churn` (True = customer left, False = customer stayed)

---

## 🧹 Data Preparation

Key preprocessing steps included:

- Dropping the `phone number` column (identifier, not predictive)
- Encoding categorical variables using one-hot encoding
- Splitting data into training (80%) and testing (20%) sets
- Handling class imbalance using `class_weight='balanced'`

---

## 📊 Exploratory Data Analysis (EDA)

Key insights:

- Customers with **more customer service calls** are more likely to churn
- Customers with an **international plan** have higher churn rates
- Higher **daytime usage** is associated with increased churn

---

## ⚙️ Modeling Approach

Three models were trained:

- Logistic Regression (with pipeline and scaling)
- Random Forest Classifier
- Gradient Boosting Classifier

A pipeline was used for Logistic Regression to ensure proper feature scaling and prevent data leakage.

---

## 📏 Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

A reusable evaluation function was implemented to ensure consistency across models.

---

## 🏆 Results

| Model                 | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|----------------------|----------|----------|--------|----------|---------|
| Logistic Regression  | 0.74     | 0.32     | 0.70   | 0.44     | 0.80    |
| Random Forest        | 0.92     | 0.89     | 0.53   | 0.66     | 0.89    |
| Gradient Boosting    | 0.96     | 0.95     | 0.77   | 0.85     | 0.89    |

### ✅ Final Model:
Gradient Boosting was selected due to its strong balance between precision and recall.

---

## 💡 Business Recommendations

- Focus on customers with **high customer service calls**
- Improve service experience to reduce dissatisfaction
- Target **international plan users** with retention offers
- Monitor high-usage customers for potential churn risk

---

## 🚀 Next Steps

- Deploy the model as an API for real-time predictions
- Build a dashboard for business stakeholders
- Perform hyperparameter tuning for further optimization
- Incorporate additional customer behavior data

---

## 🛠️ Tools & Technologies

- Python (Pandas, NumPy)
- Scikit-learn
- Matplotlib & Seaborn
- Jupyter Notebook

---

## 👤 Author

**Brian Chairo**  
Aspiring Data Scientist

---