# 💼 SF Salaries Analysis using Python

## 📌 Project Overview

This project performs an exploratory data analysis (EDA) on San Francisco city employee compensation data to understand pay patterns across employees, job titles, and years.

The analysis uses **Pandas** to load the dataset, filter records, aggregate values, group data by year, and answer a series of targeted questions about salaries and job titles.

The dataset contains **148,654 employee records and 13 columns**, covering compensation details such as base pay, overtime pay, benefits, and total pay for the years **2011 to 2014**.

## 🎯 Objectives

The main objectives of this project are to:

- Analyze the San Francisco employee salary dataset
- Explore base pay, overtime pay, and total compensation
- Identify the highest and lowest paid employees
- Examine how average base pay changes across years
- Analyze job title frequency and uniqueness
- Test whether job title length is related to pay
- Generate meaningful insights from the analysis

## 🗂️ Dataset

The dataset contains the following columns:

| Column | Description |
|---|---|
| `Id` | Unique record identifier |
| `EmployeeName` | Name of the employee |
| `JobTitle` | Job title of the employee |
| `BasePay` | Base salary |
| `OvertimePay` | Overtime pay |
| `OtherPay` | Other pay, such as additional payments or adjustments |
| `Benefits` | Value of employee benefits |
| `TotalPay` | Base pay + overtime pay + other pay |
| `TotalPayBenefits` | Total pay including benefits |
| `Year` | Year of the record |
| `Notes` | Additional notes |
| `Agency` | Employing agency |
| `Status` | Employment status |

### Dataset Size

- Records: **148,654**
- Columns: **13**
- Years covered: **2011 to 2014**
- Unique job titles: **2,159**
- Missing values: present in columns such as `Benefits`, `Notes`, and `Status`

## 🧹 Data Inspection

The following loading and inspection steps were performed:

1. Loaded the dataset using Pandas.
2. Previewed the first rows using `head()`.
3. Inspected the structure of the data using `info`.
4. Inspected extreme values such as the highest overtime pay and the lowest total pay.
5. Created a new `title_len` column from the length of each job title.

## 🔎 Exploratory Data Analysis

- **Average base pay**: Calculated the mean base pay across all records.
- **Overtime pay**: Found the highest overtime pay in the dataset.
- **Individual lookup**: Retrieved the job title and total pay for a specific employee.
- **Highest and lowest earners**: Identified the employees with the maximum and minimum total pay including benefits.
- **Yearly trend**: Compared average base pay across 2011 to 2014 using `groupby`.
- **Job title analysis**: Counted unique titles, found the most common titles, and counted titles held by only one person in 2013.
- **Keyword search**: Counted records with "chief" in the job title using a custom function and `apply()`.
- **Correlation**: Checked the relationship between job title length and total pay with `corr()`.

## 🛠️ Technologies Used

- **Python**
- **Pandas** - data loading, filtering, grouping, aggregation and correlation
- **Jupyter Notebook** - analysis environment

## 📁 Project Structure

```
SF-Salaries-Analysis
│
├── SF_Salaries.ipynb
├── Salaries.csv
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
pip install pandas jupyter
```

### 3. Add the dataset

Place `Salaries.csv` in the same folder as the notebook.

### 4. Open the notebook

```bash
jupyter notebook SF_Salaries.ipynb
```

## 💡 Key Takeaways

- The dataset contains 148,654 employee records across 2011 to 2014.
- The average base pay is about **$66,325**.
- The highest overtime pay recorded is **$245,131.88**.
- The highest total pay including benefits belongs to **Nathaniel Ford**, General Manager of the Metropolitan Transit Authority, at **$567,595.43**.
- The lowest total pay is **-$618.13**, a negative value that likely reflects an adjustment or correction in the source data.
- Joseph Driscoll, Captain of Fire Suppression, has total pay including benefits of **$270,324.91**.
- Average base pay by year: **2011** $63,596, **2012** $65,436, **2013** $69,630, **2014** $66,564.
- There are **2,159** unique job titles. The most common are Transit Operator, Special Nurse, Registered Nurse, Public Svc Aide-Public Works, and Police Officer 3.
- **202** job titles were held by only one person in 2013.
- **627** records contain "chief" in the job title.
- Job title length shows almost no correlation with total pay (about **-0.04**).

## 🚀 Possible Improvements

This project can be improved further by:

- Handling missing values and placeholder entries such as "Not provided".
- Standardizing job title capitalization before counting titles.
- Investigating negative pay values.
- Adding visualizations with Matplotlib or Seaborn.
- Analyzing overtime pay and benefits by job title or department.
- Building an interactive dashboard using Power BI.

## 📌 Note

This project is an **exploratory data analysis project**. The findings describe patterns present in the provided dataset and should not be interpreted as current salary information for San Francisco city employees.

## 👤 Author

**Shruti**

This project was created as part of a Python/Data Analytics portfolio to demonstrate skills in data loading, filtering, aggregation, grouping, and interpretation.
