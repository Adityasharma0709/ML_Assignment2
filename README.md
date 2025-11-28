# ML_Assignment2

# Section 1: Problem Formulation & Target Variable Analysis

The business problem is to predict loan default. The dataset provides a target variable "loan_paid_back". Your first task is to understand what a "default" means in this context.

The core business objective is to assess the risk of borrower default. In the provided dataset, the target variable is loan_paid_back.

### Target Definition:

loan_paid_back = 1: The loan was fully repaid (Positive Class/Non-Default).

loan_paid_back = 0: The borrower defaulted (Negative Class/Default).

Note: While standard fraud/default models often treat "Default" as the positive class (1), this dataset encodes "Paid Back" as 1. The model below predicts the probability of the loan being paid back. To interpret this as "risk of default," one can simply look at
1
−
P
(
paid_back
)
1−P(paid_back).

Class Distribution:
The dataset is moderately imbalanced:

Paid Back (1): 79.8%

Defaulted (0): 20.2%
This imbalance requires careful handling (e.g., using stratified splitting or class weights) to ensure the model effectively identifies the minority class of defaulters .

## Section 2: Feature Engineering & Preprocessing Pipeline

A robust preprocessing pipeline was designed to handle the raw data before model training.

Missing Values: No missing values were found in the dataset, so no imputation was necessary.

### Feature Selection:

- Dropped id as it is a unique identifier with no predictive power.

- Dropped grade_subgrade because it is highly correlated with interest_rate and credit_score, providing redundant information that can complicate the model.

### Categorical Encoding:

- One-Hot Encoding was applied to nominal variables: gender, marital_status, employment_status, and loan_purpose.

- One-Hot Encoding was also applied to education_level to treat categories independently without assuming a strictly linear ordinal relationship (e.g., assuming a PhD is always "better" risk than a Bachelor's).

### Numerical Scaling:

- StandardScaler was used to normalize continuous features (annual_income, debt_to_income_ratio, credit_score, loan_amount, interest_rate) to zero mean and unit variance. This ensures features with larger ranges (like income) do not dominate the model gradients or splits.

### Data Splitting:

- The data was split into 80% Training and 20% Testing sets using stratified sampling to maintain the 80:20 class distribution in both sets.
<img width="1891" height="797" alt="image" src="https://github.com/user-attachments/assets/39133bad-77a4-4687-95bf-d177043ffe21" />
