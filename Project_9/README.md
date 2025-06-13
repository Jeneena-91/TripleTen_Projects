## Predict the market value of car 
Rusty Bargain, a used car sales service, is building a machine learning model to estimate the market value of a vehicle based on historical data. The goal of this project is to develop a predictive model that is accurate, fast, and has a reasonable training time.

## Project Objectives
- Predict the market value of used cars.
- Compare multiple models in terms of:

           - Prediction quality (using RMSE)
           - Prediction speed
           - Training time

## Dataset Description
File location: /datasets/car_data.csv

Features:
|Feature|	Description|
|------|---------|
|DateCrawled|	Date the profile was downloaded|
|VehicleType|	Body type of the vehicle|
|RegistrationYear|	Year of vehicle registration|
|Gearbox|	Type of gearbox|
|Power|	Power of the car (hp)|
|Model|	Car model|
|Mileage|	Mileage in kilometers|
|RegistrationMonth|	Month of vehicle registration|
|FuelType|	Type of fuel used|
|Brand|	Car brand|
|NotRepaired|	Whether the car has been repaired or not|
|DateCreated|	Date the profile was created|
|NumberOfPictures|	Number of car pictures|
|PostalCode|	Postal code of the user|
|LastSeen|	Date of user's last activity|

Target:
Price — Selling price of the car in Euros.

## Project Workflow
1. Data Preparation
   
- Imported libraries and loaded data
- Checked for missing values, incorrect data types, and duplicates
- Removed outliers
- Conducted exploratory data analysis

2. Model Training
Trained and compared the following models:

|Model|	RMSE|	Training Time|	Prediction Time|
|------|-----|-----------|-------------|
|Linear Regression|	2535.45|	7.05s|	0.51s|
|Decision Tree|	1847.72|	7.26s|	0.063s|
|Random Forest|	1648.28|	21m 27s|	0.51s|
|LightGBM|	1660.89|	2.13s|	0.32s|
|CatBoost|	1807.16|	5.66s|	0.038s|
|XGBoost|	1754.25|	15.79s|	0.36s|

3. Model Evaluation
- RMSE (Root Mean Squared Error) was used as the primary metric.
- LightGBM offered the best trade-off between performance and speed.
- Random Forest yielded the best RMSE, but its training time was significantly higher.

Model Recommendation
- Best Performing Model (Accuracy): Random Forest (RMSE: 1648.28)
- Best Model (Efficiency + Performance): LightGBM
- Offers competitive accuracy (RMSE: 1660.89)
- Significantly faster training (2.13s) and prediction (0.32s)

## Technologies Used
-  Data Manipulation & Visualization

                   - Pandas – Data analysis and manipulation

                   -  NumPy – Numerical operations

                   -  Matplotlib – Data visualization

                   - Seaborn – Statistical plotting

- Machine Learning & Modeling

                   - Scikit-learn – Traditional ML models (Linear Regression, Decision Tree, Random Forest)

                   - LightGBM – Fast and efficient gradient boosting

                   - XGBoost – Scalable and accurate gradient boosting

                  - CatBoost – Gradient boosting with categorical support

- Experimentation & Evaluation

                 - RMSE (Root Mean Squared Error) – Model evaluation metric

                 - Jupyter Notebook – Interactive development and analysis



## Future Improvements
- Optimize hyperparameter tuning further using techniques like RandomizedSearchCV or Optuna.
- Investigate neural networks or ensemble methods for additional performance improvements.
- Consider building a web interface or API for real-time predictions.
