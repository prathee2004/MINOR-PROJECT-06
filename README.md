# QuickCart Stockout Risk Prediction

## Project Overview

This project focuses on predicting warehouse inventory stockout risk for QuickCart, a quick-commerce dark-store operator.

The objective is to classify each SKU at each store on each day into one of three categories:

- **Safe** – sufficient stock is available before the next replenishment.
- **At-Risk** – stock cover is close to the expected replenishment wait.
- **Imminent** – stock is expected to run out before the next delivery.

The project uses supervised machine learning classification techniques and combines inventory, store, SKU, supplier, and event data.

## Dataset

The project contains five CSV files:

- `dim_stores.csv` – Store information
- `dim_skus.csv` – Product/SKU information
- `dim_suppliers.csv` – Supplier information
- `dim_events.csv` – Festival and promotional event information
- `fact_inventory_daily.csv` – Daily inventory and stockout-risk data

The fact table contains **21,600 records** covering 12 stores, 60 SKUs, and 30 days.

## Data Preprocessing

The project includes:

- Data quality checking
- Handling missing supplier reliability values
- Standardizing city names
- Joining multiple tables
- Checking target-class distribution
- Creating features for machine learning

## Feature Engineering

The following features were created or used:

- Reorder gap
- Days of cover ratio
- Clean supplier reliability
- Recent reorder indicator
- Category information
- Day of month
- Festival-related features

## Machine Learning Models

The following classification models were implemented:

1. Majority Class Baseline
2. Logistic Regression
3. Random Forest
4. Gradient Boosting

A time-based train-test split was used to reduce information leakage:

- **Training:** October 1–23, 2026
- **Testing:** October 24–30, 2026

## Evaluation

The models were evaluated using:

- Accuracy
- Balanced Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

Special attention was given to **Imminent-class recall**, because correctly identifying potential stockouts is important for inventory planning.

## Results

Gradient Boosting achieved the strongest overall performance in terms of accuracy, balanced accuracy, and Imminent-class F1-score.

Logistic Regression achieved the highest recall for the Imminent class.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- Jupyter Notebook

## Project Structure

```text
QuickCart-Stockout-Risk/
│
├── MINOR_PROJECT_06_PRATHEEKSHA.ipynb
├── dim_events.csv
├── dim_skus.csv
├── dim_stores.csv
├── dim_suppliers.csv
├── fact_inventory_daily.csv
└── README.md
