# Indian House Rent Prediction

## Overview
This project is an end-to-end machine learning workflow for predicting house rental prices in major Indian cities.  
The objective is to build and evaluate regression models that estimate monthly rent based on multiple property and location features.  

The project includes data cleaning, feature engineering, exploratory data analysis (EDA), model training, hyperparameter tuning, and performance evaluation.

---

## Dataset
The dataset contains rental listings of houses across Indian cities.  
Key features include:  
- `City`  
- `Area Type`  
- `Size`  
- `BHK`  
- `Bathroom`  
- `Furnishing Status`  
- `Tenant Preferred`  
- `Floor_number`, `Total_Floors`  
- `Posted On` (date of listing)  
- `Rent` (target variable)

---

## Data Cleaning and Feature Engineering
- **String Handling:** Used multiple approaches to clean and standardize text columns, including the `rapidfuzzy` library for fuzzy string matching.  
- **Date Feature Extraction:** Extracted the month from the `Posted On` column and analyzed seasonal effects of rent prices across months.  
- **Location Analysis:** Linked rent prices with both city and area locality to capture geographic influence.  
- **Right-Skewed Target:** Applied `log1p` transformation to the target variable (`Rent`) to handle skewness and stabilize variance.  
- **Categorical Encoding:** Converted categorical features (e.g., City, Area Type, Tenant Preferred) into numerical representations.  
- **Outlier Handling:** Removed or adjusted extreme values using the IQR method.  

---

## Exploratory Data Analysis (EDA)
- Explored rent distribution across different cities and area types.  
- Visualized how features such as BHK, Size, and Furnishing Status affect rental prices.  
- Examined seasonal patterns in rent values using extracted month feature.  

---

## Modeling Approach
Trained and evaluated multiple regression models:
- Linear Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- XGBoost Regressor  
- Support Vector Regressor (SVR)  

Hyperparameter tuning was performed using `RandomizedSearchCV` for XGBoost to optimize model performance.

---

## Results

| Model                  | RMSE     | MAE     | R²   |
|-------------------------|----------|---------|------|
| Linear Regression       | 35,025   | 13,963  | 0.52 |
| Random Forest           | 31,166   | 13,514  | 0.62 |
| Gradient Boosting       | 31,183   | 13,249  | 0.62 |
| XGBoost (default)       | 31,281   | 13,157  | 0.62 |
| SVR                     | 64,755   | 19,104  | -0.64 |
| **XGBoost (tuned)**     | **31,097** | **12,859** | **0.62** |

- **Best Model:** Tuned XGBoost Regressor  
- **95% Confidence Interval:**  
  - RMSE ∈ [26,141 – 38,160]  
  - MAE ∈ [11,253 – 14,948]  

---

## Key Insights
- Rent prices strongly vary by **city and locality**, confirming the importance of geographic features.  
- Seasonal patterns exist: rent prices fluctuate depending on the **month of listing**.  
- Feature importance analysis highlights **City, Size, and BHK** as the top predictors of rent.  
- Using `log1p` improved model performance by reducing skewness in the target variable.  

---

## Tools and Libraries
- **Python:** Pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **Preprocessing & Modeling:** Scikit-learn, XGBoost  
- **String Matching:** RapidFuzzy  
- **Environment:** Jupyter Notebook  

---

## Project Structure
Indian Houses for rent/
│── data/ # Dataset (if available)
│── notebooks/ # Jupyter notebooks with EDA & modeling
│── README.md # Project documentation


---

## Conclusion
The tuned **XGBoost Regressor** achieved the best results with an R² of 0.62, outperforming baseline models.  
The project demonstrates how proper preprocessing, feature engineering, and hyperparameter tuning can significantly improve predictive performance on real-world rental price data.