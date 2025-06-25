# Car Price Prediction Analysis

## Project Overview
This project explored a dataset from Kaggle, originally containing information on 3 million used cars, but provided with 426K cars for efficient processing. The primary goal of this analysis was to understand what factors make a car more or less expensive, and to provide clear recommendations to a used car dealership regarding what consumers value in a used car. This task was framed using the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework, a standard industry process for data projects.

## Dataset
The analysis is based on the `vehicles.csv` dataset, which contains various attributes of listed vehicles. 
The dataset underwent several cleaning and preprocessing steps to ensure data quality and prepare it for modeling. Key preprocessing steps included:
* Handling missing values, specifically by dropping rows with missing year and price information.
* Outlier removal for price and odometer using the Interquartile Range (IQR) method to ensure the models are not skewed by extreme values.

### Feature Engineering:
* Transforming `year` into `age` (current year - vehicle year) for better interpretability by models.
* Extracting numerical cylinder values from the `cylinders` column.
* Calculating `mileage_per_year` from odometer and age, providing a more standardized measure of vehicle usage.

## Methodology

### Data Preparation
After the initial data cleaning and feature engineering, the dataset was split into training and testing sets. Categorical features (condition, manufacturer, fuel, drive, type, size) were transformed using One-Hot Encoding to convert them into a numerical format suitable for machine learning algorithms. Numerical features (age, mileage_per_year, cylinders) were scaled using StandardScaler to normalize their ranges.

### Model Training and Evaluation
**Four different regression models were trained and evaluated on the prepared dataset:**
1.  Linear Regression 
2.  LGBMRegressor (Light Gradient Boosting Machine) 
3.  Linear Regression with Polynomial Features 
4.  Random Forest Regressor
5.  Selected Features (Linear) LGBM

## Key Findings
Based on the analysis, the following features were identified as significant drivers that increase car price:
* **Age**: Newer vehicles (lower age) tend to have higher prices.
* **Mileage per Year OR Overall Mileage**: Cars with lower mileage per year (indicating less annual usage) are generally associated with higher prices.
* **Cylinders**: Number of cylinders are also identified as drivers of price increase

## Model Performance Summary

### R-Squared
* **Model 1 Linear Regression**: 0.36 
* **Model 2 LGBMRegressor**: 0.6 
* **Model 3 Linear Regression with Polynomial Features**: 0.48 
* **Model 4 Random Forest Regressor**: 0.80
* **Model 5 Selected Features (Linear) LGBM**: 0.53
