# Comprehensive Machine Learning Pipeline on Heart Disease UCI Dataset

## 1. Project Overview
This project analyzes, predicts, and visualizes heart disease risks using a full machine learning pipeline. The workflow includes data preprocessing, feature selection, dimensionality reduction (PCA), supervised and unsupervised model training, evaluation, hyperparameter tuning, and deployment. A Streamlit UI is built for interactive predictions, and the project is hosted on GitHub.

---

## 2. Objectives
- Perform data preprocessing & cleaning (handle missing values, encoding, scaling).
- Apply dimensionality reduction (PCA) to retain essential features.
- Implement feature selection using statistical and ML-based methods.
- Train supervised learning models (Logistic Regression, Decision Trees, Random Forest, SVM).
- Apply unsupervised learning (K-Means, Hierarchical Clustering) for pattern discovery.
- Optimize models using GridSearchCV and RandomizedSearchCV.
- Deploy a Streamlit UI for real-time user interaction (Bonus).
- Host the application via Ngrok and on GitHub (Bonus).

---

## 3. Tools & Libraries
- **Programming Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn, TensorFlow/Keras (optional)
- **Dimensionality Reduction & Feature Selection:** PCA, RFE, Chi-Square Test
- **Models:**
  - Supervised: Logistic Regression, Decision Tree, Random Forest, SVM
  - Unsupervised: K-Means, Hierarchical Clustering
- **Model Optimization:** GridSearchCV, RandomizedSearchCV
- **Deployment Tools:** Streamlit (Bonus), Ngrok (Bonus), GitHub

---

## 4. Project Workflow

### 4.1 Data Preprocessing & Cleaning
- Load the Heart Disease UCI dataset.
- Handle missing values.
- Encode categorical variables (One-Hot Encoding).
- Standardize numerical features.
- Conduct Exploratory Data Analysis (EDA) with histograms, correlation heatmaps, and boxplots.

**Deliverable:** Cleaned dataset ready for modeling.

### 4.2 Dimensionality Reduction - PCA
- Apply PCA to reduce feature dimensionality while retaining variance.
- Determine optimal number of components using explained variance ratio.
- Visualize PCA results with scatter plots and cumulative variance plots.

**Deliverable:** PCA-transformed dataset and variance plots.

### 4.3 Feature Selection
- Rank features using Random Forest / XGBoost importance.
- Apply Recursive Feature Elimination (RFE).
- Use Chi-Square Test to assess feature significance.
- Select the most relevant features.

**Deliverable:** Reduced dataset with key features and feature importance visualizations.

### 4.4 Supervised Learning - Classification
- Split dataset: 80% training, 20% testing.
- Train models: Logistic Regression, Decision Tree, Random Forest, SVM.
- Evaluate models using accuracy, precision, recall, F1-score, ROC curve, and AUC.

**Deliverable:** Trained models with performance metrics.

**Final Model:**  
- **Random Forest**  
- **Accuracy:** 88%  

### 4.5 Unsupervised Learning - Clustering
- Apply K-Means (determine K with elbow method).
- Apply Hierarchical Clustering (dendrogram analysis).
- Compare clusters with actual labels.

**Deliverable:** Clustering models and visualized results.

### 4.6 Hyperparameter Tuning
- Optimize model parameters using GridSearchCV & RandomizedSearchCV.
- Compare tuned models with baseline performance.

**Deliverable:** Best performing model with optimized hyperparameters.

### 4.7 Model Export & Deployment
- Save the trained model using `joblib` or `pickle`.
- Save the complete pipeline (preprocessing + model) for reproducibility.

**Deliverable:** Model exported as `.pkl` file.

---

## 5. File Structure
Heart_Disease_Project/
│── data/
│ └── heart_disease.csv
│── notebooks/
│ ├── 01_data_preprocessing.ipynb
│ ├── 02_pca_analysis.ipynb
│ ├── 03_feature_selection.ipynb
│ ├── 04_supervised_learning.ipynb
│ ├── 05_unsupervised_learning.ipynb
│ └── 06_hyperparameter_tuning.ipynb
│── models/
│ └── final_model.pkl

---

## 6. How to Use
1. Clone the repository:
```bash
git clone https://github.com/username/Heart_Disease_Project.git

2.Install required libraries:
pip install -r requirements.txt

3.Run the Jupyter notebooks for analysis and modeling.

## 7. Author
- Mohamed Magdy Fetouh Rizk
- Email :eng.mohamedmagdyrizk@gmail.com