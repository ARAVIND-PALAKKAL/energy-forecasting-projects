# Energy Forecasting Projects: Classical vs Deep Learning Energy Forecasting

## Overview
A comparative study of classical statistical and deep learning approaches 
for hourly energy load forecasting, using real-world data from the AEP 
(American Electric Power) region.

## Results

| Model | MAPE | RMSE |
|-------|------|------|
| ARIMA (classical baseline) | 15.67% | 2844.99 MW |
| Transformer | 5.01% | 1000.95 MW |
| LSTM | **3.45%** | **696.64 MW** |

**Key finding:** LSTM outperforms the classical ARIMA baseline by 78%, 
demonstrating the advantage of deep learning approaches for capturing 
complex temporal patterns in energy consumption data.

## Dataset
- **Source:** [PJM Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption) (Kaggle)
- **Region:** AEP (American Electric Power)
- **Period:** 2016–2018 (subset used for modelling)
- **Granularity:** Daily average (resampled from hourly)

## Methodology
1. **Data preparation:** Resampled hourly data to daily averages, 
   train/test split with last 90 days held out for evaluation
2. **ARIMA:** Fitted with order (5,1,0) as classical baseline
3. **LSTM:** 2-layer LSTM with hidden size 64, trained for 50 epochs 
   with sequence length of 30 days
4. **Transformer:** 2-layer Transformer encoder with d_model=64, 
   trained for 50 epochs

## Metrics
- **MAPE** (Mean Absolute Percentage Error) — primary metric
- **RMSE** (Root Mean Squared Error) — secondary metric

## Project Structure
energy-forecasting-projects/

├── data/               # Raw CSV files (not tracked in Git)

├── notebooks/          # Jupyter notebooks

│   └── project3_classical_vs_deeplearning.ipynb

├── models/             # Saved model weights

├── results/            # Output plots and metrics

└── README.md

## Requirements
pandas

numpy

matplotlib

statsmodels

torch

jupyter

## How to Run
1. Clone the repo
2. Install dependencies: `pip install -r requirements.txt`
3. Download AEP_hourly.csv from Kaggle and place in `data/`
4. Open and run `notebooks/project3_classical_vs_deeplearning.ipynb`

## Context
This project was built as part of a series exploring time series 
forecasting methods for energy systems, with a focus on benchmarking 
classical vs. modern deep learning approaches.
