# 🏦 Delinquency Prediction: Data Cleaning & Missing Value Treatment using Python

## 📌 Project Overview

This project prepares a customer credit dataset for delinquency prediction by inspecting it, identifying missing values, and applying a different treatment to each affected column.

The analysis uses **Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn** to document missing data, justify each handling method, impute values, visualize the result, and export a cleaned dataset.

The dataset contains **500 customer records and 19 columns**. After cleaning, **498 records** remain and no column has missing values.

## 🎯 Objectives

The main objectives of this project are to:

- Inspect the dataset structure and identify missing values
- Document each missing data issue along with a handling method and justification
- Apply a suitable treatment for each affected column
- Compare the income distribution before and after imputation
- Verify that no missing values remain
- Export a cleaned dataset ready for modeling

## 🗂️ Dataset

The dataset contains the following columns:

| Column | Description |
|---|---|
| `Customer_ID` | Unique customer identifier |
| `Age` | Customer age |
| `Income` | Customer income |
| `Credit_Score` | Customer credit score |
| `Credit_Utilization` | Share of available credit in use |
| `Missed_Payments` | Number of missed payments |
| `Delinquent_Account` | Delinquency indicator (target variable) |
| `Loan_Balance` | Outstanding loan balance |
| `Debt_to_Income_Ratio` | Debt relative to income |
| `Employment_Status` | Customer employment status |
| `Account_Tenure` | Length of the customer's account relationship |
| `Credit_Card_Type` | Type of credit card held |
| `Location` | Customer location |
| `Month_1` to `Month_6` | Six monthly records per customer |

### Dataset Size

- Initial records: **500**
- Initial columns: **19**
- Records after cleaning: **498**
- Missing values after cleaning: **None**

### Missing Data Summary

| Feature | Missing Count | % Missing | Handling Method |
|---|---|---|---|
| `Income` | 39 | 7.8% | Iterative imputation with a Random Forest estimator |
| `Loan_Balance` | 29 | 5.8% | Median imputation within Debt-to-Income quintiles |
| `Credit_Score` | 2 | 0.4% | Dropped rows (very few missing) |

## 🧹 Data Cleaning

The following cleaning steps were performed:

1. Loaded the dataset using Pandas.
2. Inspected data types and non-null counts using `info()`.
3. Counted missing values per column using `isnull().sum()`.
4. Built a table documenting each missing data issue, handling method, and justification.
5. Dropped the 2 rows with missing `Credit_Score`.
6. Imputed missing `Loan_Balance` values using the median of each Debt-to-Income quintile, created with `pd.qcut`.
7. Imputed missing `Income` values using `IterativeImputer` with a `RandomForestRegressor`, using age, credit score, utilization, missed payments, account tenure, employment status, loan balance, and debt-to-income ratio as predictors.
8. Confirmed that no missing values remain.
9. Exported the result to `Delinquency_prediction_cleaned.csv`.

## 🔎 Approach

- **Credit score**: Rows were dropped because so few were affected that the impact is minimal.
- **Loan balance**: Loan balance relates to the debt-to-income ratio, so customers were grouped into five Debt-to-Income bins and gaps were filled with the bin median. Medians help preserve the distribution shape.
- **Income**: Income is an important feature for prediction, so rows were preserved and values were estimated from the other customer attributes.
- **Categorical handling**: Categorical variables were one-hot encoded with `pd.get_dummies` before imputation.

## 🛠️ Technologies Used

- **Python**
- **Pandas** - data loading, inspection, grouping and binning
- **NumPy** - numerical operations
- **Matplotlib** - data visualization
- **Seaborn** - distribution plots
- **Scikit-learn** - `IterativeImputer` and `RandomForestRegressor`
- **Jupyter Notebook** - analysis environment

## 📊 Visualizations

The notebook includes a three-panel figure with histograms and KDE curves for:

- Original income distribution (non-missing values only)
- Income distribution after imputation
- Loan balance distribution after imputation

## 📁 Project Structure

```
Delinquency-Data-Cleaning
│
├── Tata.ipynb
├── Delinquency_prediction_dataset.csv
├── Delinquency_prediction_cleaned.csv
└── README.md
```

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/SSoumyaDas/Data-Analytics-Projects.git
cd Data-Analytics-Projects
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Add the dataset

Place `Delinquency_prediction_dataset.csv` in the same folder as the notebook.

### 4. Open the notebook

```bash
jupyter notebook Tata.ipynb
```

## 💡 Key Takeaways

- The raw dataset has 500 customer records and 19 columns.
- Three columns had missing values: `Income` (39), `Loan_Balance` (29), and `Credit_Score` (2).
- Each column received a different treatment based on how many values were missing and how important the feature is.
- Dropping 2 rows for `Credit_Score` leaves 498 records.
- After cleaning, every column is complete and the data is saved for downstream modeling.

## 🚀 Possible Improvements

This project can be improved further by:

- Verifying the income imputation. The final output shows `Income` values such as 0.0 and 1.0, so the imputed column should be checked against the encoded feature matrix.
- Comparing imputation methods (median, KNN, iterative) for `Income`.
- Adding outlier detection and treatment.
- Performing exploratory analysis of delinquency against the other features.
- Building a delinquency prediction model on the cleaned data.
- Building an interactive dashboard using Power BI.

## 📌 Note

This project focuses on **data cleaning and preparation**. It does not include a predictive model, and the imputed values are estimates rather than observed data.

## 👤 Author

**Shruti**

This project was created as part of a Python/Data Analytics portfolio to demonstrate skills in data cleaning, missing value treatment, imputation, and data preparation.
