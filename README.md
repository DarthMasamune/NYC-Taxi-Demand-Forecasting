# NYC Taxi Demand Forecasting

This project uses the 2023 NYC Yellow Taxi Trip dataset to predict taxi demand across different locations and times in New York City. We compare traditional machine learning methods with deep learning approaches to find the most effective forecasting solution.

## Dataset

The dataset contains 38 million taxi trip records from NYC Yellow Taxi operations. After cleaning and preprocessing, we worked with 35.3 million valid records covering 262 pickup locations across the city. The data was aggregated into hourly demand patterns, creating 781,196 records for analysis.

## Approach

**Baseline Models:**
- Historical averages
- Moving averages with different time windows
- Linear and Ridge regression
- Random Forest

**Deep Learning Models:**
- LSTM networks with 24-hour sequence inputs
- GRU networks for efficient sequence modeling
- Temporal CNN using 1D convolutions
- Transformer models with attention mechanisms

**Advanced Methods:**
- Hyperparameter optimization using Optuna
- Ensemble approaches combining multiple models

## Data Processing

We created 43 engineered features including lag variables, rolling statistics, cyclical time encodings, and binary indicators for weekends and peak hours. The dataset was split chronologically into 70% training, 15% validation, and 15% testing to ensure realistic evaluation.

## Results

| Model Type | Best Model | Test MAE | Test MAPE |
|------------|------------|----------|-----------|
| Baseline | Random Forest | 5.56 | 10.0% |
| Deep Learning | LSTM | 6.98 | 28.8% |
| Ensemble | Stacked Ensemble | 6.96 | 38.5% |

Random Forest achieved the best overall performance with 5.56 MAE, outperforming all deep learning approaches. The stacked ensemble method achieved the best deep learning performance at 6.96 MAE by effectively combining multiple model predictions.

## Conclusion

This project demonstrates that well-engineered features combined with tree-based methods can be highly effective for taxi demand forecasting. While deep learning models showed competitive performance, the Random Forest baseline proved most effective for this specific forecasting task. The ensemble methods successfully improved upon individual deep learning models by reducing prediction bias.