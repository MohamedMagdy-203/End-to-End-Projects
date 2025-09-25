# 🛒 Brazilian Marketplace Cost Prediction

## 📌 Overview
This project is an **end-to-end machine learning workflow** for predicting the **cost of retail transactions** in the Brazilian e-commerce marketplace.  

The goal is to clean and preprocess messy, inconsistent datasets, perform **feature engineering**, and build a robust ML pipeline that can accurately predict the **order cost**.  
The project also includes exploratory analysis and a final submission file for predictions.

---

## 📊 Dataset
The dataset comes from the **Brazilian Marketplace Orders Dataset** with more than **40,000 customer orders**.  
It contains multiple noisy sources with missing and inconsistent values.  

### Key Data Components:
- **Customer & Order Information**: Person description, yearly income, order details, review scores.  
- **Product & Packaging**: Gross weight, net weight, package weight, recyclability indicators.  
- **Store Data**: Store type, sales, cost, and area breakdown (grocery, frozen, meat).  
- **Promotions & Market**: Promotion names and marketing features.  
- **Geographical Data**: Customer & seller location (city, state, latitude, longitude).  

**🎯 Target Variable:** `Cost` → representing the total cost of each order.  

---

## 🧹 Data Cleaning & Feature Engineering
We implemented robust preprocessing to handle **13+ major data quality issues**:  

| Problem Area             | Issue Example                                | Solution |
|--------------------------|-----------------------------------------------|----------|
| Column Names             | Inconsistent, typos, spaces                  | Standardized names with mapping dictionary |
| Person Description       | Free text mixing marital, gender, children   | Extracted structured features (`marital_status`, `gender`, `children_number`, etc.) |
| Yearly Income            | Mixed formats (“$400 monthly”, “5k”)         | Converted to clean yearly numeric values |
| Customer Order           | Raw text                                     | Parsed into `Product Type`, `Department`, `Brand` |
| Product Weights          | Missing/inconsistent gross/net/package       | Standardized in **kg** and recalculated missing |
| Recyclability Field      | Nil, unknown, yes/no                         | Normalized into {Yes, No, Unknown} |
| Promotion Name           | “nil”, “missing”, “tbd”                      | Cleaned and standardized |
| Store Kind               | Noisy free text                              | Standardized with fuzzy matching |
| Sales & Cost             | Text (“1.2 million”, “not available”)        | Converted to numeric |
| Store Areas              | Missing/invalid grocery/frozen/meat areas    | Imputed with formulas and ratios |
| Location Data            | Extra text in city/state fields              | Cleaned + standardized |
| Review Score             | Mixed scales (%, 1–10, fractions)            | Normalized to a 1–5 scale |
| Cost                     | Free text                                    | Cleaned + numeric |

### 🔧 Feature Engineering
We engineered powerful new features via a custom `FeatureEngineering` class:
- **Business Metrics**: `Store Profit`, `Profit Margin`  
- **Ratios**: Grocery Ratio, Frozen Ratio, Meat Ratio  
- **Interaction Terms**: Income × Store Sales  
- **Geospatial Feature**: Customer–Seller Distance (via Haversine formula)  

---

## 🔎 Exploratory Data Analysis (EDA)
- Distribution of **store sales, profit, and costs**.  
- Correlation between **customer income, distance, and profit margin**.  
- Impact of **review scores** and **delivery metrics** on satisfaction.  
- Geographic breakdown of sales across Brazilian regions.  

---

## 🤖 Modeling Approach
We experimented with multiple ML models to identify the best performer.  

### 🏗️ Preprocessing Pipelines
- Built modular **Scikit-learn Pipelines** to handle diverse feature types (numerical, categorical, binary, multi-label).  
- Automated the workflow → consistent, reproducible, maintainable.  

### 🧠 Final Model
We selected **LightGBM Regressor** as the final model due to its:  
- Speed and scalability.  
- Strong performance on tabular data.  
- Ability to handle categorical & numerical features efficiently.  

### Training Strategy
- Log-transformed target variable (`Cost`) to reduce skewness.  
- Used **early stopping** to prevent overfitting.  
- Hyperparameter tuning with **Optuna** + **K-Fold CV**.  

---

## 📈 Results

| Model                | RMSE   |
|-----------------------|--------|
| LightGBM (baseline)   | 221.97 |
| LightGBM (tuned)      | 210.49 |

✅ **Best Model**: Tuned **LightGBM Regressor**  
📌 Achieved RMSE ≈ **210.49**, showing strong predictive accuracy on unseen data.  

---

## 📑 Project Deliverables
- 📓 **Notebook**: [Brazilian marketplace notebook.ipynb](Brazilian%20marketplace%20notebook.ipynb)  
- 📊 **Dashboard Preview**: ![Dashboard](Brazilian%20marketplace%20summarize.png)  
- 📄 **Presentation**: [Brazilian marketplace presentation.pdf](Brazilian%20marketplace%20presentation.pdf)  

---

## 📂 Project Structure
End-to-End-Projects/
│── Brazilian marketplace/
│ ├── Train/ # Training dataset
│ ├── Test/ # Test dataset
│ ├── Brazilian marketplace notebook.ipynb # EDA + modeling notebook
│ ├── Brazilian marketplace dashboard.pbix # Power BI Dashboard
│ ├── Brazilian marketplace presentation.pdf # Final project presentation
│ └── Brazilian marketplace summarize.png # Dashboard snapshot


---

## ✨ Key Insights
- **Distance** between customer & seller strongly impacts **delivery cost**.  
- **Review scores** are highly linked to delivery performance.  
- **Profit margins** vary widely by store type & product category.  
- **Feature engineering** significantly boosted model performance.  

---

## 🛠️ Tools & Technologies
- **Python**: Pandas, NumPy, Scikit-learn, LightGBM, Optuna  
- **Visualization**: Matplotlib, Seaborn, Power BI  
- **Version Control**: Git, GitHub  
- **Environment**: Jupyter Notebook  

---

👨‍💻 **Author**: Mohamed Magdy  
🔗 GitHub: [MohamedMagdy-203](https://github.com/MohamedMagdy-203)  