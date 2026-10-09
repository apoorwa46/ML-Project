# 🌍 AQI Prediction Using Machine Learning

**Air Quality Index (AQI) Estimation and Classification for Indian Cities**

A machine learning project that analyzes air pollution data from Indian cities to estimate numerical AQI values and classify air quality into predefined categories. The project combines Exploratory Data Analysis (EDA), feature-importance analysis, regression, classification, and comparative model evaluation.

---

## 📌 Project Overview

Air pollution is a major environmental concern that affects public health and quality of life. Monitoring air quality and understanding pollutant patterns can help identify pollution trends and support environmental analysis.

This project uses historical air-quality data from Indian cities to:

- Analyze pollutant distributions and AQI patterns.
- Investigate correlations between pollutants and AQI.
- Estimate numerical AQI values using regression algorithms.
- Classify air quality into categories using classification algorithms.
- Compare model performance using appropriate evaluation metrics.
- Identify important predictive features using feature-importance analysis.

## 🎯 Objectives

1. **Exploratory Data Analysis:** Understand the distribution, trends, and quality of air-pollution data.
2. **Correlation Analysis:** Examine relationships between pollutants and AQI.
3. **AQI Estimation:** Develop and evaluate machine learning regression models.
4. **AQI Classification:** Predict air-quality categories using classification algorithms.
5. **Performance Comparison:** Identify the best-performing models based on test-set metrics.

## 📊 Dataset

The project uses the `city_day.csv` dataset obtained from Kaggle, containing daily air-quality observations for Indian cities.

**Dataset shape:** 29,531 rows × 16 columns.

### Features

| Feature | Description |
|---|---|
| `City` | Name of the city |
| `Date` | Date of observation |
| `PM2.5` | Fine particulate matter concentration |
| `PM10` | Coarse particulate matter concentration |
| `NO` | Nitric oxide measurement |
| `NO2` | Nitrogen dioxide measurement |
| `NOx` | Nitrogen oxides measurement |
| `NH3` | Ammonia measurement |
| `CO` | Carbon monoxide measurement |
| `SO2` | Sulfur dioxide measurement |
| `O3` | Ozone measurement |
| `Benzene` | Benzene measurement |
| `Toluene` | Toluene measurement |
| `Xylene` | Xylene measurement |
| `AQI` | Numerical Air Quality Index |
| `AQI_Bucket` | Categorical air-quality label |

*Note: Pollutant columns may contain missing values, which are handled during preprocessing.*

## 🛠️ Technology Stack

- **Language:** Python
- **Environment:** Google Colab / Jupyter Notebook
- **Data Processing:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn

## ⚙️ Project Workflow

### 1. Data Loading and Familiarization
- Load the dataset and inspect its structure.
- Examine data types, statistical summaries, missing values, and duplicate records.

### 2. Data Preprocessing
- Handle missing values using median imputation for numerical features and suitable imputation for categorical features.
- Extract year, month, and day from the date.
- Encode categorical variables such as city.
- Separate input features from target variables.
- Split the data into training and testing sets.

### 3. Exploratory Data Analysis
- Analyze AQI distributions.
- Compare average AQI across cities.
- Visualize pollutant correlations using heatmaps.
- Investigate the relationships between individual pollutants and AQI.

### 4. Regression Modeling
The regression task predicts the numerical `AQI` value using pollutant measurements and contextual features.

Algorithms evaluated:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- Support Vector Regressor (SVR)

**Evaluation metrics:** Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score.

### 5. Classification Modeling
The classification task predicts the `AQI_Bucket` category.

Algorithms evaluated:

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier
- Support Vector Classifier (SVC)

**Evaluation metrics:** Accuracy, macro precision, macro recall, macro F1-score, and confusion matrix.

### 6. Feature-Importance Analysis
- Examine Random Forest feature importance for both regression and classification.
- Compare predictive contributions from different pollutants.
- Use permutation importance to further investigate feature relevance.

## 📈 Model Performance

### Regression Results

| Model | MAE ↓ | RMSE ↓ | R² ↑ |
|---|---:|---
