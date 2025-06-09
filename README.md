# Obesity Risk Classification Using Machine Learning

## Overview

Obesity is a serious and growing health issue linked to chronic diseases like diabetes, heart disease, and sleep apnea. Since prevention is significantly easier than treatment, the goal of this project is to build a predictive model that can classify individuals into different obesity risk categories based on lifestyle and biometric data.

Using a dataset of over 21,000 entries with features like height, weight, gender, eating habits, and activity levels, this project applies machine learning techniques to create a tool that could be used by individuals or health-oriented businesses to provide early risk detection and encourage healthier decisions.

---

## Objectives

- Predict obesity risk levels using supervised classification models.
- Evaluate the performance of different algorithms.
- Analyze feature importance to understand what factors influence obesity most.
- Use visualizations (confusion matrix, feature importance plots, correlation heatmaps, etc.) to interpret model behavior.
- Recommend data-driven solutions to improve health outcomes.

---

## Dataset

The dataset includes the following types of features:
- **Biometric**: Height, Weight, Age, Gender
- **Lifestyle**: Water intake, fast food consumption, physical activity, transportation type, etc.
- **Target**: Obesity level (7 classes)

Preprocessing steps included:
- Dropping irrelevant or highly imbalanced dummy variables
- Scaling features using `StandardScaler`
- Optional dimensionality reduction with PCA
- Label encoding of categorical variables

---

## Models Used

- **Logistic Regression**:  
  Achieved 87% accuracy. Performed very well on clear-cut classes like Obesity_Type_III and Insufficient_Weight. Struggled slightly with borderline categories like Overweight_Level_I and II.

- **Decision Tree**:  
  Accuracy: 88%. Showed high interpretability, with Weight being the dominant feature. Some confusion in mid-range classes but overall strong performance.

- **Random Forest**:  
  Best performer overall. Accuracy: 90%. Extremely confident on extreme classes and handled overlapping categories better than Decision Trees.

---

## Key Visualizations

- **Confusion Matrices**: Used to evaluate misclassification patterns. All models performed best on distinct classes but had overlapping predictions on adjacent weight categories.
  
- **Classification Reports**: Provided precision, recall, and F1-score for each class. The reports confirmed model strengths and weaknesses seen in the confusion matrices.
  
- **Feature Importance**:  
  - Weight was the strongest predictor across all models.
  - Gender and Height followed in importance.
  - Behavioral features like water intake, fast food consumption, and alcohol had relatively low importance in the Decision Tree model.
  
- **Correlation Heatmap**: Showed low multicollinearity across most features, validating that each contributed unique information.

---

## Final Thoughts

This project proves that machine learning can effectively classify obesity risk with high accuracy and strong interpretability. The models were especially successful with clearly defined categories and offer actionable insights for early intervention.

Improvements could include:
- Hyperparameter tuning for even better performance
- Feature engineering to capture interactions between behaviors
- Incorporating time-series or longitudinal data if available

Ultimately, this tool can help both individuals and organizations better understand the lifestyle factors driving obesity and take proactive steps to prevent it.

---

## Data Dictionary

| Feature        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| Gender         | Gender of the individual (Male/Female)                                      |
| Age            | Age in years                                                                |
| Height         | Height in meters                                                            |
| Weight         | Weight in kilograms                                                         |
| family_history_with_overweight | Whether there is a family history of being overweight (Yes/No)        |
| FAVC           | Frequent consumption of high-calorie food (Yes/No)                          |
| FCVC           | Frequency of vegetable consumption (scale 1–3)                              |
| NCP            | Number of main meals per day                                                |
| CAEC           | Consumption of food between meals (No, Sometimes, Frequently, Always)       |
| SMOKE          | Whether the individual smokes (Yes/No)                                      |
| CH2O           | Daily water intake in liters                                                |
| SCC            | Monitors caloric intake (Yes/No)                                            |
| FAF            | Frequency of physical activity (hours per week)                             |
| TUE            | Time spent using technology per day (hours)                                 |
| CALC           | Frequency of alcohol consumption (No, Sometimes, Frequently)                |
| MTRANS         | Main mode of transportation (e.g., Public_Transportation, Walking, etc.)    |
| obesity_level  | Target variable: classifies individual into obesity risk category           |

Note: One-hot encoding was applied to categorical variables like CAEC, CALC, MTRANS during preprocessing. Low-variance and highly imbalanced dummies were dropped before modeling.

---

Let me know if you'd like this in `.md`, `.txt`, or as a `README.pdf` format!
