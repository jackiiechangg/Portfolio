# Predicting Customer Churn Factors Analysis 
### Tools & Technologies
- Python  
- pandas  
- scikit-learn  
- Logistic Regression  
- Random Forest  
- ROC-AUC and classification metrics
  
## Project Overview 

Customer retention is one of the most important metrics that determines an organization's longevity, yet companies rarely understand why customers leave. Without clear visibility into these factors, it'd difficult to know which type of customers to attract and what about the organization is critical to customer retention. Because bringing in new customers is far more expensive than keeping current ones, understanding churn drivers is an important analytics problem. 

This project aims to address the question: **What customer behavior and operational factors have the greatest impact on churn rates?**


## Data & Metrics 

- The original dataset consisted of 10,000 observations with 32 features (full list included in python notebook), including a binary churn indicator (0 indicates retention / 1 indicates the customer churned)
- Mix of behavioral, financial, satisfaction, and demographic metrics
- Data is taken from Kaggle and is synthetic
- Target variable is churn.

### Preprocessing steps:
- Dropped observations with missing values  
- Removed identifier columns not relevant to prediction  
- Separated features and target variable  
- Applied a stratified train/test split to preserve churn distribution  
- Standardized numeric features  
- Encoded categorical variables  

### Feature Categories

| Category | Features |
|--------|----------|
| Customer Profile | Age, gender, location, tenure, contract type |
| Product Usage | Logins, session duration, feature usage, activity trends |
| Billing & Payment | Subscription fees, revenue, payment failures, discount |
| Customer Support | Tickets, resolution time, CSAT, complaints |

After preprocessing, the final dataset used for the project consisted of **7,955 observations with 32 features**.

## Methodology

### Logistic Regression

Logistic regression was used as a baseline model given the binary target variable and its coefficient-based interpretability. Coefficient analysis revealed the strongest drivers of churn:

| Feature | Description | Coefficient |
|-------|------------|-------------|
| csat_score | Customer satisfaction | -0.54 |
| tenure_months | Months with company | -0.42 |
| monthly_logins | Account activity | -0.38 |
| payment_failures | Failed payments | 0.37 |

The results indicate that customer retention is strongly influenced by engagement and financial interaction with the platform of the organization. Payment failures increase churn likelihood, suggesting friction in billing or transactions contribute to attrition, while higher satisfaction, longer tenure, and frequent usage signal stronger cutstomer attachment. Overall, behavioral indicators appear more predictive of churn than static attributes, emphasizing engagment and payment stability as key areas to monitor. 

### Model Performance:
The logistic regression model achieved an accuracy of 89.6% and a ROC-AUC of 0.716, indicating the model's reasonable predictive power to distinguish between churned and retained customers.

- Accuracy: 0.896  
- Precision: 0.316  
- Recall: 0.019  
- F1-score: 0.035  
- ROC-AUC: 0.716  

### Random Forest

After running the regression, I decided to run a random forest model to capture any potential nonlinear relationships and feature interactions that logistic regression might miss. The model achieved an accuracy of 89.8% and a ROC-AUC of 0.712, which is similar to the logistic regression model. While the Random Forest did not improve predictive performance, it reaffirms that the relationships between the predictors and churn are largely linear in the dataset.

## Conclusion

This analysis demonstrates that customer churn in this data is mainly influenced by financial behavior and engagement, with payment failures increasing churn risk and higher satisfaction, longer tenure, and more monthly logins reducing it. Logistic regression provided a clear, interpretable baseline, while Random Forest confirmed that nonlinear relationships did not substantially improve prediction, suggesting that the key drivers are largely linear.
