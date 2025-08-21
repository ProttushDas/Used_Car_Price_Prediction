# Used Car Price Prediction System

This project is a regression problem focused on predicting the price of used cars. It uses a dataset of used cars with various features to train and evaluate multiple machine learning models.

## Project Description

The goal of this project is to create a system that can accurately predict the price of a used car based on its attributes. The process involves comprehensive data cleaning, exploratory data analysis (EDA), and the implementation of several machine learning regression models.

## Dataset

The dataset used, `used_cars_data.csv`, contains 7,252 entries and 13 columns after removing one duplicate entry. The data was collected in 2019. The following features are included:

* **`name`**: The full name of the car, including brand and model.
* **`location`**: The city where the car is located.
* **`year`**: The year of manufacture.
* **`kilometers_driven`**: The total distance the car has been driven.
* **`fuel_type`**: The type of fuel the car uses (e.g., Diesel, Petrol, CNG).
* **`transmission`**: The type of transmission (Manual or Automatic).
* **`owner_type`**: The ownership history of the car (First, Second, etc.).
* **`mileage`**: The fuel efficiency in km/kg or kmpl.
* **`engine`**: The engine displacement in CC.
* **`power`**: The engine power in bhp.
* **`seats`**: The number of seats in the car.
* **`new_price`**: The new car price (this column was largely incomplete and dropped from the analysis).
* **`price`**: The target variable, representing the price of the used car.

## Data Preprocessing & Feature Engineering

The project notebook details a structured approach to preparing the data for modeling:

* **Handling Missing Values**: Rows with missing values in the `price` column (the target variable) were dropped. The remaining missing values in `engine`, `seats`, and `power` were imputed by grouping the data by car name and using the mean of that group to fill in the missing values. An outlier in `kilometers_driven` was also removed.
* **Column Cleaning**: The `name` column was split to create new `make` and `model` features to allow for more granular analysis. Units were removed from the `mileage`, `engine`, and `power` columns to convert them to numerical data types.
* **New Feature Creation**: A `car_age` feature was created by subtracting the `year` from the year the dataset was collected (2019).
* **Categorical Encoding**: Locations were grouped into broader `region` categories (North, South, East, West) to simplify the model.

## Exploratory Data Analysis (EDA)

The notebook includes a comprehensive EDA section that examines the distribution of the numerical features and the frequency of categorical features. The distributions of several key features (`engine`, `kilometers_driven`, and `power`) were found to be skewed and have high kurtosis, indicating a need for appropriate model selection or data transformations to handle these characteristics.

## Modeling

The project uses several regression models to predict car prices. The performance of these models is compared to determine the most effective approach. The models trained and evaluated include:

* **Linear Regression**
* **Decision Tree Regressor**
* **Random Forest Regressor**

The performance of each model is evaluated using metrics like R-squared, Mean Squared Error (MSE), and Mean Absolute Error (MAE).
