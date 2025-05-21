# Telecom Customer Churn Analysis

## Project Overview
This project explores customer churn within a telecommunications company, aiming to predict which customers are likely to leave based on their usage patterns and service preferences. The dataset consists of **15,043 customer records**, with various demographic, contract, and service-related features.

## Dataset
The dataset contains **21 attributes** describing customer demographics, subscription details, and monthly charges. The target variable **"Churn"** (Yes/No) indicates whether a customer has left the service.

### Attributes:
- **customerID** – Unique identifier for each customer.
- **gender** – Male or Female.
- **SeniorCitizen** – 1 (Yes), 0 (No).
- **Partner** – Whether the customer has a partner (Yes/No).
- **Dependents** – Whether the customer has dependents (Yes/No).
- **tenure** – Number of months the customer has stayed with the company.
- **PhoneService** – Whether the customer has phone service (Yes/No).
- **MultipleLines** – Whether the customer has multiple lines (Yes/No/No phone service).
- **InternetService** – Type of internet service (DSL, Fiber optic, No).
- **OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport** – Availability of additional online services (Yes/No/No internet service).
- **StreamingTV, StreamingMovies** – Subscription to streaming services (Yes/No/No internet service).
- **Contract** – Type of customer contract (Month-to-month, One year, Two year).
- **PaperlessBilling** – Whether the customer has paperless billing (Yes/No).
- **PaymentMethod** – Payment method (Electronic check, Mailed check, etc.).
- **MonthlyCharges** – Monthly bill amount.
- **TotalCharges** – Total billed amount.
- **Churn** – Target variable indicating customer departure (Yes/No).

## Data Processing Steps
### 1. Data Cleaning
- Removed missing values from `TotalCharges`.
- Converted `SeniorCitizen` to categorical.
- Ensured `PhoneService` consistency (e.g., those with no service cannot have multiple lines).
  
### 2. Exploratory Data Analysis (EDA)
- Visualised customer demographics and service subscriptions.
- Analysed relationships between churn and key factors like tenure, contract type, and monthly charges.
- Performed **Chi-Square correlation** to identify categorical features linked to churn.

### 3. Feature Engineering
- Selected correlated features for modelling.
- One-hot encoded categorical variables.
- Scaled numerical data for better model performance.

## Model Training & Evaluation
Multiple classification models were trained to predict churn:
- **Logistic Regression**: Accuracy: **82.23%**, AUC: **0.7359**
- **K-Nearest Neighbor (KNN)**: Accuracy: **76.76%**, AUC: **0.6739**
- **Random Forest**: Accuracy: **82.09%**, AUC: **0.7171**
- **Support Vector Machine (SVM)**: Accuracy: **81.80%**, AUC: **0.7285**
- **XGBoost**: Accuracy: **80.73%**, AUC: **0.7239**
- **Neural Network**: Accuracy: **82.16%**, AUC: **0.7344**

### Model Comparison:
| Algorithm | Train Accuracy | Test Accuracy | AUC Score |
|-----------|---------------|--------------|-----------|
| Logistic Regression | 79.61% | 82.23% | 0.7359 |
| KNN | 83.02% | 76.76% | 0.6739 |
| Random Forest | 80.99% | 82.09% | 0.7171 |
| SVM | 79.27% | 81.80% | 0.7285 |
| XGBoost | 91.80% | 80.73% | 0.7239 |
| Neural Network | 79.85% | 82.16% | 0.7344 |

## Key Findings
- Customers with **Month-to-month contracts** are the most likely to churn.
- Higher **Monthly Charges** correlate with a higher churn rate.
- **Senior Citizens** have a significantly higher likelihood of churn.
- Customers with **Partners or Dependents** are less likely to leave the service.
- **Internet Service type and additional security features** impact customer retention.

## Conclusion
This analysis provides valuable insights for customer retention strategies. Optimising service packages, providing better incentives for long-term contracts, and targeting high-risk customers for engagement can help reduce churn rates.

---
