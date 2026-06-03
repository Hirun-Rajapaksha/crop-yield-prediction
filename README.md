# Crop Yield Prediction Using Machine Learning

## Introduction

This project focuses on predicting crop yield using machine learning techniques. The main goal is to build a regression model that can estimate crop yield based on agricultural and environmental factors such as country, crop type, year, rainfall, pesticide usage, and average temperature.

Crop yield prediction is useful in agriculture because it can support better planning, resource management, and decision-making. By analyzing historical crop yield data, this project identifies important patterns and builds models that can predict future yield values.

The target variable of this project is:

```text
hg/ha_yield
```

This represents crop yield measured in hectograms per hectare.

Since the target variable is continuous numerical data, this is a **regression machine learning problem**.

---

## Project Objectives

The main objectives of this project are:

* Analyze the crop yield dataset using Exploratory Data Analysis.
* Identify missing values, duplicate records, outliers, and feature patterns.
* Clean and preprocess the dataset for machine learning.
* Encode categorical variables such as country and crop type.
* Train multiple regression models.
* Compare model performance using evaluation metrics.
* Identify the best-performing model for crop yield prediction.

---

## Dataset Description

The dataset contains agricultural crop yield records from different countries and crop types over multiple years.

### Dataset Columns

| Column Name                     | Description                                   |
| ------------------------------- | --------------------------------------------- |
| `Area`                          | Country or region where the crop was produced |
| `Item`                          | Crop type                                     |
| `Year`                          | Year of the record                            |
| `hg/ha_yield`                   | Crop yield in hectograms per hectare          |
| `average_rain_fall_mm_per_year` | Average yearly rainfall in millimeters        |
| `pesticides_tonnes`             | Pesticide usage in tonnes                     |
| `avg_temp`                      | Average temperature                           |

---

## Project Folder Structure

```text
crop-yield-prediction/
│
├── data/
│   ├── yield_df.csv
│   └── crop_yield_cleaned.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_model_building.ipynb
│
├── src/
│   └── utils.py
│
├── requirements.txt
├── README.md
├── .gitignore
└── .gitattributes
```

---

## File Description

| File / Folder                       | Description                                                                |
| ----------------------------------- | -------------------------------------------------------------------------- |
| `data/yield_df.csv`                 | Original raw dataset                                                       |
| `data/crop_yield_cleaned.csv`       | Cleaned and preprocessed dataset                                           |
| `notebooks/01_eda.ipynb`            | Exploratory Data Analysis notebook                                         |
| `notebooks/02_data_cleaning.ipynb`  | Data cleaning and preprocessing notebook                                   |
| `notebooks/03_model_building.ipynb` | Model training, evaluation, and comparison notebook                        |
| `src/utils.py`                      | Helper functions for loading data, preprocessing, evaluation, and plotting |
| `requirements.txt`                  | Python libraries required to run the project                               |
| `README.md`                         | Project documentation                                                      |

---

## Tools and Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Visual Studio Code
* GitHub Desktop

---

## Project Workflow

The project was completed in three main stages.

---

## 1. Exploratory Data Analysis

Notebook:

```text
notebooks/01_eda.ipynb
```

In this stage, the dataset was analyzed to understand its structure, patterns, and important features.

### Main tasks completed:

* Loaded and inspected the dataset.
* Checked dataset shape and column details.
* Identified numerical and categorical variables.
* Checked missing values and duplicate records.
* Analyzed the target variable distribution.
* Performed univariate analysis on numerical features.
* Performed bivariate analysis with crop yield.
* Analyzed crop yield by crop type.
* Analyzed crop yield by country.
* Checked correlation between numerical features.
* Studied crop yield trends over time.

### Key findings from EDA:

* The dataset contains crop yield records from multiple countries and crop types.
* The target variable `hg/ha_yield` is right-skewed.
* There are no missing values in the dataset.
* Duplicate records exist in the raw dataset.
* Crop type and country/area strongly influence crop yield.
* Numerical features alone do not show strong linear correlation with crop yield.

---

## 2. Data Cleaning and Preprocessing

Notebook:

```text
notebooks/02_data_cleaning.ipynb
```

In this stage, the dataset was cleaned and prepared for machine learning.

### Main tasks completed:

* Loaded the raw dataset.
* Checked missing values.
* Checked duplicate records.
* Removed duplicate rows.
* Applied one-hot encoding to categorical variables.
* Converted the dataset into numerical format.
* Verified the cleaned dataset.
* Saved the cleaned dataset as `crop_yield_cleaned.csv`.

### Cleaning summary:

| Step                   | Result                    |
| ---------------------- | ------------------------- |
| Missing values         | 0                         |
| Duplicate rows removed | 2,310                     |
| Raw dataset shape      | 28,242 rows × 7 columns   |
| Cleaned dataset shape  | 25,932 rows × 114 columns |
| Target variable        | `hg/ha_yield`             |

The cleaned dataset was saved as:

```text
data/crop_yield_cleaned.csv
```

---

## 3. Model Building and Evaluation

Notebook:

```text
notebooks/03_model_building.ipynb
```

In this stage, several regression models were trained and evaluated.

### Models used:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* K-Nearest Neighbors Regressor
* Gradient Boosting Regressor
* Tuned KNN using GridSearchCV

### Evaluation metrics:

| Metric   | Description                                               |
| -------- | --------------------------------------------------------- |
| MAE      | Mean Absolute Error                                       |
| RMSE     | Root Mean Squared Error                                   |
| R² Score | Measures how well the model explains crop yield variation |
| MAPE     | Mean Absolute Percentage Error                            |

---

## Model Performance Summary

The strongest models in this project were KNN and Random Forest.

### Final model findings:

* KNN achieved the highest R² score.
* Random Forest also performed very well with low error values.
* Decision Tree performed better than Linear Regression.
* Gradient Boosting performed better than Linear Regression but weaker than KNN and Random Forest.
* Linear Regression had the weakest performance because crop yield prediction is not purely linear.

Based on the results, **KNN Tuned** can be selected as the best model by R² score, while **Random Forest** is also a strong and stable alternative.

---

## Feature Importance

Feature importance analysis was performed using tree-based models.

Important features included:

* Crop type dummy variables such as `Item_Potatoes`
* Pesticide usage
* Average temperature
* Average rainfall
* Country/area dummy variables

This showed that both crop type and geographical area are important factors in predicting crop yield.

---

## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/crop-yield-prediction.git
```

### 2. Open the project folder

```bash
cd crop-yield-prediction
```

### 3. Create a virtual environment

```bash
python -m venv .venv
```

### 4. Activate the virtual environment

For Windows PowerShell:

```bash
.\.venv\Scripts\Activate.ps1
```

For Command Prompt:

```bash
.venv\Scripts\activate
```

### 5. Install required libraries

```bash
pip install -r requirements.txt
```

### 6. Open Jupyter Notebook

```bash
jupyter notebook
```

Then run the notebooks in this order:

```text
01_eda.ipynb
02_data_cleaning.ipynb
03_model_building.ipynb
```

---

## Requirements

The required Python libraries are listed in `requirements.txt`.

Main libraries used:

```text
jupyter
pandas
numpy
matplotlib
seaborn
scikit-learn
```

Install all requirements using:

```bash
pip install -r requirements.txt
```

---

## Results

This project successfully built and evaluated machine learning models for crop yield prediction.

The final results showed that:

* KNN achieved the best R² score.
* Random Forest gave strong and stable performance.
* Non-linear models performed better than Linear Regression.
* Crop type and country/area were highly important features.
* The cleaned and encoded dataset was suitable for regression model training.

---

## Future Improvements

Possible future improvements include:

* Try advanced models such as XGBoost or LightGBM.
* Perform deeper hyperparameter tuning.
* Apply log transformation to skewed variables.
* Add more agricultural features such as soil type, fertilizer usage, irrigation, and humidity.
* Save the best trained model using Pickle or Joblib.
* Build a web application using Streamlit, Flask, or FastAPI.
* Deploy the model for real-world crop yield prediction.

---

## Project Status

Completed.

This project includes:

* Exploratory Data Analysis
* Data Cleaning and Preprocessing
* Machine Learning Model Training
* Model Evaluation
* Feature Importance Analysis
* Hyperparameter Tuning
* Final Model Comparison

---

## Author

Hirun Rajapaksha
Developed as a machine learning project for crop yield prediction.
