## Predict the best region for a new well
## Objective
OilyGiant, a mining company, is planning to develop a new oil well. The goal of this project is to identify the most profitable region for drilling, based on existing geological survey data. This includes:
- Predicting the volume of oil reserves in potential wells using Linear Regression.
- Calculating expected profit from wells with the highest predicted reserves.
- Performing risk analysis using the Bootstrapping technique.
- Selecting the best region with maximum profit and minimum risk (loss risk < 2.5%).
## Dataset Description
Data is collected from three regions:
- geo_data_0.csv
- geo_data_1.csv
- geo_data_2.csv
## Features:
|Column|	Description|
|id|	Unique oil well identifier|
|f0, f1, f2|	Features representing geological characteristics|
|product|	Target variable: volume of reserves (in thousand barrels)|

## Technologies Used

- Data Manipulation	pandas, numpy
- Machine Learning	scikit-learn (Linear Regression only)
- Imbalanced Sampling	N/A (uniform distributions)
- Visualization	matplotlib, seaborn
- Statistical Modeling	Bootstrapping via numpy
- Development Environment	Jupyter Notebook
## Project Workflow
1. Data Loading and Preprocessing
       - Loaded all three datasets.
       - Checked for duplicates and missing values.
       - Performed EDA using:
                 - Histograms for distribution of features.
                 - Boxplots to identify outliers.
                 - Correlation heatmaps.
2. Model Training & Evaluation
      - Split each dataset into:75% training and 25% validation
      -  Trained Linear Regression models on each region's data.
      - Evaluated with RMSE and average predicted reserves.

Results:
|Region	|RMSE	Avg.| Predicted Reserves (k barrels)|
|Region 0|	37.58	|92.59|
|Region 1	|0.89	|68.73|
|Region 2	|40.03	|94.97|

3. Profit Calculation Preparation
- Budget: $100 million to drill 200 wells.
- Revenue per 1k barrels: $4,500
- Break-even reserve volume per well: 111.11 thousand barrels

Conclusion:
No region meets the break-even reserve threshold, but Region 2 comes closest (94.97k barrels), making it a promising candidate pending profit and risk analysis.

5. Profit Calculation (Top 200 Predicted Wells)
Profit = (Total target reserves of top 200 wells × 4.5) - 100 million

|Region|	Predicted Profit (USD)|
|Region 0|	$33,208,260|
|Region 1	|$24,150,867|
|Region 2|	$27,103,500|
Conclusion:
Region 0 delivers the highest predicted profit based on top 200 well predictions.

5. Risk Analysis via Bootstrapping (1000 Iterations)
Using 1000 bootstrapped samples:
- Randomly selected 500 wells for top 200 predictions
- Calculated profit
- Measured:Mean profit, 95% confidence interval, Risk of loss (negative profit)

Results:
|Region	|Mean Profit (USD)|	Risk of Loss (%)|
|Region 0|	$3.79 million|	7.4%|
|Region 1|	$4.54 million|	1.10% |
|Region 2|	$3.96 million	|6.6

After evaluating profit and risk:
    - Region 1 has the highest average profit ($4.54M)
    - Lowest risk of loss (1.10% < 2.5% threshold)

## Recommended Region: Region 1
It offers a strong balance of profitability and acceptable risk, making it the best choice for oil well development.

