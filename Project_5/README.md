## Customer Churn Prediction for Beta Bank
## Overview
Beta Bank is facing a slow but steady loss of customers each month. Since retaining existing customers is more cost-effective than acquiring new ones, the objective of this project is to predict customer churn based on historical behavioral data. By identifying potential churners early, the bank can take proactive measures to retain them.

This project focuses on building a classification model that achieves a minimum F1 score of 0.59, with additional evaluation using the AUC-ROC metric.

## Project Steps
1. Data Loading and Initialization
       - Imported necessary libraries.
       - Loaded the dataset.
       - Reviewed basic statistics and structure.
2. Data Preprocessing
       - Checked for duplicates and missing values.
       - Encoded categorical features (Geography, Gender) using appropriate techniques.
       - Scaled numerical features where necessary.
3. Data Splitting
     - Split the dataset into: Training set, Validation set, Test set
4. Initial Modeling (Without Handling Class Imbalance)
   - Built and evaluated basic models: DecisionTreeClassifier, RandomForestClassifier, LogisticRegression. Observed class imbalance negatively impacting F1 score.
5. Class Imbalance Handling and Model Tuning
      Applied two main techniques: Class weighting (class_weight='balanced'), Resampling (SMOTE / under-sampling). Performed hyperparameter tuning using validation data. Evaluated each model based on F1 and AUC-ROC metrics.
6. Final Model and Evaluation
     - Best model: RandomForestClassifier with class_weight='balanced'
     - Final F1 Score: 0.63
     - AUC-ROC: 0.8689
## Results
|Metric	|Score|
|F1 Score|	0.63|
|AUC-ROC|	0.869|
The F1 score exceeds the project requirement (0.59).
AUC-ROC indicates strong model performance in distinguishing between churned and non-churned customers.
## Technologies Used
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Jupyter Notebook
  
## Conclusion
- RandomForestClassifier with class weighting performed best in balancing precision and recall.
- Both F1 and AUC-ROC metrics affirm that the model is suitable for identifying churn risks.
This model can be integrated into Beta Bank's retention strategy for proactive customer engagement.
