# Flight Ticket Price Prediction

## Overview

This project develops a machine learning pipeline to predict airline ticket prices using flight-related attributes such as airline, source, destination, departure time, arrival time, number of stops, travel class, duration, and days left until departure.

The workflow covers the complete machine learning lifecycle, including data preprocessing, exploratory data analysis (EDA), feature engineering, model training, hyperparameter tuning, and model evaluation.

---

## Dataset

The dataset consists of:

* **Train Dataset:** 40,000 flight records with ticket prices.
* **Test Dataset:** 10,000 flight records without ticket prices.
* **Target Variable:** `price`

### Features

| Feature     | Description                     |
| ----------- | ------------------------------- |
| airline     | Airline operating the flight    |
| flight      | Flight number                   |
| source      | Departure city                  |
| departure   | Departure time slot             |
| stops       | Number of stops                 |
| arrival     | Arrival time slot               |
| destination | Arrival city                    |
| class       | Economy or Business class       |
| duration    | Flight duration                 |
| days_left   | Days remaining before departure |
| price       | Ticket price (target variable)  |

---

## Project Workflow

### 1. Data Exploration

* Identified data types of all features.
* Generated descriptive statistics for numerical columns.
* Examined dataset structure and feature distributions.

### 2. Missing Value Handling

* Categorical features were imputed using the most frequent value.
* Numerical features were imputed using K-Nearest Neighbors (KNN) imputation.

### 3. Duplicate Detection

* Checked both training and testing datasets for duplicate records.
* No duplicate rows were found.

### 4. Outlier Analysis

* Detected outliers using the Interquartile Range (IQR) method.
* Removed extreme outliers from the target variable (`price`).
* Retained duration outliers after assessing their impact on model performance.

### 5. Exploratory Data Analysis

Key visualizations include:

* Flight Class vs Ticket Price
* Ticket Price Distribution
* Number of Flights per Airline

### Key Insights

* Business class tickets are significantly more expensive than economy tickets.
* Ticket prices exhibit a right-skewed distribution.
* Vistara accounts for the highest number of flights in the dataset.

### 6. Feature Engineering

* One-Hot Encoding applied to categorical variables.
* Min-Max Scaling applied to numerical features.

---

## Models Trained

The following regression models were evaluated:

1. Linear Regression
2. Ridge Regression
3. Lasso Regression
4. Decision Tree Regressor
5. Random Forest Regressor
6. K-Nearest Neighbors Regressor
7. Gradient Boosting Regressor

---

## Hyperparameter Tuning

Hyperparameter optimization was performed using:

* GridSearchCV for Ridge Regression
* GridSearchCV for Lasso Regression
* RandomizedSearchCV for Random Forest Regression

---

## Model Performance

| Model             | RMSE    | MAE     | R² Score |
| ----------------- | ------- | ------- | -------- |
| Random Forest     | 3549.80 | 1778.88 | 0.975    |
| Decision Tree     | 4334.54 | 1918.20 | 0.963    |
| Gradient Boosting | 5177.05 | 3132.23 | 0.948    |
| KNN Regressor     | 5643.31 | 3387.54 | 0.938    |
| Ridge Regression  | 6411.45 | 4459.85 | 0.920    |
| Linear Regression | 6422.55 | 4475.15 | 0.920    |
| Lasso Regression  | 6446.83 | 4448.13 | 0.919    |

### Best Performing Model

**Random Forest Regressor**

* RMSE: 3549.80
* MAE: 1778.88
* R² Score: 0.975

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

---

## Results

The Random Forest Regressor achieved the best overall performance and was used to generate final ticket price predictions for the test dataset.

This project demonstrates an end-to-end machine learning workflow, including data cleaning, feature engineering, model evaluation, and hyperparameter tuning for a real-world regression problem.
