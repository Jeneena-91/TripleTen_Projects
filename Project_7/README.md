## Predict the amount of gold recovered from gold ore.
##  Objective
The goal of this project is to build a machine learning model for Zyfra to predict the amount of gold recovered from ore during industrial extraction and purification. By accurately predicting recovery rates, the company can optimize production and minimize losses from non-optimal processing parameters.
## Project Overview
Gold ore goes through several stages of processing:
- Flotation (Rougher stage): Extracts rougher gold concentrate from the ore.
- Purification: Two stages of processing are used to yield a final concentrate.

The model predicts gold recovery based on various input parameters recorded during these processes.

## Data Description
Files Used:
- /datasets/gold_recovery_train.csv – Training dataset
- /datasets/gold_recovery_test.csv – Test dataset (without targets)
- /datasets/gold_recovery_full.csv – Complete dataset for reference
## Data Characteristics:
- Indexed by datetime
- Contains numerical process parameters and target values
- Some features are only available in the training set due to the delay in measuring or calculating them

## Technologies Used

|Purpose|	Tools / Libraries|
|--------|----------|
|Language|	Python 3.8+|
|Data Handling	|pandas, numpy|
|Visualization|	matplotlib, seaborn|
|Modeling|	scikit-learn|
|Model Evaluation|	Custom SMAPE function|
|Hyperparameter Tuning|	GridSearchCV|
|Environment|	Jupyter Notebook|
## Project Workflow
1. Data Preparation
Loaded all datasets and checked for:
- Missing values
- Duplicates
- Data types

- Verified that rougher.output.recovery is calculated correctly 
- MAE from calculation: ~9.30e-15 (effectively zero)
- Compared test and train sets to identify missing features in the test set (mostly target and post-process features).

2. Data Analysis
- Analyzed metal concentrations (Au, Ag, Pb) across stages:
           Feed - Rougher concentrate - Final concentrate
- Compared particle size distributions between train and test sets:
         Confirmed similar distributions - No adjustment needed
- Examined total concentration of substances:
       Identified and removed rows with zero or near-zero total concentration (likely invalid readings)

3. Model Building
Evaluation Metric: sMAPE (Symmetric Mean Absolute Percentage Error)
Custom function used to calculate combined sMAPE for:
- rougher.output.recovery (25% weight)
- final.output.recovery (75% weight)

Models Tested:

|Model|	sMAPE (%)|
|-------|-------|
|DecisionTreeRegressor|	16.33|
|LinearRegression|	11.99|
|RandomForestRegressor|	10.83|

RandomForestRegressor achieved the best cross-validation performance.

Final Model:
Hyperparameter tuning with GridSearchCV

Final test set sMAPE: 8.80%

## Conclusion
- The RandomForestRegressor performed best for predicting gold recovery with a final test sMAPE of 8.80%.
- Model helps Zyfra optimize production decisions, ensuring higher efficiency and reduced material loss.
- Proper preprocessing, anomaly filtering, and metric selection were essential for reliable performance.
