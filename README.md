# 🏠 House Price Prediction and Analysis Using Machine Learning

**IBM SkillsBuild – Data Analytics with AI Academic Internship Project**

**Student Name:** Haveesh Chowdary Kante
**Institution:** Amrita Vishwa Vidyapeetham, Coimbatore

---

## 📌 Project Overview

This project builds an end-to-end machine learning pipeline to predict residential property prices in India. It covers data loading, cleaning, exploratory data analysis, feature engineering, model training, and evaluation using four regression algorithms.

---

## ❓ Problem Statement

House prices in India vary widely based on location, property size, amenities, and other attributes. The goal of this project is to:

> **Predict the price of a house (in Indian Rupees – Lakhs) based on its physical characteristics, location, and amenity features using machine learning.**

---

## 🎯 Objectives

1. Load and explore the India House Price dataset from Kaggle.
2. Clean the data and handle quality issues.
3. Perform Exploratory Data Analysis (EDA) to understand price-influencing factors.
4. Build and compare multiple regression models.
5. Evaluate all models using MAE, MSE, RMSE, and R² metrics.
6. Identify the best-performing model and analyse feature importance.
7. Draw conclusions and suggest future improvements.

---

## 📊 Dataset Description

| Property | Details |
|---|---|
| **Name** | India House Price Prediction |
| **Source** | Kaggle |
| **Link** | https://www.kaggle.com/datasets/ankushpanday1/india-house-price-prediction |
| **Filename** | india_house_prices.csv |
| **Rows** | 250,000 |
| **Columns** | 23 |
| **Target Variable** | `Price_in_Lakhs` (float – property price in Indian Lakhs ₹) |

### Key Columns

| Column | Description |
|---|---|
| State | State where the property is located |
| City | City of the property |
| Property_Type | Apartment / Independent House / Villa |
| BHK | Number of bedrooms (1–5) |
| Size_in_SqFt | Property area in square feet |
| Price_in_Lakhs | **Target: price in Indian Lakhs ₹** |
| Year_Built | Year the property was constructed |
| Furnished_Status | Furnished / Semi-furnished / Unfurnished |
| Age_of_Property | Age of the property in years |
| Nearby_Schools | Number of nearby schools |
| Nearby_Hospitals | Number of nearby hospitals |
| Public_Transport_Accessibility | High / Medium / Low |
| Parking_Space | Yes / No |
| Security | Yes / No |
| Amenities | List of available amenities |
| Facing | Direction the property faces |
| Owner_Type | Owner / Builder / Broker |
| Availability_Status | Ready_to_Move / Under_Construction |

---

## 🛠️ Technologies Used

| Category | Library/Tool |
|---|---|
| Language | Python 3.12 |
| Data Manipulation | pandas, numpy |
| Visualisation | matplotlib, seaborn |
| Machine Learning | scikit-learn |
| Notebook | Jupyter Notebook |
| Report | python-docx |

---

## 📁 Project Structure

```
House Price Prediction Analysis/
│
├── india_house_prices.csv                           ← Kaggle dataset (input)
├── Haveesh Chowdary Kante_HousePriceAnalysis.ipynb  ← Main Jupyter Notebook
├── Haveesh Chowdary Kante_HousePriceReport.docx     ← Project report (DOCX)
├── requirements.txt                                 ← Python dependencies
└── README.md                                        ← This file
```

---

## ⚙️ Installation & Setup

### 1. Download or clone the project folder

Make sure `india_house_prices.csv` is in the same folder as the notebook.

### 2. Create and activate a virtual environment (recommended)

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux / macOS
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ How to Run the Notebook

```bash
jupyter notebook "Haveesh Chowdary Kante_HousePriceAnalysis.ipynb"
```

Or open it in **VS Code** with the Jupyter extension, or **JupyterLab**:

```bash
jupyter lab
```

Run all cells from top to bottom using **Kernel → Restart & Run All**.

> ⚠️ The CSV file `india_house_prices.csv` must be in the same directory as the notebook.

---

## 🔬 Methodology

1. **Data Loading** – Load the CSV using pandas.
2. **Data Understanding** – Inspect shape, dtypes, first rows, and statistics.
3. **Data Cleaning** – Check for missing values, duplicates, and data-quality issues.
4. **Feature Engineering** – Convert the `Amenities` text column into a numerical count (`Amenities_Count`). Remove high-cardinality columns (`Locality`, `City`) and non-predictive `ID`. Retain `Price_per_SqFt` as the primary pricing feature (correlation ~0.56 with target).
5. **EDA** – Histograms, box plots, bar charts, scatter plots, and a correlation heatmap.
6. **Preprocessing** – Label encoding of categorical features, train-test split (80/20), and StandardScaler normalisation.
7. **Model Training** – Train four regression models on the training set.
8. **Evaluation** – Evaluate all models on the test set using MAE, MSE, RMSE, and R².
9. **Feature Importance** – Visualise and explain the top contributing features using Random Forest.
10. **Conclusions** – Summarise findings, limitations, and future work.

---

## 🤖 Models Used

| Model | Notes |
|---|---|
| Linear Regression | Baseline linear model |
| Decision Tree Regressor | Non-linear, single tree (max_depth=10) |
| Random Forest Regressor | Ensemble of 100 trees (max_depth=15) |
| Gradient Boosting Regressor | Sequential boosting (100 estimators, lr=0.1) |

---

## 📏 Evaluation Metrics

| Metric | Description |
|---|---|
| **MAE** | Mean Absolute Error – average prediction error in ₹ Lakhs |
| **MSE** | Mean Squared Error – penalises large errors more |
| **RMSE** | Root Mean Squared Error – interpretable in ₹ Lakhs |
| **R²** | Coefficient of determination – proportion of variance explained (higher = better) |

---

## 📈 Key Results

| Model | MAE | RMSE | R² |
|---|---|---|---|
| **Random Forest Regressor** ✅ | **6.89** | **8.85** | **0.9961** |
| Gradient Boosting Regressor | 7.42 | 9.26 | 0.9957 |
| Decision Tree Regressor | 9.65 | 12.67 | 0.9919 |
| Linear Regression | 81.14 | 100.82 | 0.4902 |

**Best Model: Random Forest Regressor** — R²=0.9961, RMSE=8.85 Lakhs, MAE=6.89 Lakhs.
`Price_per_SqFt` (80.8%) and `Size_in_SqFt` (19.0%) are the top two features by importance.

---

## ✅ Conclusion

This project demonstrates a complete data analytics and machine learning pipeline applied to India house price prediction. The workflow is clean, reproducible, and beginner-friendly — suitable for an IBM SkillsBuild Data Analytics with AI academic internship submission.

---

## 📜 License

This project is for academic and educational purposes only.
