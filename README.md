# 🏡 Predicting California Housing Values

A simple linear regression project exploring the **California Housing dataset**, focusing on the relationship between **median income** and **median house value**. This notebook includes data cleaning, visualization, correlation analysis, and modeling using scikit-learn.

[📓 View the Colab Notebook](https://colab.research.google.com/drive/1lQV4eJCumBZcHIfHtGS_f24jL_oMH5Q-)

---

## 📌 Project Objective

- Predict **`median_house_value`** using features in the dataset, especially **`median_income`**.
- Handle missing data using **k-Nearest Neighbors (kNN)** imputation.
- Explore data distributions and relationships via **EDA** and **correlation analysis**.
- Build a **simple linear regression model** and interpret its results.

---

## 📊 Dataset

- Source: [California Housing Data (Kaggle)](https://www.kaggle.com/datasets/camnugent/california-housing-prices)  
- Format: CSV (loaded via a Google Sheets link)
- Features include:
  - `longitude`, `latitude`
  - `housing_median_age`, `total_rooms`, `total_bedrooms`, `population`, `households`
  - `median_income`, `median_house_value` (target)

---

## 🛠 Workflow Overview

### 🔹 1. Data Loading & Inspection
- Loaded from Google Sheets into a Pandas DataFrame.
- Checked data types, shape, and missing values.

### 🔹 2. Missing Value Handling
- Used **k-Nearest Neighbors Regression** to impute missing numerical values.
- Created a reusable `impute_knn()` function to clean data.

### 🔹 3. Exploratory Data Analysis (EDA)
- Histograms to visualize distributions and spot skewness/outliers.
- Observed notable outliers in:
  - `housing_median_age`
  - `median_house_value`
- Many features showed skewed distributions, requiring transformation consideration.

### 🔹 4. Correlation Analysis
- Used both **Pearson** and **Spearman** methods.
- Found strong positive correlation between:
  - `median_income` and `median_house_value` (ρ ≈ 0.69)

### 🔹 5. Chi-Squared Test
- Binned income and house value into categories.
- Ran Chi-squared test to statistically assess their relationship.
- **Result:** Statistically significant association found between income level and house value.

### 🔹 6. Linear Regression Modeling
- Modeled: `median_house_value = β * median_income + intercept`
- Coefficient: `41,793.85`
- Intercept: `45,085.58`
- **Interpretation**: Every unit increase in median income is associated with a ~$41,794 increase in predicted house value.

---

## 🔍 Key Findings

- **Median income** is a strong and practical predictor of **median house value**.
- Dataset has manageable missing values and outliers.
- Even simple models like linear regression can provide meaningful insights when relationships are strong and linear.

---

## 📁 File Structure

```bash
📦 california-housing-prediction/
 ┣ 📜 README.md
 ┣ 📜 california_housing_prediction.ipynb
