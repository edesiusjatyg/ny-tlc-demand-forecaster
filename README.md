# New York TLC Demand Forecaster
Simple LSTM model to forecast New York Taxi &amp; Limousine Commission's hourly demand. This model uses the yellow taxi dataset, ranging from June 2025 - September 2025. **This model is built using Keras.**

<br>

__*There's no dataset in this repo because it is too large. Refer to [this link](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) if you want to download the dataset.*__

## Information
**Task:** Forecast taxi demand for the next hour

**Data Size:** ~2100 rows (hourly time series)

### Features:
- hour
- day_of_week
- is_weekend
- lag_24 (1 day lag)
- lag_168 (1 week lag)

### Architecture:
***LSTM(50) → Dense(10) → Dense(1)***

**Loss:** MSE

**Batch Size:** 32

**Epoch:** Early stopped at ~60 epoch (10 patience)

### Test Metrics:
Train/test split uses 80:20 chronological split with no shuffle.

**RMSE Percentage:** ~7.64%

**MSE Percentage:** ~0.58%

**R-squared:** ~0.979

### Limitations:
- As of now, the model could only forecast 1 hour ahead.
- Performance declines in the occurrence of an outlier event.

### Intended Use:
- Short term demand forecasting
- Taxi supply scheduling
