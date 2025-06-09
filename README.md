# Predicting Obesity with Machine Learning

## Executive Summary

Obesity is a global health concern tied to serious conditions like diabetes, heart disease, and sleep apnea. The earlier we can predict obesity risk, the better our chances of preventing it. This project uses machine learning to analyze lifestyle habits, eating patterns, and physical activity to classify individuals into obesity risk categories.

By identifying the strongest predictors of obesity, this model can help individuals, healthcare professionals, and wellness platforms take early, data-informed action.

---

## Who is Affected?

- Individuals who may be at risk of obesity  
- Healthcare providers aiming to offer proactive care  
- Policymakers and researchers focused on prevention  
- Nutritionists, personal trainers, and health app developers  
- Families with a history of obesity looking to reduce risk

---

## Proposed Data Science Solution

We approach this as a **multiclass classification** problem, building a model that predicts a person’s obesity level and highlights the most influential lifestyle factors contributing to that risk.

---

## Impact of the Solution

- Personalized health recommendations
- Support tools for doctors and nutritionists
- Prevention strategies for gyms, wellness coaches, and meal-planning apps
- Educational outreach for high-risk individuals and families

---

## Demo
*Coming soon.*  
A walk-through Jupyter Notebook showing data exploration, feature engineering, and model results.

---

## Methodology

### Exploratory Data Analysis (EDA)
- Investigated class distribution and trends across features like meals per day, activity level, and food intake.
- Visualized relationships between obesity levels and lifestyle habits.

### Feature Engineering
- Created dummy variables from categorical features
- Removed low-variance and redundant features
- Standardized column names and fixed data quality issues

### Preprocessing
- Scaled numeric variables using `StandardScaler`
- Created grouped datasets for dimension reduction (Grouped PCA)
- Addressed data skew and ensured input consistency across models

### Modeling Journey

1. **Logistic Regression**  
   - Used as the baseline model  
   - Performed well with regularization and tuning  
   - Highlighted multicollinearity and non-linearity challenges for some features

2. **Decision Tree Classifier**  
   - Tuned using GridSearchCV (max depth, min samples split/leaf)  
   - Helped visualize decision paths and identify most influential features  
   - Slightly overfit on training data

3. **Random Forest (Final Model)**  
   - Chosen for its balance between performance and interpretability  
   - Achieved ~87% accuracy  
   - Delivered strong recall and precision across all 7 obesity classes  
   - Feature importances and SHAP analysis helped explain model behavior

---

## Model Evaluation

- **Accuracy**: ~87% on test set  
- **F1-Score**: Balanced across all classes (no single class dominated performance)  
- **Confusion Matrix**: Low misclassification between adjacent obesity levels  
- **Permutation Importance + SHAP**: Confirmed model was learning meaningful patterns, not noise

---

## Data Dictionary

<details>
<summary><strong>Click to expand</strong></summary>

| Column Name                     | Description                                          | Data Type | Possible Values / Units                                                               | Example              |
|--------------------------------|------------------------------------------------------|-----------|----------------------------------------------------------------------------------------|----------------------|
| Age                            | Age of each person                                  | Float     | 14-61                                                                                  | 25                   |
| Height                         | Height of each person                               | Float     | Meters                                                                                 | 1.70                 |
| Weight                         | Weight of each person                               | Float     | Kgs                                                                                    | 70                   |
| family_history_with_overweight| Obese family member?                                | Boolean   | 0 or 1                                                                                 | 0                    |
| FAVC                           | High-caloric food consumption                       | Boolean   | 0 or 1                                                                                 | 0                    |
| FCVC                           | Vegetable consumption frequency                     | Float     | 1 - 3                                                                                  | 2                    |
| NCP                            | Number of main meals                                | Float     | 1 - 4                                                                                  | 3                    |
| SMOKE                          | Smoker or not                                       | Boolean   | 0 or 1                                                                                 | 0                    |
| water                          | Daily water consumption                             | Float     | 1 - 3 (units not specified)                                                            | 2.6                  |
| SCC                            | Caloric beverages consumption                       | Boolean   | 0 or 1                                                                                 | 0                    |
| physical_activity_freq         | Physical activity frequency                         | Float     | 0 - 3 (units not specified)                                                            | 2.4                  |
| TUE                            | Technology use hours                                | Float     | 0 - 2 (units not specified)                                                            | 1.7                  |
| obesity_level                  | Obesity class label                                 | String    | ['Overweight_Level_II', 'Normal_Weight', ..., 'Obesity_Type_I']                       | 'Overweight_Level_I' |
| CAEC_Always                    | Always eats between meals                           | Boolean   | 0 or 1                                                                                 | 0                    |
| CAEC_Frequently                | Frequently eats between meals                       | Boolean   | 0 or 1                                                                                 | 1                    |
| CAEC_Never                     | Never eats between meals                            | Boolean   | 0 or 1                                                                                 | 0                    |
| CAEC_Sometimes                 | Sometimes eats between meals                        | Boolean   | 0 or 1                                                                                 | 1                    |
| Gender_Female                  | Gender = Female                                     | Boolean   | 0 or 1                                                                                 | 1                    |
| Gender_Male                    | Gender = Male                                       | Boolean   | 0 or 1                                                                                 | 1                    |
| alcohol_con_Frequently         | Frequently consumes alcohol                         | Boolean   | 0 or 1                                                                                 | 1                    |
| alcohol_con_Never              | Never consumes alcohol                              | Boolean   | 0 or 1                                                                                 | 1                    |
| alcohol_con_Sometimes          | Sometimes consumes alcohol                          | Boolean   | 0 or 1                                                                                 | 1                    |
| MTRANS_Automobile              | Transportation by automobile                        | Boolean   | 0 or 1                                                                                 | 1                    |
| MTRANS_Bike                    | Transportation by bike                              | Boolean   | 0 or 1                                                                                 | 0                    |
| MTRANS_Motorbike               | Transportation by motorbike                         | Boolean   | 0 or 1                                                                                 | 1                    |
| MTRANS_Public_Transportation   | Transportation by public transport                  | Boolean   | 0 or 1                                                                                 | 1                    |
| MTRANS_Walking                 | Transportation by walking                           | Boolean   | 0 or 1                                                                                 | 1                    |

</details>

---

## Repository Structure

```bash
obesity-prediction
├── data/                    # Raw and processed datasets
├── notebooks/              # Jupyter notebooks (EDA, modeling, etc.)
├── models/                 # Saved model files
├── visuals/                # Graphs and images for presentation
├── requirements.txt        # Python package dependencies
├── README.md               # This file
