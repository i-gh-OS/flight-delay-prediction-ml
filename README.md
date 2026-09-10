# U.S. Flight Delay Prediction

Machine learning project analyzing approximately **13.7 million U.S. commercial flight records** to study and predict flight delays.

The project covers the full modelling workflow, from data exploration and preprocessing to classification and regression, with particular attention to temporal validation and out-of-sample performance.

## Project Overview

Flight delays are influenced by a combination of temporal, operational and route-related factors. This project explores whether historical flight data can be used to predict both the **occurrence** and **magnitude** of delays.

The analysis is organized into four stages:

1. Dataset inspection and preparation
2. Exploratory data analysis
3. Delay classification
4. Delay regression

A chronological train / validation / test strategy is used instead of a purely random split to better approximate a real forecasting setting, where models are trained on past observations and evaluated on future flights.

## Dataset

The project works with approximately **13.7 million observations** of U.S. commercial flights.

Given the size of the dataset, preprocessing and model development required particular attention to:

- memory-efficient data manipulation
- feature preparation
- computational cost
- scalable model evaluation
- prevention of temporal data leakage

The raw dataset is not included in this repository due to its size.

## Methodology

### 1. Data Overview

`00_data_overview.ipynb`

Initial inspection of the dataset, including its structure, variables, data quality and preparation requirements.

### 2. Exploratory Data Analysis

`01_eda.ipynb`

Exploratory analysis of the variables and patterns associated with flight delays.

This stage is used to better understand the data before modelling and to identify potentially relevant relationships and distributions.

### 3. Classification

`02_classification.ipynb`

Supervised classification models are developed to predict whether a flight will be delayed.

The models evaluated include:

- Logistic Regression
- K-Nearest Neighbors
- Decision Tree
- Random Forest

Models are compared using out-of-sample performance metrics on validation and test data.

The comparison allows both predictive performance and computational complexity to be considered when evaluating the different approaches.

### 4. Regression

`03_regression.ipynb`

Regression techniques are used to model the magnitude of flight delays as a continuous prediction problem.

This complements the classification task by moving beyond whether a delay occurs and studying the expected extent of the delay.

## Validation Strategy

A **temporal train / validation / test split** is used rather than randomly distributing observations across datasets.

This is important because random splitting can allow information from later periods to influence model development.

The temporal setup provides a more realistic evaluation:

```text
Past observations  →  Training
Later observations →  Validation
Future observations → Test
```
The final test set therefore acts as an approximation of genuinely unseen future data.

## Repository Structure
```text
├── 00_data_overview.ipynb    # Dataset inspection and preprocessing
├── 01_eda.ipynb              # Exploratory data analysis
├── 02_classification.ipynb   # Flight delay classification models
├── 03_regression.ipynb       # Flight delay regression models
├── requirements.txt          # Python dependencies
└── .gitignore
````
## Technologies
```text
Python
pandas
NumPy
scikit-learn
Jupyter Notebook
Data preprocessing
Exploratory data analysis
Supervised machine learning
Classification
Regression
Temporal model validation
Out-of-sample evaluation
Key Technical Considerations
Large-scale data processing
```
The dataset contains approximately 13.7 million flight records, making computational efficiency an important part of the modelling process.

## Temporal validation

Using chronological rather than random validation reduces the risk of temporal leakage and more closely resembles how a predictive system would be evaluated in practice.

## Model comparison

The project compares models with substantially different characteristics, ranging from an interpretable linear classifier to nonlinear and ensemble methods.

This makes it possible to assess the trade-off between predictive performance, interpretability and computational cost.

## Reproducibility

Install the required Python dependencies with:

``pip install -r requirements.txt``

The notebooks are intended to be followed sequentially:

```text
00_data_overview.ipynb
        ↓
01_eda.ipynb
        ↓
02_classification.ipynb
        ↓
03_regression.ipynb
```
## Project Context

Academic machine learning project developed as part of the Telecommunications Engineering & Business Analytics program at ICAI – Universidad Pontificia Comillas.
