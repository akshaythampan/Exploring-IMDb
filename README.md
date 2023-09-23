# Exploring-IMDb


This repository contains Python code for analyzing movie data using the Pandas library. The code covers various aspects of data preprocessing, exploration, and feature selection. Below, we summarize the key methods and steps performed in the code.

## Overview

The code processes a movie dataset stored in a CSV file and performs the following tasks:

1. Data Loading and Initial Exploration
2. Data Cleaning and Imputation
3. Feature Engineering
4. Correlation Analysis
5. Feature Selection
6. Director Success Prediction

## Key Methods and Steps

### 1. Data Loading and Initial Exploration

- The code uses the Pandas library to read the movie dataset from a CSV file into a DataFrame.
- The `df.head()` method is used to display the first few rows of the DataFrame.
- The `df.columns` attribute is used to retrieve and display the column names of the DataFrame.
- Null value checks are performed using the `df.isnull()` method, and the presence of null values is determined.
- Rows with any null values are removed using `df.dropna()`.

### 2. Data Cleaning and Imputation

- The "year" column values are cleaned using regular expressions to remove decimal parts.
- The data type of the "year" column is changed to float64 using the `astype()` method.
- The code extracts the release year from the "released" column using regular expressions and compares it with the "year" column to identify matches.
- Rows where the years do not match are filtered out.

### 3. Feature Engineering

- The code performs correlation analysis on all columns to identify relationships between features.
- The number of unique companies in the "company" column is calculated.
- The count of each unique company in the "company" column is determined using `value_counts()`.

### 4. Correlation Analysis

- The code calculates the correlation matrix for all columns in the DataFrame.
- Diagonal elements of the correlation matrix are set to NaN to avoid self-correlation.
- The top 5 unique correlation pairs are identified and displayed.
- A heatmap visualization of the correlation matrix is created using Seaborn.

### 5. Feature Selection

- Feature selection is performed using the `SelectKBest` method from Scikit-learn.
- Chi-squared test is used as the scoring function.
- The code selects the top 5 features based on their scores.

### 6. Director Success Prediction

- The code calculates the average IMDb rating for each director.
- A threshold is defined to classify directors as successful or not.
- A binary target variable "director_success" is created.
- The director success information is merged back into the original DataFrame.
- Missing values in "director_success" are filled with 0 for directors not in the director success DataFrame.

## Dependencies

The code requires the following Python libraries:

- Pandas
- NumPy
- Seaborn
- Matplotlib
- Scipy
- Scikit-learn
- re

## Usage

To run the code, follow these steps:

1. Ensure you have the required dependencies installed.
2. Replace `"movies.csv"` with the path to your movie dataset CSV file.
3. Execute the code in a Python environment (e.g., Jupyter Notebook).

Feel free to customize and adapt the code to your specific dataset and analysis goals.

---
