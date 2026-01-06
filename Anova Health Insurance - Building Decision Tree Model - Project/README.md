# 🏥 Anova Health Insurance – Building a Decision Tree Model
### 🌳 Explainable Machine Learning for Insurance Risk Analytics

---

## 📌 Project Overview

**Project Name:** 🏥 **Anova Insurance Health Risk Prediction**  
**Domain:** 💼 Health Insurance | 📊 Risk Analytics  
**Model Type:** 🤖 Supervised Machine Learning  
**Task:** 🧩 **Binary Classification**  
**Algorithm:** 🌳 **Decision Tree**  
**Explainability:** 🔍 **High (Business-friendly, rule-based)**

---

## 🧭 Business Context

### 🏢 Why This Project Exists
Anova Insurance aims to **optimize health insurance eligibility and premium pricing** by accurately assessing **applicant health risk** using data-driven decisioning.

### 🔑 Key Business Decisions
- ✅ Insurance eligibility approval  
- 💰 Premium pricing (standard vs risk-adjusted)

### ⚠️ Risk Focus
- 🚫 Avoid underpricing high-risk applicants  
- 🎯 Minimize **False Negatives**  
  *(Unhealthy applicants predicted as Healthy)*

---

## 🎯 Problem Statement

### Objective
Build a predictive model that classifies individuals as:

- 🟢 **Healthy (0)**
- 🔴 **Unhealthy (1)**

using **health, lifestyle, and medical attributes**.

### Why It Matters
| Applicant Type | Impact | Business Action |
|---------------|--------|-----------------|
| 🟢 Healthy | Lower claim risk | 💸 Standard / Discounted premium |
| 🔴 Unhealthy | Higher claim risk | ⚠️ Risk-adjusted premium / Medical review |

---

## 🗂️ Dataset Overview

**Source:** 🗂️ Anova Insurance (Synthetic / Training Dataset)

**Shape**
- **Rows:** 10,000  
- **Columns:** 20  

### 🎯 Target Variable
**Name:** `Target`

- `0` → 🟢 Healthy  
- `1` → 🔴 Unhealthy  

### ❗ Data Challenges
- ❗ Missing values (especially for older individuals)
- ❌ Negative age values
- 🔄 Mixed feature types (numeric, ordinal, nominal)

---

## 🧬 Feature Breakdown

### 🔢 Numerical Features
- 🎂 Age  
- ⚖️ BMI  
- 💉 Blood_Pressure  
- 🧪 Cholesterol  
- 🍬 Glucose_Level  
- ❤️ Heart_Rate  
- 😴 Sleep_Hours  
- 🏃 Exercise_Hours  
- 🚰 Water_Intake  
- 😖 Stress_Level  

### 🔁 Ordinal Categorical (0 < 1 < 2)
- 🚬 Smoking  
- 🍺 Alcohol  
- 🥗 Diet  
- 🧠 MentalHealth  
- 🏋️ PhysicalActivity  
- 🏥 MedicalHistory  
- 🤧 Allergies  

### 🧩 Nominal Categorical
- 🍽️ Diet_Type → Vegetarian, Non-Vegetarian, Vegan  
- 🩸 Blood_Group → A, B, AB, O  

---

## 🧠 Machine Learning Objective

**Task Type:** 🧠 Classification

### 🔮 Prediction Output
- `0` → 🟢 Healthy  
- `1` → 🔴 Unhealthy  

### 🎯 Evaluation Priority
**Primary Metric:** 🚨 **Recall (Unhealthy)**

> ⚠️ False Negatives lead to **underpriced high-risk policies**,  
> which is financially dangerous for insurers.

---

## 🔄 End-to-End Workflow

### 📥 Step 1: Data Ingestion
- 📂 Load dataset  
- 🔍 Validate schema & shape  
- ✅ Ensure target ∈ `{0,1}`  

---

### 🔎 Step 2: Exploratory Data Analysis (EDA)
- 📊 Target distribution  
- 📈 Numeric feature statistics  
- 🧩 Missing value analysis  
- 🔗 Correlation with target  
- 📌 Category frequency checks  

**Outputs**
- 💡 Risk indicator hypotheses  
- 🧠 Data quality insights  

---

### 🧹 Step 3: Data Cleaning
- ❌ Convert negative ages → `NaN`  
- 🚫 Remove impossible values (BMI ≤ 0, invalid sleep hours)  
- 🛠️ Handle missing values:
  - **Numerical:** Median  
  - **Ordinal:** Mode  
  - **Nominal:** Mode / `"Unknown"`  

---

### 🏗️ Step 4: Feature Engineering
- 🔢 Preserve ordinal order (0 < 1 < 2)  
- 🧩 One-hot encode nominal features  
- ✨ Optional domain features:
  - ⚖️ BMI category  
  - 💉 Blood pressure category  
  - 🧬 Lifestyle risk score  

---

### 🔀 Step 5: Train–Test Split
- **Split Ratio:** 80 / 20  
- **Stratify:** Target  
- **Random State:** Fixed  

---

### 🌱 Step 6: Baseline Decision Tree
**Purpose:** 🧪 Establish benchmark performance

- Default depth  
- Fixed random state  

---

### 🎛️ Step 7: Hyperparameter Tuning
**Goal:** 🛡️ Control overfitting

**Parameters Tuned**
- 🌳 `max_depth`  
- 🔀 `min_samples_split`  
- 🍃 `min_samples_leaf`  
- ⚖️ `class_weight`  

**Strategy**
- 🔁 GridSearchCV / RandomizedSearchCV  
- 🎯 Optimize **Recall (Unhealthy)**  

---

### 📏 Step 8: Model Evaluation

**Technical Metrics**
- 📉 Confusion Matrix  
- 📊 Accuracy  
- 🎯 Precision (Unhealthy)  
- 🚨 Recall (Unhealthy)  
- 🧮 F1-score  
- 📈 ROC-AUC  

**Insurance Lens**
- 🚫 Track False Negatives explicitly  
- 🔧 Adjust thresholds if required  

---

### 🔍 Step 9: Model Interpretability
- ⭐ Feature importance ranking  
- 🌳 Decision Tree visualization  
- 🗣️ Human-readable IF–THEN rules  

**Example Rule**
> IF 🍬 *Glucose_Level is high* AND 🏥 *MedicalHistory is severe*  
> THEN applicant is 🔴 **Unhealthy**

---

### 🧮 Step 10: Risk Banding & Premium Mapping

**Method:** 📊 Probability-based (Recommended)

| Risk Band | Condition | Action |
|----------|-----------|--------|
| 🟢 Low | p < 0.30 | 💸 Standard / Discount |
| 🟡 Medium | 0.30 – 0.60 | ⚠️ Mild loading |
| 🔴 High | ≥ 0.60 | 🚑 Medical review / Higher premium |

---

## 🚀 Deployment Readiness

**Usage Notes**
- 🤝 Model supports decisions, not final approval  
- 👩‍⚖️ Underwriters retain authority  

**Monitoring**
- 📉 Prediction drift tracking  
- 🚨 False negative trend review  
- 🔁 Periodic retraining  

---

## ✅ Success Criteria

### 🧪 Technical
- 🎯 High recall for Unhealthy  
- 📈 Stable ROC-AUC  
- 🛡️ Controlled overfitting  

### 💼 Business
- 💰 Better premium differentiation  
- 🔐 Reduced underwriting risk  
- 🔍 Explainable & auditable decisions  

---

## 📦 Deliverables
- 📂 Cleaned dataset  
- 📊 EDA insights  
- 🌳 Trained Decision Tree model  
- 📏 Evaluation metrics  
- 🧠 Interpretable rules  
- 💸 Risk band & premium mapping  
- 🚀 Deployment-ready notebook  

---

## 🔮 Next Improvements
- 🌲 Random Forest / ⚡ Gradient Boosting comparison  
- 🎯 Probability calibration  
- ⚖️ Bias & fairness checks  
