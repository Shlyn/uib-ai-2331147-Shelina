# 📱 Smartphone Price Prediction Model

## Overview
This repository contains the code and resources for a **Machine Learning Model** designed to predict the price of a smartphone based on its technical specifications.

The model is trained using a dataset of various smartphones and their features, and the complete analysis workflow is provided.

***

## Repository Contents

| File Name | Description |
| :--- | :--- |
| **[`Prediction Price.ipynb`](./Prediction%20Price.ipynb)** | The main **Jupyter Notebook** that contains the complete project workflow: data loading, Exploratory Data Analysis (EDA), feature engineering, model training, evaluation, and saving the final model. |requirements.txt
| **[`Data-smartphone.csv`](./data-smartphone.csv)** | The **raw dataset** used for training the model. It includes features like Brand, Storage, RAM, Screen Size, Camera, and Battery Capacity. |
| **[`E_Model_Price_Pridiction_For_Phones.joblib`](./E_Model_Price_Pridiction_For_Phones.joblib)** | The **final trained machine learning model**, serialized using `joblib`. This model can be loaded directly to make price predictions without retraining. |
| **[`Requirements.txt`](./requirements.txt)** | A list of all required **Python packages** and their specific versions needed to run the notebook and the model successfully. |


## 🔬 Notebook Workflow (`Prediction Price.ipynb`)

This Jupyter Notebook details the entire machine learning pipeline, structured into the following key phases:

1.  **Data Loading and Inspection:**
    * Reading the `data-smartphone.csv` file into a Pandas DataFrame.
    * Initial exploration of the dataset, including checking for missing values, data types, and descriptive statistics.

2.  **Exploratory Data Analysis (EDA):**
    * Visualization of key features to understand their distribution and relationship with the target variable (Price).
    * Analysis of how features like **RAM, Storage, and Brand** correlate with smartphone pricing.

3.  **Data Preprocessing and Feature Engineering:**
    * **Cleaning:** Handling any inconsistencies in the data.
    * **Feature Transformation:** Converting categorical features (like 'Brand') into a numerical format suitable for machine learning using techniques like One-Hot Encoding.
    * **Scaling/Normalization** (If applicable): Preparing numerical features for the model.

4.  **Model Training and Selection:**
    * Splitting the data into training and testing sets.
    * Implementing and training a **Regression Model** (e.g., Linear Regression, based on the joblib file structure) to predict the price.
    * Evaluating the model's performance using relevant metrics (e.g., Mean Absolute Error, R-squared).

5.  **Model Export:**
    * The final, best-performing model is saved using `joblib` into the file **`E_Model_Price_Pridiction_For_Phones.joblib`** for easy reuse and deployment.

---
