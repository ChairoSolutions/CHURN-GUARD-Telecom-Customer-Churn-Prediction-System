# CHURN-GUARD-Telecom-Customer-Churn-Prediction-System

##  Project Overview
In this project, I built a machine learning model to predict **customer churn** for a telecom company. The goal was to identify customers who are likely to leave the service so that the business can take proactive retention actions.

Customer churn is a critical problem because retaining existing customers is often more cost-effective than acquiring new ones. This project focuses not just on model accuracy, but on building a solution that is **practically useful for business decision-making**.

---

##  Objectives
- Identify key factors that drive customer churn  
- Build predictive models to classify churn vs non-churn customers  
- Improve model performance using:
  - Threshold tuning  
  - Class imbalance handling  
- Compare multiple models and select the best one  
- Generate actionable business insights  

---

##  Dataset
The dataset contains customer information such as:

- Account details (account length, area code)
- Usage behavior (day, evening, night minutes)
- Service features (international plan, voicemail)
- Customer service interactions
- Target variable: **Churn (True/False)**

---

##  Exploratory Data Analysis (EDA)

Key findings from the analysis:

- Customers with **international plans churn more**
- High number of **customer service calls** is strongly associated with churn
- Higher **daytime usage** shows a positive relationship with churn
- Overall, churn is influenced more by **customer experience and behavior** than static attributes

---

##  Data Preprocessing

Steps performed:

- Removed irrelevant features (e.g., phone number as an identifier)
- Encoded categorical variables (one-hot encoding where appropriate)
- Checked for multicollinearity
- Split data into training and testing sets:
  - Training samples: 2666  
  - Testing samples: 667  

---

##  Models Built

I trained and evaluated the following models:

- Logistic Regression (baseline)
- Random Forest
- Gradient Boosting

---

##  Initial Model Performance

The baseline Logistic Regression model achieved:

- Accuracy: 86%  
- Recall (churn): 24%  

Although accuracy was high, the model **missed most churners**, making it unsuitable for real-world use.

---

##  Model Improvements

### 1. Threshold Tuning

Instead of using the default 0.5 threshold, I tested lower thresholds:

| Threshold | Precision | Recall | F1 |
|---|---|---|---|
| 0.5 | 0.56 | 0.26 | 0.35 |
| 0.4 | 0.50 | 0.36 | 0.42 |
| 0.3 | 0.44 | 0.47 | 0.46 |
| 0.2 | 0.37 | 0.61 | 0.46 |

 **Insight:**
- Lowering the threshold significantly improves recall
- Best balance achieved around **0.2–0.3**

---

### 2. Handling Class Imbalance

Applied:

```python
class_weight='balanced'
Result: 
- Recall improved from 24% to 70%
- Model became much better at detecting churners

## Model Benchmarking Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|------|------|------|------|------|------|
| Logistic Regression | 0.74 | 0.32 | 0.70 | 0.44 | 0.80 |
| Random Forest | 0.92 | 0.89 | 0.53 | 0.66 | 0.89 |
| Gradient Boosting | 0.96 | 0.95 | 0.77 | 0.85 | 0.89 |

 **Best Model: Gradient Boosting**

Gradient Boosting outperformed all other models:

- Highest accuracy (96%)
- Highest recall (77%)
- Highest precision (95%)
- Best F1 score (0.85)

 **Why it matters:**

- Captures most churners
- Minimizes false positives
- Provides the best balance for business use

---

##  Feature Importance

The most important features influencing churn:

- Customer service calls
- Total day minutes
- International plan
- Total international minutes
- Voicemail usage

---

##  Business Insights

### 1. Customer Support is a Major Churn Driver

Customers who frequently contact support are more likely to churn.

 **Action:**

- Improve customer service experience
- Prioritize customers with repeated complaints

### 2. High Usage Customers Are At Risk

Heavy users tend to churn more, possibly due to pricing sensitivity.

 **Action:**

- Offer personalized plans
- Provide loyalty incentives

### 3. International Plan Customers Have Higher Churn

These customers may face higher costs or unmet expectations.

 **Action:**

- Re-evaluate pricing
- Introduce better international bundles

---

##  Final Conclusion

Initially, the model showed high accuracy but failed to identify churners due to class imbalance and default threshold settings. By applying threshold tuning and class weighting, I significantly improved the model’s ability to detect churn.

After benchmarking multiple models, Gradient Boosting emerged as the best-performing model, offering the optimal balance between precision and recall.

This model can help businesses proactively identify at-risk customers and implement targeted retention strategies, ultimately reducing churn and improving customer lifetime value.

---

##  Future Improvements

- Apply SHAP for model explainability
- Perform hyperparameter tuning
- Deploy model using Flask or Streamlit
- Conduct ROI analysis for retention strategies

---

##  Tools & Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib

---

##  Author

Brian Chairo