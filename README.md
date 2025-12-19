# Mexico Real Estate Price Prediction

This project focuses on predicting real estate prices in Mexico using a dataset of property listings. The goal was to build a machine learning model that could accurately estimate property values based on features like location, size, and property type.

After extensive data cleaning, feature engineering, and model evaluation, the **Random Forest Regressor** emerged as the best-performing model with an **R² score of 0.83** on the test set.

---

## Dataset

The dataset consists of real estate listings in Mexico, including:

- **Location:** Latitude, Longitude, State, Neighborhood (extracted from `place_with_parent_names`)  
- **Property Details:** Surface Area (`surface_covered_in_m2`), Price (`price_aprox_usd`)  
- **Derived Features:** Price per square meter (`price_usd_per_m2`)

---

## Tech Stack

- **Python** – Core programming language  
- **Pandas & NumPy** – Data manipulation and cleaning  
- **Matplotlib, Seaborn & Plotly** – Exploratory Data Analysis (EDA) and visualization  
- **Scikit-Learn** – Building and evaluating machine learning models  
- **IPyWidgets** – Interactive data exploration

---

## Project Structure

### 1. Data Import & Exploration
- Loaded libraries and dataset  
- Checked data shape, data types, and null values  
- Previewed the dataset with `.head()`

### 2. Data Cleaning
- Filtered dataset to **Houses** for consistent pricing  
- Imputed missing numerical values with the median  
- Cleaned location data to extract **State** and **Neighborhood**  
- Removed outliers by filtering the top and bottom 5% of `price_usd_per_m2`

### 3. Exploratory Data Analysis (EDA)
- Visualized price distributions  
- Examined correlation between Surface Area and Price  
- Plotted property locations using Latitude and Longitude

### 4. Feature Engineering
- Applied **One-Hot Encoding** to categorical features like State  
- Dropped high-cardinality columns (Neighborhood) and leakage features (`price_usd_per_m2`)  

### 5. Model Building
Tested multiple regression algorithms:  
- **Linear Regression** – Baseline performance  
- **Polynomial Regression** – Captured non-linear trends  
- **Lasso/Ridge** – Regularization to prevent overfitting  
- **K-Nearest Neighbors (KNN)** – Distance-based prediction  
- **Tree-Based Models:** Random Forest and XGBoost for non-linear relationships  

### 6. Evaluation
- Metrics: **R² Score** and **Mean Absolute Error (MAE)**  
- Visualized **Actual vs. Predicted Prices** for validation

---

## Results

| Model                     | Test R² Score |
|----------------------------|---------------|
| Random Forest Regressor    | 0.83 ✅       |
| XGBoost Regressor          | 0.81          |
| KNN Regressor              | 0.76          |
| Linear Regression          | 0.69          |

---

## Conclusion

The **Random Forest Regressor** proved to be the most robust model, effectively capturing complex, non-linear relationships in the real estate market.  
The scatter plot of Actual vs. Predicted prices showed a tight cluster around the diagonal, confirming the model’s accuracy.


