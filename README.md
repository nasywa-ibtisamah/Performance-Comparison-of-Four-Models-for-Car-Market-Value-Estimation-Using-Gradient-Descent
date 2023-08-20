# Project Description

Hello there :wave:
I hope this project finds you well!

In this project, I will compare four models to determine which one has the lowest RMSE value along with the fastest processing time. These models are utilized to estimate the market value of cars using gradient descent techniques.


**Objective**

Training the gradient descent model and performing hyperparameter tuning using the Root Mean Square Error (RMSE) metric to evaluate the model.

**Used Model**
1. Linear Regression Model
2. Decision Tree Model
3. Random Forest Model
4. CatBoost

# Steps

1. Data Overview
2. Data preprocessing
3. Model Training and Evaluation

## 1. Data Overview

**Features:**

-   `DateCrawled` - the date when the profile was downloaded from the database
-   `VehicleType` - type of vehicle body
-   `RegistrationYear` - year of vehicle registration
-   `Gearbox` - type of transmission
-   `Power` - power (in horsepower)
-   `Model` - vehicle model
-   `Mileage` - mileage (measured in km, based on specific regional dataset)
-   `RegistrationMonth` - month of vehicle registration
-   `FuelType` - type of fuel
-   `Brand` - vehicle brand
-   `NotRepaired` - whether the vehicle has been repaired before
-   `DateCreated` - date of profile creation
-   `NumberOfPictures` - number of vehicle pictures
-   `PostalCode` - postal code of the profile owner (user)
-   `LastSeen` - date of the user's last activity

**Target:**

-   `Price` - price (in euros)

**Conclusion of Data Exploration Stage**
1. Column names are not standardized. They will be converted to lowercase.
2. There are missing values in the following columns: Model (5.5%), Gearbox (5.5%), FuelType (9.28%), VehicleType (10.5%), NotRepaired (10%).
3. Columns that are not used will be dropped, namely: date_crawled, date_created, number_of_pictures, postal_code, last_seen, registration_month.
4. The column number_of_pictures will be dropped as it contains constant values.
5. In the numerical columns, there are some anomalies observed:
- price with a value of 0
- registration_year with values 4000, 6000, 8000, 9999
- power with a value of 0, which should not have values equal to 0.

## 2. Data Preprocessing

The following are data preprocessing steps I did in this project:
1. Standardizing Column Names
2. Drop Unused Columns
3. Checking for Data Anomalies
4. Handling Missing Values
5. Encoding Features

## 3. Model Training and Evaluation

#### 1. Comparison of Linear Regression and Decision Tree Regressor

1. In terms of time, the Linear Regression model takes 384 ms to train the model and 114 ms to predict.
2. In terms of time, the Decision Tree Regressor model takes 532 ms to train the model and 53.4 ms to predict.
3. In terms of RMSE values, the results for the Linear Regression model are as follows:
- RMSE for the train set: 3030.918640114626
- RMSE for the validation set: 3011.971271674251
- RMSE for the test set: 3037.850419864315

4. In terms of RMSE values, the results for the Decision Tree Regressor model are as follows:
- RMSE for the train set: 2080.8215792004166
- RMSE for the validation set: 2096.1324636142726
- RMSE for the test set: 2108.0985267118494

5. In terms of processing time, Linear Regression has a slight advantage (although the time difference is not significant). However, the RMSE values are better when using the Decision Tree Regressor model.

#### 2. Comparison of Decision Tree Regressor and Random Forest Regressor

1. In terms of time, the Decision Tree Regressor model takes 532 ms to train the model and 53.4 ms to predict.
2. In terms of time, the Random Forest Regressor model takes 1 minute and 9 seconds to train the model and 5.2 seconds to predict.
3. In terms of RMSE values, the results for the Decision Tree Regressor model are as follows:
- RMSE for the train set: 2080.8215792004166
- RMSE for the validation set: 2096.1324636142726
- RMSE for the test set: 2108.0985267118494
4. In terms of RMSE values, the results for the Random Forest Regressor model are better, but not significantly so, with the following details:
- RMSE for the train set: 2032.9603534810776
- RMSE for the validation set: 2046.7549186999825
- RMSE for the test set: 2062.256812392978
5. In terms of processing time, Linear Regression is more efficient (with a significant time difference). Regarding RMSE values, Random Forest performs better, but the difference is not significant.

#### 3. Comparison of CatBoost and Decision Tree Regressor

1. In terms of time, the Decision Tree Regressor model takes 532 ms to train the model and 53.4 ms to predict.
2. In terms of time, the CatBoost model takes 26.4 seconds to train the model and 522 ms to predict.
3. In terms of RMSE values, the results for the Decision Tree Regressor model are as follows:
- RMSE for the train set: 2080.8215792004166
- RMSE for the validation set: 2096.1324636142726
- RMSE for the test set: 2108.0985267118494
4. In terms of RMSE values, the results for the CatBoost model are significantly better with the following results:
- RMSE for the train set: 1575.4128372253374
- RMSE for the validation set: 1615.0450134140049
- RMSE for the test set: 1645.5720694106196
5. In terms of processing time, Linear Regression is more efficient (with an insignificant time difference). Regarding RMSE values, CatBoost performs significantly better.

# General Conclusion

From the 4 models that have been trained along with the comparison findings for each model, it can be concluded that the CatBoost model has the best (lowest) RMSE values with processing time that is not significantly different from the Decision Tree Regressor.
