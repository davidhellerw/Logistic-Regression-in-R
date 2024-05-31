# Predicting Diabetes Onset Using Logistic Regression

## Introduction

The prediction of diabetes onset is a crucial task in medical diagnostics, with significant implications for patient care and healthcare systems worldwide. Early detection of diabetes can lead to timely interventions, potentially mitigating the severity of the disease and improving patient outcomes. This project leverages the Pima Indians Diabetes Database from Kaggle to develop a predictive model for diabetes onset using logistic regression in R. The dataset comprises medical information from female patients of Pima Indian heritage, including variables such as glucose concentration, blood pressure, BMI, and age.

The primary goal of this project is to enhance my skills in logistic regression using R. By analyzing the relationships between the predictor variables and the target variable (diabetes outcome), I aim to understand the intricacies of the modeling process, identify key risk factors associated with diabetes, and predict the likelihood of its onset. This hands-on experience is intended to deepen my understanding of data analysis and machine learning techniques applied to a real-world dataset.

## Dataset

The [Pima Indians Diabetes Database (from Kaggle)](https://www.kaggle.com/uciml/pima-indians-diabetes-database) contains diagnostic measurements from a subset of female individuals of Pima Indian heritage, aged at least 21 years. The dataset consists of 768 observations and 9 attributes, including pregnancies, glucose level, blood pressure, skin thickness, insulin levels, BMI, diabetes pedigree function, age, and the target variable indicating the presence or absence of diabetes.

## Key Steps

1. **Data Loading and Exploration:** The dataset is loaded and examined to understand its structure and contents.
2. **Model Building:** An initial logistic regression model is fitted using all available predictors.
3. **Model Optimization:** The model is refined using stepwise selection to retain the most significant predictors.
4. **Models Comparison:** The full model and the optimal model are compared to understand which one performs better and why.
5. **Model Evaluation:** The performance of the model is assessed using metrics such as accuracy, precision, recall, F1 score, and the area under the ROC curve (AUC).
6. **Visualization:** The ROC curve is plotted to visualize the model's discriminative ability.

## Conclusions

**Strengths of the Model:**
- The model demonstrates a strong ability to distinguish between individuals who will develop diabetes and those who will not, as indicated by the high AUC value of 0.8396.
- It achieves a high overall accuracy of 78.39%, correctly classifying a significant majority of instances.
- With a precision of 74.06%, the model minimizes false alarms and unnecessary interventions by correctly identifying positive outcomes.

**Weaknesses of the Model:**
- The model's performance is hindered by its relatively low recall of 58.58%, suggesting that it misses identifying about 41.42% of actual positive instances.
- The moderate F1 score of 65.42% indicates room for improvement in balancing the trade-off between precision and recall.
- Due to the imbalanced nature of the dataset, there is a potential bias towards predicting the majority class (no diabetes onset), which may lead to suboptimal performance in identifying individuals at risk.

In conclusion, while the model demonstrates proficiency in accurately predicting negative outcomes, its effectiveness in identifying positive instances is limited. Improvements such as balancing the dataset, adjusting class weights, exploring feature engineering, and considering alternative algorithms are essential for enhancing the model's performance and reliability in predicting diabetes onset.

## Suggestions for Model Improvement

1. **Balancing the Dataset:** Employ techniques such as undersampling the majority class or oversampling the minority class to address class imbalance and improve model performance.
2. **Adjusting Class Weights:** Utilize class-weight parameters to give more importance to the minority class during model training, ensuring better representation of both classes.
3. **Feature Engineering:** Explore the inclusion of interaction terms or additional relevant features to capture complex relationships within the data and improve predictive accuracy.
4. **Model Selection:** Consider exploring alternative algorithms or ensemble methods that may better handle imbalanced data and capture subtle patterns more effectively.
