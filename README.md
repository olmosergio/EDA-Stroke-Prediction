
# 🚀 Project: Stroke Prediction (EDA)

An Exploratory Data Analysis (EDA) on Kaggle's "Stroke Prediction" dataset to identify key risk factors associated with cerebrovascular accidents.

![1763200202221](image/README/1763200202221.png)

---

### 1. Problem Context

The objective of this project is to analyze a patient dataset to understand which variables (demographic, lifestyle, and medical) have the highest correlation or impact on the probability of suffering a stroke.

### 2. Analysis Phases

1. **Data Cleaning:**
   * Identified null values in the `bmi` column (approx. 3% of the data).
   * Decided to **impute** these values using the **median** instead of the mean to avoid the influence of outliers.
2. **Univariate Analysis (Per Variable):**
   * **Critical Imbalance:** A severe imbalance was detected in the target variable (`stroke`): less than 5% of patients suffered a stroke.
   * **Distributions:** `age` is left-skewed (more elderly patients), while `bmi` and `avg_glucose_level` are right-skewed.
   * **Key Finding:** `avg_glucose_level` shows a  **bimodal distribution** , suggesting two distinct population groups (healthy patients and hyperglycemic patients).
3. **Bivariate Analysis (Relationship with Stroke):**
   * Categorical variables (like `smoking_status`) were analyzed using proportions (100% fill plots) to avoid erroneous conclusions due to the data imbalance.
   * Confirmed that `age`, `hypertension`, and `heart_disease` are the strongest individual predictors.
4. **Encoding and Correlation Matrix:**
   * Applied **Label Encoding** to binary variables (e.g., `ever_married`) and **One-Hot Encoding** to multi-category variables (e.g., `work_type`).
   * The final correlation matrix confirmed that **no single variable** has "magical" predictive power. Stroke risk is a  **complex combination of multiple factors** .

### 3. Key Findings (Insights)

* **Imbalance is the Challenge:** Any future model must be trained by handling this imbalance (e.g., with techniques like SMOTE or by adjusting class weights).
* **Age is the #1 Factor:** `age` is, by far, the variable with the highest correlation (0.25).
* **Combined Risk Factors:** Hypertension, heart disease, and high glucose levels are clear risk factors.

### 4. Next Steps

The logical next step after this EDA is to build a Machine Learning model. The pre-processing would include:

1. Scaling numerical variables (`StandardScaler`).
2. Handling the imbalance (`SMOTE`).
3. Training classification models (Logistic Regression, Random Forest...).

### 5. Technologies Used

* Python
* Pandas (Data Manipulation)
* Matplotlib & Seaborn (Visualization)
* Jupyter Notebook
