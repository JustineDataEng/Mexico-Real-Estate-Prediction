Mexico Real Estate Price Prediction Project

Project Overview

This project focuses on predicting real estate prices in Mexico using a dataset of property listings. The goal was to build a machine learning model that could accurately estimate property values based on features like location, size (area), and property type.

After extensive data cleaning, feature engineering, and model evaluation, the Random Forest Regressor emerged as the best-performing model with an $R^2$ score of 0.83 on the test set.

Dataset

The dataset consists of real estate listings in Mexico, including:

Location: Latitude, Longitude, State, Neighborhood (extracted from place_with_parent_names).

Property Details: Surface Area (surface_covered_in_m2), Price (price_aprox_usd).

Derived Features: Price per square meter (price_usd_per_m2).

Tech Stack

Python: The core programming language.

Pandas & NumPy: For data manipulation and cleaning.

Matplotlib, Seaborn & Plotly: For exploratory data analysis (EDA) and visualization.

Scikit-Learn: For building and evaluating machine learning models.

IPyWidgets: For interactive data exploration.

Project Structure

The analysis follows a structured machine learning pipeline:

1. Data Import & Exploration

Import Libraries: Loaded Pandas, Matplotlib, Seaborn, Plotly, and Scikit-Learn.

Load Data: Ingested the Mexico real estate dataset from CSV.

Initial Inspection: Checked data shape, data types, and null values using .info() and .head().

2. Data Cleaning

Filtering: Restricted analysis to "Houses" to ensure consistent pricing logic.

Handling Nulls: Imputed missing values in numerical columns with the median.

Cleaning Location Data: Split the place_with_parent_names column to extract clean "State" and "Neighborhood" features.

Outlier Removal: Calculated price_usd_per_m2 and filtered out the top and bottom 5% of properties to remove errors and extreme luxury/distressed properties.

3. Exploratory Data Analysis (EDA)

Price Analysis: Visualized the distribution of property prices.

Correlation: Analyzed the relationship between Surface Area and Price.

Geospatial Analysis: Plotted property locations using Latitude and Longitude to verify they fall within Mexico.

4. Feature Engineering

Encoding: Applied One-Hot Encoding to categorical features like "State" to make them machine-readable.

Feature Selection: Dropped high-cardinality columns (like raw Neighborhood names) and leakage columns (like price_usd_per_m2) before training.

5. Model Building

I implemented and compared multiple regression algorithms:

Linear Regression: Established a baseline performance.

Polynomial Regression: Tested if adding complexity captured curved relationships.

Regularization (Lasso/Ridge): Applied L1 and L2 penalties to prevent overfitting.

K-Nearest Neighbors (KNN): Used distance-based prediction with scaled features.

Tree-Based Models: Trained Random Forest and XGBoost to capture non-linear patterns without heavy preprocessing.

6. Evaluation

Metrics: Used $R^2$ Score and Mean Absolute Error (MAE) to judge performance.

Visualization: Created a scatter plot of Actual vs. Predicted Prices to visually confirm the model's accuracy (ideal predictions align on the diagonal line).

Results

Model

Test $R^2$ Score

Random Forest Regressor

0.83 (Winner)

XGBoost Regressor

0.81

KNN Regressor

0.76

Linear Regression

0.69

Conclusion

The Random Forest Regressor proved to be the most robust model, successfully capturing the complex, non-linear relationships in the real estate market. The scatter plot of Actual vs. Predicted values showed a tight cluster around the ideal prediction line, validating the model's accuracy.
