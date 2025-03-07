# COVID-19 Regression Analysis Project

## Overview

This project uses regression and regularization techniques to predict early COVID-19 cases. It employs linear regression, polynomial regression, and ridge regression to estimate future cases and experiments with hyperparameters to improve results. The analysis is performed on a COVID-19 dataset from January 22, 2020, to March 31, 2020, containing approximately 10,671 rows and 8 columns.

## Data Analysis

### 1. Data Loading

The project starts by loading the COVID-19 dataset from a remote raw CSV file into a pandas DataFrame.


The dataset includes the following columns:

-   `SNo`: Serial number.
-   `ObservationDate`: Date of the observation.
-   `Province/State`: Province or state of the region.
-   `Country/Region`: Country or region.
-   `Last Update`: Last update timestamp.
-   `Confirmed`: Number of confirmed cases.
-   `Deaths`: Number of deaths.
-   `Recovered`: Number of recovered cases.

The DataFrame `df_orig` initially contains 10671 rows and 8 columns, displaying the confirmed cases, deaths and recoveries for each region on a particular date.

### 2. Cumulative Cases, Deaths, and Recoveries

A new DataFrame is created to aggregate the cumulative total number of confirmed cases, deaths, and recoveries for each date. This aggregation helps in understanding the overall trend of the pandemic.


The number of unique dates in the dataset is 70. The DataFrame `df_date_tots` is created to represent the confirmed, death, and recovered counts for each of these dates.

### 3. "Closed Cases" Column

A "Closed Cases" column is added to the DataFrame, representing the sum of deaths and recoveries.


### 4. "Active Cases" Column

An "Active Cases" column is created by subtracting "Closed Cases" from the total number of confirmed cases.


### 5. Visualizing Total Cases Over Time

The project visualizes the total number of COVID-19 cases per day over time. This visualization helps in identifying trends and patterns in the spread of the virus.


The plot shows that the number of confirmed and active cases increased exponentially from late January to the end of March, while deaths and recovered cases also increased but at a slower rate.

## Regression Analysis

The project applies various regression techniques to forecast COVID-19 cases. These techniques include:

### 1. Linear Regression

Linear regression is used as a baseline model to predict the number of confirmed cases.  The Mean Absolute Error (MAE) for Linear Regression is **181791.42** and the Mean Squared Error (MSE) is **33128805402.92**.

### 2. Polynomial Regression

Polynomial regression is employed to capture non-linear relationships in the data. The degree of the polynomial is a hyperparameter that can be tuned. The Mean Absolute Error (MAE) for Polynomial Regression is **31989.75** and the Mean Squared Error (MSE) is **1314905574.53**.

### 3. Ridge Regression

Ridge regression, a type of linear regression with L2 regularization, is used to prevent overfitting.  The Mean Absolute Error (MAE) for Ridge Regression is **181588.76** and the Mean Squared Error (MSE) is **33054982293.84**.

### 4. Polynomial Ridge Regression
Polynomial Ridge Regression is employed to capture non-linear relationships in the data while preventing overfitting by using Ridge Regression. The Mean Absolute Error (MAE) is **15796.10** and the Mean Squared Error (MSE) is **352565817.84**.

## Evaluation

The performance of each regression model is evaluated using metrics such as Mean Squared Error (MSE) and Mean Absolute Error (MAE). Based on the errors calculated the Polynomial Ridge Regression outperforms all other algorithms.

## Conclusion

This project provides a basic framework for predicting COVID-19 cases using regression techniques. The results highlight the effectiveness of polynomial ridge regression with proper hyperparameter tuning. Further improvements can be made by:

*   Feature engineering to include additional relevant variables.
*   Exploring a wider range of hyperparameter values and tuning methods.
*   Exploring more advanced regression models.
