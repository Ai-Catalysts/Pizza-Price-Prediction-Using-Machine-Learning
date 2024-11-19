# **Pizza Price Prediction Using Machine Learning**

## **Objective**
Predict pizza prices based on features such as toppings, diameter, variant, size, and extras using machine learning techniques.

## **Project Workflow**

### **1. Data Loading and Exploration**
- Imported necessary libraries: `pandas`, `numpy`, `matplotlib`, and `seaborn`.
- Loaded the dataset using `read_csv`.
- Displayed the first and last 5 rows using `.head()` and `.tail()`.
- Determined dataset shape with `.shape` and column information with `.info()`.

### **2. Null Value Check**
- Checked for missing values using `.isnull().sum()`.
- **Outcome**: No null values were found.

### **3. Descriptive Statistics**
- Summarized numerical columns using `.describe()` to extract counts, means, and ranges.

### **4. Data Preprocessing**
- **Price Column**:
  - Removed currency symbols (`RP`) and commas.
  - Converted data type from `object` to `int`.
  - Transformed prices from Indonesian Rupiah to Indian Rupees.
- **Diameter Column**:
  - Removed text (`each`) and whitespace.
  - Converted data type from `object` to `float`.
- Encoded categorical columns (e.g., `variant`, `size`, `extras`) using `LabelEncoder`.

### **5. Data Analysis**
#### **Univariate Analysis**
- Used `.value_counts()` for column exploration.
- Visualized data with `matplotlib` and `seaborn`:
  - Histogram: Price distribution (right-skewed).
  - Count plots: Popular toppings, variants, and sizes.
- **Insights**:
  - Popular toppings: Chicken, mushrooms, smoked beef, mozzarella.
  - Most common variant: Classic.
  - Most common size: Medium.

## **Machine Learning Workflow**

### **1. Feature and Target Separation**
- **Independent Variables (`X`)**: All features except the target column (`price`).
- **Dependent Variable (`y`)**: Target column (`price`).

### **2. Train-Test Split**
- Split data using `train_test_split`:
  - 80% training set, 20% test set.
  - `random_state=242` ensures reproducibility.

### **3. Model Selection**
Trained multiple regression models to predict prices:
1. **Linear Regression**
2. **Support Vector Regressor (SVR)**
3. **Random Forest Regressor**
4. **Gradient Boosting Regressor**
5. **XGBoost Regressor**

### **4. Model Evaluation**
- Used the **R-squared score** (`r2_score`) for evaluation:
  - Assessed performance on the test set.
  - Compared results across models.
- **Best Model**: XGBoost Regressor (highest R-squared score).

### **5. Feature Importance**
- Analyzed features contributing to predictions using `.feature_importances_` for tree-based models:
  - Visualized feature importance using horizontal bar plots.

### **6. Save the Best Model**
- Retrained the XGBoost Regressor on the full dataset for production use.
- Saved the trained model using `joblib` for future predictions.

---

## **Visualization**
1. **Price Distribution**: Histogram showing a right-skewed distribution.  
2. **Categorical Analysis**: Count plots for toppings, variants, and sizes.  
3. **Model Performance**: Bar plot comparing R-squared scores.  
4. **Feature Importance**: Horizontal bar plot highlighting top contributing features.

---

## **Key Learnings**
- **Preprocessing**: Transforming data for analysis and model training.  
- **EDA**: Deriving actionable insights through visualization.  
- **Model Training**: Testing multiple regression models for accuracy.  
- **Feature Engineering**: Identifying impactful features using feature importance.

---

## **Future Scope**
1. Extend to multiclass classification for pizza categories.
2. Integrate more real-world features (e.g., restaurant location, customer ratings).
3. Implement deployment strategies for real-time pricing prediction.
