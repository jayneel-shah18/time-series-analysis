# IoT Sensor Data Analysis using Machine Learning

**Author**: Jayneel Shah  

---

## Repository Contents

| File                          | Description |
|------------------------------|-------------|
| `Solution.ipynb`             | Main notebook containing all analysis, modeling, and markdown documentation |
| `device1_final_output.csv`   | Prediction results and anomaly flags for temperature Device 1 |
| `device2_final_output.csv`   | Prediction results and anomaly flags for temperature Device 2 |
| `alerts_device1.csv`         | Timestamps and reasons for all alerts generated on Device 1 |
| `alerts_device2.csv`         | Timestamps and reasons for all alerts generated on Device 2 |
| `cycle_pattern_device1.png`  | Visualization of temperature cycles for Device 1 |
| `cycle_pattern_device2.png`  | Visualization of temperature cycles for Device 2 |
| `timeseries_device1.png`     | Actual vs Predicted temperature for Device 1 |
| `timeseries_device2.png`     | Actual vs Predicted temperature for Device 2 |
| `error_histogram_device1.png`| Error distribution for Device 1 |
| `error_histogram_device2.png`| Error distribution for Device 2 |

---

## Summary of Methodology

The solution applies LSTM-based time series forecasting to temperature and motor current sensor data. The following steps were performed:

1. **Data Preprocessing**:
   - Timestamp parsing and sorting
   - Interpolation and outlier clipping
   - Normalization using MinMaxScaler

2. **Sequence Modeling**:
   - A sliding window of 60 timesteps was used to convert the series into supervised learning format.
   - An LSTM model with 64 hidden units was trained to predict the next value.

3. **Anomaly Detection**:
   - Deviation thresholds were applied to detect anomalies:
     - Any error > 3°C triggered a direct alert
     - 3+ consecutive errors > 2°C triggered an alert

4. **Evaluation**:
   - MSE and R² were computed for all models
   - Train-test split analysis confirmed generalization
   - Summary markdowns were included for all devices

---

## Final Remarks

The solution demonstrates a robust, well-documented pipeline for anomaly detection in IoT sensor data. All metrics, visualizations, and justifications are included to support reproducibility and evaluation.