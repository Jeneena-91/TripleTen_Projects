## Insurance Company ML project
## Overview
This project explores the use of machine learning techniques to solve various business problems for the Sure Tomorrow Insurance Company. The dataset includes demographic information about insured individuals and the number of insurance benefits they have received over five years. The objective is to evaluate ML methods for customer segmentation, classification, regression, and secure data transformation. 
## Dataset
File: /datasets/insurance_us.csv

Features:
- gender – Insured person's gender
- Age – Age of the insured
- salary – Annual salary
- family_members – Number of family members

Target:
- insurance_benefits – Number of benefits received over the last 5 years

## Preprocessing
- Checked for missing values, duplicates, and incorrect data types
- Verified feature distributions and correlations using visualizations (e.g., pairplots)
- Applied data scaling where appropriate (e.g., MaxAbsScaler)

## Tasks & Results
- Task 1: Find Similar Customers
Approach:
Used the k-Nearest Neighbors (kNN) algorithm with various scaling and distance metric combinations:
- Distance metrics: Euclidean, Manhattan
- Scaling: Raw vs MaxAbsScaler

Findings:
- Scaling is crucial in distance-based models to prevent bias (e.g., income dominating the distance metric)
- Scaled data significantly improved neighbor selection, model reliability, and downstream task performance

- Task 2: Classification – Will a Customer Receive Any Benefits?
      - Baseline: Dummy classifiers with constant probabilities yielded low F1-scores (max ~0.21)
      - Model: kNN Classifier (k=1 to 10)
      - Metric: F1 Score

Results:

|k	|Original Data F1|	Scaled Data F1|
|----|-----------|--------|
|1|	0.66|	0.95|
|5|	0.17|	0.95|
|10|	0.02|	0.95|


The model vastly outperforms dummy classifiers, particularly on scaled data. Scaling enabled stable and accurate predictions across various k values.

- Task 3: Regression – Predict Number of Benefits

Model: Linear Regression
Metrics: RMSE, R²

Performance:

RMSE: 0.36

R²: 0.66


The model explains 66% of the variance in the data, which is decent for a linear model. Feature scaling does not significantly affect model performance due to scale-invariance in linear regression.

- Task 4: Data Protection (Obfuscation)
     - Goal: Obfuscate personal data to preserve privacy without degrading model performance.
     - Method: Applied a transformation algorithm to features (e.g., data rotation, feature mixing).
     - Test: Compare model results before and after obfuscation.

Results:

RMSE: 0.36 (unchanged)

R²: 0.43 after transformation (acceptable drop)


The obfuscation algorithm maintains model performance, validating that sensitive information is protected without sacrificing prediction accuracy.

## Key Takeaways
- Distance-based models (like kNN) require feature scaling for fairness and accuracy.
- Predictive models significantly outperform untrained baselines.
- Linear regression provides a decent baseline for regression tasks.
- Data obfuscation is effective when designed carefully and tested rigorously.

 ## Technologies Used
- Programming Language
  
Python 3.11+ – Core language for data analysis, machine learning, and automation

- Data Manipulation & Analysis
  
       - Pandas – Data cleaning, transformation, and handling

       - NumPy – Numerical operations and efficient array management

- Data Visualization
  
      - Matplotlib – Plotting static charts and graphs

     - Seaborn – Advanced statistical visualizations built on top of Matplotlib

- Machine Learning
scikit-learn –

       - Algorithms: k-Nearest Neighbors, Linear Regression

      - Model evaluation: F1-score, RMSE, R²

      - Preprocessing: Scaling, encoding, train/test split

- Development Tools
  
Jupyter Notebook – Interactive coding environment used for development and experimentation

## Future Work
- Explore more robust classifiers (Random Forest, Gradient Boosting) for benefit prediction
- Enhance data obfuscation using differential privacy techniques
- Implement model interpretability (e.g., SHAP) to explain predictions
