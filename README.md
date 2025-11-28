# ML_Assignment2

Section 1: Problem Formulation & Target Variable Analysis

The business problem is to predict loan default. The dataset provides a target variable "loan_paid_back". Your first task is to understand what a "default" means in this context.

The core business objective is to assess the risk of borrower default. In the provided dataset, the target variable is loan_paid_back.

Target Definition:

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
