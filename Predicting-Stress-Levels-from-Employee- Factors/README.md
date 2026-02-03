# Predictive Modeling: Effects of Work Productivity & Lifestyle Habits on Employee Mental Health

### Tools & Techniques
- Python
- pandas, scikit-learn
- Supervised classification models (k-NN, Decision Trees, Random Forest, Neural Networks)
- Feature scaling and categorical encoding
- Permutation feature importance

### Problem Statement
Work-related stress has become increasingly prevalent as jobs grow more demanding and remote work becomes more common. Understanding which workplace and lifestyle factors contribute most to employee stress is critical for organizations aiming to improve employee well-being, productivity, and retention.

This project addresses the question:  
**Which work environment and lifestyle factors have the greatest impact on employee stress levels?**


### Data Overview
- **Source:** Kaggle (synthetic dataset)
- **Initial Size:** 5,000 employee observations, 20 variables
- **Final Dataset:** 1,715 observations, 30 features
- **Target Variable:** Stress_Level (binary: Low = 0, High = 1)
- **Geographic Coverage:** Global (North America, Europe, Asia, South America, Africa, Oceania)

**Feature Categories**
- Employee demographics and experience  
- Work productivity and workload metrics  
- Remote work and company support indicators  
- Lifestyle factors (sleep quality, physical activity)  
- Mental health and stress-related indicators  

### Data Preprocessing
- Removed observations with missing values  
- Dropped non-predictive identifier variables  
- Dummy-encoded categorical variables  
- Standardized numerical features  
- Converted stress level from three classes (Low, Medium, High) to a binary outcome to improve model performance  
- Evaluated correlations and determined PCA was not appropriate due to low feature redundancy  

### Methodology
Multiple supervised classification models were evaluated across several modeling approaches, including:
- k-Nearest Neighbors (k-NN)
- Decision Trees (pruned and tuned)
- Logistic Regression
- Random Forest
- Neural Networks

Due to the evenly distributed nature of the original stress categories, several modeling strategies were tested. The final approach focused on binary classification between **Low** and **High** stress levels to maximize predictive signal.

### Model Selection & Performance
- **Final Model:** k-NN (n = 49)
- **Test Accuracy:** 55.54%
- Achieved a **5% improvement over the naive baseline**, representing the largest marginal performance gain across tested models
- Accuracy was prioritized over precision and recall due to the non-critical nature of misclassification in this context

Permutation feature importance was applied to interpret model results.

### Key Findings
The most influential predictors of employee stress were:
- **Years of experience** (strongest driver)
- Employment in the **healthcare industry**
- **Company support for remote work**
- Productivity stability and education level

These findings suggest that stress is driven more by **structural and environmental factors** than short-term workload alone.

### Business Implications
- Organizations should invest in mid-career and tenured employee support
- Healthcare firms may require industry-level interventions to mitigate burnout
- Stronger organizational support for remote workers can reduce stress and disengagement
- HR teams can use predictive insights to identify high-risk employees and design preventative interventions

