# Big Mart Sales Prediction

A machine learning project for predicting item outlet sales using historical Big Mart sales data.

## Project Overview

This project focuses on predicting the sales of products across different Big Mart outlets.

The workflow covers data exploration, missing-value handling, feature preprocessing, model training, prediction, and evaluation using an XGBoost regression model.

## Dataset

The dataset contains information about products and outlets, including:

- Item Identifier
- Item Weight
- Item Fat Content
- Item Visibility
- Item Type
- Item MRP
- Outlet Identifier
- Outlet Establishment Year
- Outlet Size
- Outlet Location Type
- Outlet Type
- Item Outlet Sales

The training dataset used in this project is `Train.csv`.

## Workflow

### 1. Data Collection and Exploration

- Loaded the dataset using Pandas.
- Examined the dataset shape and structure.
- Checked for missing values.
- Reviewed statistical information.
- Explored numerical and categorical features using visualizations.

### 2. Missing Value Handling

Missing values were handled using:

- Mean imputation for `Item_Weight`.
- Mode-based imputation for `Outlet_Size`, using `Outlet_Type` to determine the appropriate outlet size.

### 3. Data Preprocessing

The `Item_Fat_Content` values were standardized:

- `low fat` -> `Low Fat`
- `LF` -> `Low Fat`
- `reg` -> `Regular`

Categorical features were then converted into numerical values using `LabelEncoder`.

### 4. Feature and Target Separation

The target variable was:

`Item_Outlet_Sales`

The remaining columns were used as input features.

### 5. Train-Test Split

The dataset was divided into:

- 80% training data
- 20% testing data

A `random_state` of 2 was used for reproducibility.

### 6. Model Training

An XGBoost Regressor was trained on the processed training data.

### 7. Prediction and Evaluation

Predictions were generated for the test dataset.

The model was evaluated using the R-squared (R2) score on the test data.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

## Project Structure

```text
02-BIG MART SALES PREDICTION PROJECT/
│
├── data/
│   └── raw/
│       ├── Train.csv
│       └── Test.csv
│
├── notebooks/
│   └── analysis.ipynb
│
├── .gitignore
└── README.md