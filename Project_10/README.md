## Predict the amount of taxi orders for the next hour
Sweet Lift Taxi has collected historical data on taxi orders at airports. To attract more drivers during peak hours, it's critical to predict the number of taxi orders for the next hour. This project develops a machine learning pipeline to forecast hourly taxi demand and recommends the best model based on RMSE performance.

## Data Description
- File Location: /datasets/taxi.csv
- Target Column: num_orders — Number of taxi orders at airports.
- Frequency: Data is initially recorded at arbitrary intervals and resampled to 1-hour intervals.

## Project Workflow
1. Data Loading and Cleaning
   - Imported necessary Python libraries.
  - Loaded the dataset and checked for:

              - Missing values
              - Correct data types
              - Resampled data to hourly intervals.

2. Stationarity Check
   - Performed the Augmented Dickey-Fuller (ADF) test.
   - Visualized trends, seasonality, and autocorrelation with:

     - Time series plot
     - ACF and PACF plots
     - Seasonal decomposition

3. Feature Engineering
Created time-based features like hour, day of week, lag features, and rolling statistics.

4. Model Training
- Data split:

      - Training set: 90%
      - Test set: 10%

- Models trained:
    - Linear Regression
    - Random Forest Regressor
    - Gradient Boosting Regressor
    - XGBoost Regressor
    - CatBoost Regressor
    - SARIMAX (Statistical model)

5. Evaluation Metric
   - Evaluated models using Root Mean Squared Error (RMSE)
   - Target RMSE: ≤ 48

Model Performance
|Model|	RMSE|
|------|-----|
|Linear Regression|	44.98|
|Random Forest|	42.59|
|Gradient Boosting|	43.09|
|XGBoost|	45.36|
|CatBoost|	42.09|
|SARIMAX|	40.69 |

SARIMAX showed the best performance, making it the most reliable model for hourly taxi order prediction.
## Technologies used
- Python (pandas, numpy, matplotlib, seaborn)
- scikit-learn
- XGBoost
- CatBoost
- statsmodels
- pmdarima
- Matplotlib / Seaborn for visualization

##  Conclusion
The SARIMAX model achieved the lowest RMSE of 40.69, outperforming all machine learning models. It effectively captures seasonality and temporal patterns, making it ideal for hourly demand forecasting at Sweet Lift Taxi.


