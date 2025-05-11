## Predicting Obesity with Machine Learning
=========================

### Executive Summary

Obesity is a major health issue worldwide, driven by lifestyle, eating habits, and genetics. Catching it early can help prevent serious health problems, but predicting obesity risk isn't always straightforward. With machine learning and data analysis, we can pinpoint key risk factors and predict someone's likelihood of becoming obese. This gives people the chance to take action before it happens, making healthier choices based on data insights.

#### Who is Affected?

- Individuals who may be at risk of obesity.

- Healthcare providers looking to offer proactive care.

- Policymakers and researchers working on obesity prevention strategies.

#### Proposed Data Science Solution

Classification models will be explored and the model will not only predict obesity risk but also explain which lifestyle changes could help reduce it.

#### Impact of the Solution

- Personalized health recommendations.

- Healthcare applications where doctors and nutritionists can use the model to guide patients.

- Preventative strategies for meal planning services and fitness apps.

- People who have obesity in their family and want to take precautions. 
### Demo

### Methodology
- Exploratory Data Analysis (EDA) to understand trends and class distribution

- Feature Engineering: created binary features, combined sparse columns, removed low-variance and redundant features

- Preprocessing: applied standard scaling and log transformation to reduce skew. Created a seperate dataframe for group PCA

- Modeling: Trained and tuned a logistic regression model and decision trees model using Pipeline and GridSearchCV

Evaluation: Achieved ~87% accuracy with balanced precision and recall across all obesity levels

### Organization

#### Repository 

#### Dataset
Source: https://www.kaggle.com/datasets/fatemehmehrparvar/obesity-levels

Size: ~20,000 records

Features: Demographics, dietary habits, physical activity, lifestyle indicators

Target: obesity_level (7-class categorical variable)

### Credits & References
