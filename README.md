## Input (X)
- The input to the model is an hourly multivariate time series consisting of the past L hours (lookback window) of environmental variables, including:
  PM2.5 (past values, used as explanatory variable — autoregressive feature)
  NO₂
  CO
  SO₂
  O₃
  Temperature
  Humidity
  (Optional) Pressure, Wind speed, and other available features

- Additional features can be included:
  Time features: hour of day, day of week, month, weekend flag, etc.
  Station ID: if training across multiple monitoring stations (encoded as one-hot or embedding).

## Input shape 
(samples, lookback, n_features)

## Output (y)
  The output is the forecasted PM2.5 concentration for the next 1 hour (HORIZON = 1) at the same station/location.
  
## Valuation Metrics
  MAE (Mean Absolute Error) – measures average absolute difference between predicted and actual values.
  RMSE (Root Mean Squared Error) – penalizes larger errors more strongly than MAE.
  R² (Coefficient of Determination) – measures goodness-of-fit, closer to 1 means better performance.
  MAPE (Mean Absolute Percentage Error) – expresses the error as a percentage of the actual values, useful for interpretability.
  
