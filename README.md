# Telco Customer Churn Prediction 📉

## 🚀 Project Overview
Customer retention is critical for the long-term success of any subscription-based business. Acquiring a new customer is often 5-25x more expensive than retaining an existing one.

This project utilizes Machine Learning to predict which customers are likely to churn (cancel their subscription). By analyzing customer demographics, services, and account information, this model achieves an **accuracy of ~79%**. Beyond prediction, the project identifies key drivers of churn, providing actionable insights that can help product and marketing teams design better retention strategies.

## 📊 Key Business Insights & Recommendations
Based on the feature importance analysis (Odds Ratios) performed in this project:

* **High Risk Factors:**
    * **Fiber Optic Internet:** Customers with Fiber Optic service are significantly more likely to churn (Odds Ratio > 3.0). *Recommendation: Investigate service quality or pricing competitiveness for Fiber plans.*
    * **Month-to-Month Contracts:** These customers have the highest churn rate.
    * **Electronic Check Payments:** Associated with higher churn compared to automatic payments.

* **Loyalty Drivers:**
    * **Tenure:** The longer a customer stays, the less likely they are to leave.
    * **Long-Term Contracts:** Customers on 2-year contracts are highly stable.
    * **Add-on Services:** Tech Support and Online Security correlate with lower churn.

* **Strategic Recommendation:** Implement targeted marketing campaigns to incentivize Month-to-Month users to switch to 1-Year or 2-Year contracts using discounts or free add-on services (like Tech Support).

## 🛠️ Technologies Used
* **Language:** Python 3.x
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Logistic Regression, Random Forest)
* **Visualization:** Matplotlib, Seaborn
* **Environment:** Jupyter Notebook / Google Colab

## 📂 Dataset
The project uses the **Telco Customer Churn** dataset (`WA_Fn-UseC_-Telco-Customer-Churn.csv`).
* **Rows:** 7,043 customers
* **Features:** 21 columns including tenure, contract type, payment method, monthly charges, and demographics.
* **Target:** `Churn` (Yes/No)

## ⚙️ Methodology

1.  **Data Cleaning:**
    * Handled missing values in the `TotalCharges` column.
    * Converted the target variable `Churn` to binary (0/1).
2.  **Exploratory Data Analysis (EDA):**
    * Visualized churn distribution.
    * Analyzed the relationship between churn and categorical variables (Contract, Internet Service).
    * Analyzed numerical distributions (Tenure).
3.  **Feature Engineering:**
    * Removed irrelevant identifiers (`customerID`).
    * Applied **One-Hot Encoding** for categorical variables to make them machine-readable.
    * Applied **Standard Scaling** to numerical variables (`tenure`, `MonthlyCharges`, `TotalCharges`) to normalize data range.
4.  **Model Building:**
    * **Logistic Regression:** Used as a baseline model for its interpretability (Odds Ratios).
    * **Random Forest Classifier:** Implemented to capture non-linear relationships.
    * **Class Imbalance:** Utilized `class_weight='balanced'` to improve the model's ability to detect churners (minority class).
5.  **Evaluation:**
    * Models were evaluated using Accuracy, Confusion Matrices, and Classification Reports (Precision, Recall, F1-Score).

## 📈 Model Performance
The models were trained on an 80/20 Train-Test split.

| Model | Accuracy | Key Observation |
| :--- | :--- | :--- |
| **Random Forest** | **79%** | Best overall accuracy. Robust against outliers. |
| **Logistic Regression (Weighted)** | **73%** | Prioritized **Recall** (catching more churners) over precision, which is often preferable in churn prevention contexts. |
