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
|---|---:|---:|---:|
| Random Forest Regressor | **20.407** | **40.282** | **0.911** |
| Gradient Boosting Regressor | 23.159 | 43.194 | 0.898 |
| Decision Tree Regressor | 24.443 | 50.366 | 0.861 |
| Linear Regression | 29.978 | 56.704 | 0.824 |
| Support Vector Regressor | 25.397 | 63.647 | 0.779 |

**Best regression model: Random Forest Regressor**

The model achieved an R² score of 0.911, with an MAE of approximately 20.41 AQI points and an RMSE of approximately 40.28 AQI points on the test set.

### Classification Results

| Model | Accuracy ↑ | Macro Precision ↑ | Macro Recall ↑ | Macro F1 ↑ |
|---|---:|---:|---:|---:|
| Random Forest Classifier | **81.2%** | **0.802** | 0.776 | **0.788** |
| Gradient Boosting Classifier | 81.0% | 0.798 | 0.770 | 0.783 |
| Support Vector Classifier | 75.8% | 0.716 | **0.791** | 0.739 |
| Decision Tree Classifier | 75.8% | 0.715 | 0.754 | 0.731 |
| Logistic Regression | 72.6% | 0.691 | 0.762 | 0.709 |

**Best overall classification model: Random Forest Classifier**

It achieved 81.2% accuracy and a macro F1-score of 0.788 on the test set.

*Results reflect the current experimental setup and may vary with different data splits, preprocessing choices, or hyperparameters.*

## 🔍 Key Findings

- Random Forest Regressor performed best among the five evaluated regression models.
- Random Forest Classifier achieved the highest classification accuracy and macro F1-score among the five classification models.
- PM2.5 was the most important feature in the Random Forest feature-importance plots for both tasks.
- PM10 showed the strongest individual correlation with AQI in the correlation analysis.
- The classification confusion matrix indicated that the Poor AQI category had lower recall than several other categories, highlighting an opportunity for improvement.

Correlation and model feature importance measure different things; neither should be interpreted as proof of causation.

## 🚀 How to Run the Project

### Option 1: Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload or open the project notebook.
3. Upload the `city_day.csv` dataset when prompted.
4. Run the notebook cells sequentially.
5. Review the EDA visualizations, trained models, evaluation metrics, and comparison tables.

### Option 2: Run Locally

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Install the dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open the project notebook, ensure the dataset is available at the expected path, and execute the cells in order.

## 📁 Suggested Repository Structure

```text
AQI-Prediction-ML/
├── AQI_Prediction_ML_Project.ipynb
├── README.md
├── requirements.txt
└── data/
    └── city_day.csv
```

The dataset is not required to be committed to GitHub. If it is large or subject to redistribution restrictions, keep it out of the repository and provide the original Kaggle source instead.

## ⚠️ Limitations

- Missing pollutant measurements can affect the quality of model predictions.
- Random train-test splitting does not establish performance on future dates or unseen cities.
- Classification errors remain, particularly for the Poor AQI category.
- The current models estimate AQI from pollutant measurements in the same observation; they do not directly forecast future AQI.
- Feature importance indicates predictive relevance rather than causal impact.

## 🔮 Future Improvements

- Perform chronological validation to evaluate generalization to future observations.
- Tune hyperparameters using cross-validation.
- Investigate class imbalance and improve minority-category recall.
- Apply permutation importance and other explainability techniques.
- Develop a time-series forecasting model for future AQI prediction.
- Build an interactive dashboard for exploring AQI estimates and air-quality categories.

## 🏁 Conclusion

This project demonstrates the application of machine learning to air-quality analysis through numerical AQI estimation and categorical AQI prediction. Comparative evaluation identified Random Forest Regressor as the strongest regression model and Random Forest Classifier as the strongest classification model in the current experiments.

The findings highlight the value of pollutant measurements for estimating air quality while identifying opportunities for improved generalization, classification performance, and future AQI forecasting.

## 👨‍💻 Author

**Apoorwa Kumar**

B.Tech — Computer Science and Engineering

GitHub: [@apoorwa46](https://github.com/apoorwa46)

---

*Developed as a machine learning project focused on air-quality analysis and prediction using historical data from Indian cities.*
