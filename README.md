# 🏥 Healthcare Insurance Prediction

A Machine Learning project that predicts an individual's **health insurance premium** based on demographic, lifestyle, financial, and medical attributes. The application is deployed with an interactive **Streamlit** interface, allowing users to input their details and receive an instant premium prediction.

## 🚀 Project Overview

This project follows a complete end-to-end Machine Learning workflow—from **data preprocessing** and **feature engineering** to **model deployment**. It incorporates domain-specific risk calulations, age-based model selection, and an intuitive web interface for a seamless user experience.

## 🛠️ Tech Stack

* 🐍 Python
* 📊 Pandas & NumPy
* 🤖 Scikit-learn
* 💾 Joblib (Model Serialization)
* 🎈 Streamlit (Frontend Deployment)

## ⚙️ Key Concepts Implemented

* Data Preprocessing & Feature Engineering
* One-Hot Encoding for Categorical Features
* Feature Scaling using Standard Scaler
* Custom Medical Risk Score Normalization
* Age-Based Model Selection (Separate models for young and adult users)
* Model Serialization with Joblib
* Interactive Web App using Streamlit

## 📊 Data Preprocessing & Exploratory Data Analysis (EDA)

To improve prediction accuracy and model generalization, the dataset underwent extensive preprocessing and feature engineering before training.

### 📁 Dataset Overview

* 📊 **Total Records:** **50,000**
* 👶 **Young Dataset (Age ≤ 25):** **20,096 records**
* 👨 **Adult Dataset (Age > 25):** **29,904 records**
* 📌 **13 original features** covering demographic, financial, lifestyle, and medical information.

### 🔍 EDA & Preprocessing Steps

* ✅ Performed **data quality checks** for missing values, duplicates, and inconsistent entries.
* ✅ Split the dataset into **two age-specific datasets** to better capture different premium patterns.
* ✅ Created a **custom Medical Risk Score** by assigning weighted scores to diseases:

  * ❤️ Heart Disease = **8**
  * 🩺 Diabetes = **6**
  * 🩸 High Blood Pressure = **6**
  * 🦋 Thyroid = **5**
* ✅ Normalized the medical risk score to a **0–1 scale**.
* ✅ Converted **Insurance Plan** into **Ordinal Encoding**:

  * Bronze → 1
  * Silver → 2
  * Gold → 3
* ✅ Applied **One-Hot Encoding** on **6 categorical features**:

  * Gender
  * Region
  * Marital Status
  * BMI Category
  * Smoking Status
  * Employment Status
* ✅ Generated **18+ model-ready features** after encoding and feature engineering.
* ✅ Applied **StandardScaler** independently for each age group to maintain feature consistency.
* ✅ Serialized preprocessing objects and trained models using **Joblib** for seamless deployment.

## 🤖 Machine Learning Models

Multiple regression models were experimented with and evaluated to identify the best-performing solution for healthcare premium prediction.

To identify the most accurate prediction model, multiple regression algorithms were trained and evaluated on the healthcare premium dataset.

### 📌 Models Implemented

* 📈 Linear Regression (Baseline Model)
* 📉 Ridge Regression (Regularized Linear Model)
* 🚀 XGBoost Regressor (Final Selected Model)

### 📊 Model Performance

| Model                                |              R² Score |            RMSE |
| ------------------------------------ | --------------------: | --------------: |
| 📈 Linear Regression                 |            **0.9281** |     **2272.80** |
| 📉 Ridge Regression                  |            **0.9281** |     **2272.81** |
| 🚀 XGBoost Regressor                 |            **0.9782** |     **1250.23** |
| ⭐ Tuned XGBoost (RandomizedSearchCV) | **0.9809 (CV Score)** | Best Performing |

### 🔧 Hyperparameter Tuning

The XGBoost model was further optimized using **RandomizedSearchCV**, resulting in the following best parameters:

* 🌲 Number of Trees (`n_estimators`) = **50**
* 🌳 Maximum Tree Depth (`max_depth`) = **5**
* 📉 Learning Rate (`learning_rate`) = **0.1**

The tuned XGBoost model significantly outperformed the linear models, making it the final choice for premium prediction due to its superior accuracy and ability to capture complex non-linear relationships within the data.


## 🔄 Project Workflow

```text
Healthcare Premium Dataset (50,000 Records)
                │
                ▼
      Exploratory Data Analysis (EDA)
 • Missing Value Analysis
 • Duplicate Check
 • Correlation Analysis
 • Feature Distribution
 • Outlier Inspection
                │
                ▼
      Data Preprocessing
 • Custom Medical Risk Score
 • Feature Engineering
 • One-Hot Encoding
 • Ordinal Encoding
 • Feature Scaling
                │
                ▼
     Age-Based Dataset Split
      (≤25 Years | >25 Years)
                │
                ▼
      Model Development
 • Linear Regression
 • Ridge Regression
 • XGBoost Regressor
                │
                ▼
 Hyperparameter Tuning
 (RandomizedSearchCV)
                │
                ▼
 Feature Importance Analysis
                │
                ▼
 Model Serialization (Joblib)
                │
                ▼
 Streamlit Web Application
                │
                ▼
 Real-Time Healthcare Premium Prediction
```


## 💡 Key Insights

* 📊 Age is one of the strongest predictors of insurance premium.
* 💰 Annual income and insurance plan significantly influence premium costs.
* ❤️ Individuals with multiple health conditions receive higher risk scores and consequently higher premium estimates.
* 🚬 Smoking habits and BMI category substantially impact premium prediction.
* 🧬 Genetic risk and medical history further improve prediction accuracy.
* 🎯 Using **separate preprocessing pipelines and models for different age groups** provides more personalized and reliable premium estimation than a single generalized model.
