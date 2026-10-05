Paste this directly into your GitHub **README.md**:

```markdown
# Global Health Risk Analysis & Prediction System

A Machine Learning project focused on analyzing global health statistics and preparing a clean, meaningful, and model-ready dataset for predictive modeling.

## Sprint 1 – Data Understanding & Preprocessing

### Objective

Convert raw global health data into a clean and model-ready dataset through data inspection, cleaning, exploratory data analysis, outlier detection, feature encoding, feature scaling, and train-test splitting.

### Dataset

- **Rows:** 1,000,000
- **Columns:** 22
- **Target Variable:** `Prevalence Rate (%)`
- **Numerical Features:** 14
- **Categorical Features:** 7
- **Missing Values:** 0
- **Duplicate Records:** 0

The dataset contains information related to countries, diseases, healthcare access, treatment, mortality, recovery, population, income, education, and urbanization.

The original dataset is not included in this repository due to its large size.

## Sprint 1 Workflow

1. Data Collection & Loading
2. Initial Data Inspection
3. Data Cleaning
4. Exploratory Data Analysis (EDA)
5. Outlier Detection & Treatment
6. Train-Test Split
7. Feature Encoding
8. Feature Scaling
9. ColumnTransformer Preprocessing

## Data Analysis

### Univariate Analysis

Used histograms and bar charts to understand individual feature distributions and category frequencies.

### Bivariate Analysis

Analyzed relationships between features and the target variable using scatter plots, correlation analysis, and box plots.

### Multivariate Analysis

Used multiple-variable visualizations to identify patterns and relationships within the dataset.

### Outlier Detection

Outliers were detected using the Interquartile Range (IQR) method with a `1.5 × IQR` threshold.

**Result:** No statistical outliers were detected across the numerical features, so no outlier treatment was required.

## Feature Preprocessing

### Categorical Features

The dataset contains mostly nominal categorical variables, with `Age Group` being ordinal.

Categorical features were encoded using:

```python
OneHotEncoder(handle_unknown="ignore")
```

- Categorical columns: **7**
- Encoded features: **64**

### Numerical Features

Numerical features were standardized using:

```python
StandardScaler()
```

- Numerical columns: **14**

The scaler was fitted only on the training data to prevent data leakage.

## Train-Test Split

The dataset was divided using an **80:20 ratio**:

- Training data: **800,000 records**
- Testing data: **200,000 records**

## ColumnTransformer

`ColumnTransformer` was used to apply different preprocessing techniques to categorical and numerical features.

```text
Categorical Features
        ↓
OneHotEncoder
        ↓
64 Features

Numerical Features
        ↓
StandardScaler
        ↓
14 Features

        ↓
78 Total Features
```

Final transformed data:

```text
X_train_transformed: (800000, 78)
X_test_transformed:  (200000, 78)
```

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Joblib
- Jupyter Notebook
- Google Colab

## Repository Structure

```text
Global-Health-Risk-Analysis/
│
├── README.md
│
├── notebooks/
│   └── Sprint_1_Data_Understanding_Preprocessing.ipynb
│
├── data/
│   └── README.md
│
├── preprocessing/
│   └── preprocessor.pkl
│
├── outputs/
│   └── Sprint_1_Metrics.csv
│
└── requirements.txt
```

## Sprint 1 Deliverables

- Clean dataset validation
- EDA visualizations and insights
- Outlier analysis
- Train-test split
- One-Hot Encoding
- Standard Scaling
- ColumnTransformer
- Preprocessing documentation
- Sprint 1 metrics

## Current Status

**Sprint 1 – Completed ✅**

The raw dataset has been successfully inspected, validated, analyzed, preprocessed, and transformed into a model-ready format.

Model training and evaluation will be implemented in the subsequent stages of the project.

## Author

**Sree Dharma**

B.Tech – Computer Science & Engineering (AI & Machine Learning)

SRM Institute of Science and Technology
```
