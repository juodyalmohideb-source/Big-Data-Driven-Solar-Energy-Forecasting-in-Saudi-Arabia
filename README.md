# Big Data-Driven Solar Energy Forecasting in Saudi Arabia

## Overview

This project presents a Big Data-driven framework for forecasting daily solar photovoltaic (PV) energy output across five major Saudi Arabian cities: Riyadh, Jeddah, Mecca, Medina, and Dammam.

The project combines Apache Spark for scalable data processing with Machine Learning and Deep Learning models to analyse solar energy patterns and forecast daily PV output.

The dataset contains 10,980 simulation-based records covering the year 2024, including meteorological conditions, geographic information, solar panel configurations, solar irradiance, output power, and estimated daily energy generation.

## Cities Included

- Riyadh
- Jeddah
- Mecca
- Medina
- Dammam

## Project Objectives

The project investigates four main research questions:

1. Which forecasting model provides the most accurate prediction of daily solar PV output across the five cities?
2. How do panel technology and mounting configuration interact with geographic and climatic factors?
3. Which model generalises best across the different climatic conditions of the five cities?
4. How does extreme ambient temperature above 38°C affect forecasting difficulty?

## Methodology

The project follows a complete data analytics and forecasting pipeline:

1. Data ingestion and processing using Apache Spark
2. Exploratory Data Analysis (EDA)
3. Feature engineering
4. Categorical encoding and numerical normalization
5. Chronological train-validation-test splitting
6. Machine Learning model training
7. Deep Learning model training
8. Model evaluation using multiple metrics
9. Statistical significance testing
10. City-level and temperature-stratified analysis

## Models Evaluated

### Classical Machine Learning

- Mean Baseline
- Linear Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

### Deep Learning

- Dense Neural Network
- LSTM
- GRU
- Bi-GRU
- CNN-LSTM Hybrid
- Transformer Encoder
- CNN-LSTM-Transformer

## Key Results

XGBoost achieved the best overall performance on the held-out test set:

| Metric | XGBoost |
|--------|---------|
| RMSE | 0.4955 kWh |
| MAE | 0.4180 kWh |
| MAPE | 2.01% |
| R² | 0.9391 |
| MBE | 0.173 kWh |

Random Forest showed stronger stability across the five-fold walk-forward cross-validation, achieving a mean RMSE of 0.6286 ± 0.3450 kWh.

Among the deep learning models, GRU achieved the best performance with an RMSE of 1.0551 kWh and an R² of 0.7240.

## Key Findings

- Solar irradiance was the strongest predictor of daily solar output, with a Pearson correlation of approximately 0.99.
- XGBoost outperformed the evaluated deep learning architectures on the held-out test set.
- Dammam showed substantially higher forecasting difficulty compared with the other cities.
- Forecasting errors increased for records with temperatures above 38°C.
- Panel efficiency showed negligible predictive importance in this simulation dataset.
- The three panel technologies produced statistically similar output distributions in the dataset.
- The proposed CNN-LSTM-Transformer architecture underperformed on the current dataset, highlighting that increased model complexity does not necessarily lead to better forecasting performance.

## Technologies

- Python
- Apache Spark / PySpark
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- Matplotlib
- Seaborn

## Dataset

The dataset is simulation-based and contains solar energy records for five major Saudi Arabian cities during 2024.

It includes:

- Date
- City
- Latitude
- Longitude
- Temperature
- Weather condition
- Panel Type
- Mount Type
- Tilt Angle
- Panel Efficiency
- Solar Irradiance
- Output Power
- Estimated Daily Output

See [Data_Dictionary.md](Data_Dictionary.md) for detailed information about each field.
