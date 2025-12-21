## Input (X)
- The input to the model is an hourly multivariate time series consisting of the past L hours (lookback window) of environmental variables, including:
  - PM2.5 (past values, used as explanatory variable — autoregressive feature)
  - NO₂
  - CO
  - SO₂
  - O₃
  - Temperature
  - Humidity
  - (Optional) Pressure, Wind speed, and other available features

- Additional features can be included:
  Time features: hour of day, day of week, month, weekend flag, etc.
  Station ID: if training across multiple monitoring stations (encoded as one-hot or embedding).

## Input shape 
(samples, lookback, n_features)

## Output (y)
  The output is the forecasted PM2.5 concentration for the next 1 hour (HORIZON = 1) at the same station/location.
  
## Valuation Metrics
- MAE (Mean Absolute Error) – measures average absolute difference between predicted and actual values.
- RMSE (Root Mean Squared Error) – penalizes larger errors more strongly than MAE.
- R² (Coefficient of Determination) – measures goodness-of-fit, closer to 1 means better performance.
- MAPE (Mean Absolute Percentage Error) – expresses the error as a percentage of the actual values, useful for interpretability.
  
## Result
- Train
<img width="1223" height="412" alt="image" src="https://github.com/user-attachments/assets/f01845d0-143e-4eff-935e-b730bc60f4e0" />
<img width="1212" height="403" alt="image" src="https://github.com/user-attachments/assets/aea3b6d0-3048-4356-9efa-2ca7cba46bb5" />
<img width="1214" height="409" alt="image" src="https://github.com/user-attachments/assets/84b8548b-5414-41b6-8f8f-f6ecc866326e" />
- Valuation Metrics
<img width="341" height="360" alt="image" src="https://github.com/user-attachments/assets/603fa33f-df8f-4fb1-b27b-9931d4ced566" />

- Comparison of PM2.5 forecasts (200 initial test samples)
<img width="1251" height="554" alt="image" src="https://github.com/user-attachments/assets/2ee5ecce-5a6a-4b2f-9447-685dbff26e5b" />
