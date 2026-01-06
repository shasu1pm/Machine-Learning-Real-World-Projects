# Anova Insurance – Health Risk Classification

## 📌 Project Overview
This project builds a **machine learning–based health risk classification system** to help Anova Insurance make **data-driven insurance eligibility and premium pricing decisions**.  
Applicants are classified as **Healthy** or **Unhealthy** based on medical, lifestyle, and demographic data.

---

## 🧩 Problem Statement
Anova Insurance, a global health insurance company, seeks to optimize insurance policy **premium pricing and eligibility decisions** based on applicant health status.

Understanding an applicant’s health condition is critical for:
- Determining eligibility for health insurance coverage
- Adjusting premium rates when higher health risks are identified

### Objective
Develop a **predictive classification model** that labels applicants as:
- **Healthy (0)**
- **Unhealthy (1)**

This enables consistent, scalable, and explainable underwriting decisions.

---

## 🧠 Machine Learning Approach
- **Problem Type:** Supervised Binary Classification
- **Target Variable:** `Target`  
  - `0` → Healthy  
  - `1` → Unhealthy
- **Input Features:**  
  Health metrics, lifestyle habits, medical history, and demographic attributes
- **Output:** Health risk classification + probability score

---

## 📊 Dataset Summary
- **Rows:** 10,000  
- **Features:** 20  
- **Feature Types:**
  - Numerical (Age, BMI, Blood Pressure, Glucose, etc.)
  - Ordinal categorical (Smoking, Alcohol, MentalHealth, Medical History)
  - Nominal categorical (Diet_Type, Blood_Group)
- **Data Challenges:**
  - Missing values
  - Negative age values
  - Mixed feature types

---

## 🔁 Project Workflow – Step-by-Step

### **Step 1: Data Preparation & Modeling Workflow**
- Exploratory Data Analysis (EDA)
- Data cleaning (missing values, negative ages)
- Feature engineering
- Train–test split
- Model training and comparison
- Initial evaluation and interpretation

### **Step 2: Problem Understanding**
- Business objective alignment
- ML objective definition
- Target and feature clarification

### **Step 3: Model Usage & Decision Flow**
- Insurance eligibility assessment
- Premium pricing guidance
- Risk stratification support (not final decision-making)

### **Step 4: Key Modeling Considerations**
- High impact of false negatives (Unhealthy → Healthy)
- Recall prioritization for Unhealthy class
- Threshold tuning
- Handling mixed data types and data quality issues

### **Step 5: Success Criteria**
**Technical Metrics**
- Accuracy (baseline)
- Recall (Unhealthy class)
- Precision
- F1-score
- ROC-AUC

**Business Outcomes**
- Better premium differentiation
- Reduced underwriting risk
- Scalable, explainable health scoring

### **Step 6: Insurance-Focused Risk Stratification**
- Probability-based risk scoring
- Risk bands: Low / Medium / High
- Premium multiplier mapping

### **Step 7: Export & Delivery**
- Final output delivered as a **single Excel file** with two tabs:
  1. `1_anova_health_risk_predictions`
  2. `2_Success Criteria`

---

## 🧪 Models Used
- Logistic Regression (baseline, interpretable)
- Random Forest
- Gradient Boosting

Models are evaluated and compared with emphasis on **Recall for the Unhealthy class**.

---

## 📈 Business Value
- Enables **risk-aware underwriting**
- Improves **premium pricing accuracy**
- Reduces insurer exposure to high-risk applicants
- Provides explainable, auditable ML outputs

---

## 🛠️ Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- Google Colab
- Matplotlib

---

## ▶️ How to Run
1. Open the notebook in **Google Colab**
2. Upload the dataset (CSV or Excel)
3. Run cells step-by-step
4. Download final output from **Step 7**

---

## ✅ Final Outcome
A **production-ready, explainable health risk classification system** that bridges machine learning predictions with real-world insurance decision-making.

---

## 📄 License
This project is for educational and demonstration purposes.
