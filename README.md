AWS EC2 CPU Utilization Anomaly Detection
This project implements and compares statistical and unsupervised machine learning methods to detect anomalies in AWS EC2 CPU utilization metrics. We leverage both a Z-Score Baseline (statistical outlier detection) and an Isolation Forest (tree-based contextual anomaly detection).

✅ Project Workflow
Exploratory Data Analysis (EDA)

Loaded historical EC2 CPU utilization records sampled at regular 5-minute intervals.
Analyzed statistical properties (Mean: ~43.11%, Std Dev: ~4.30%).
Plotted overall distribution metrics using Histograms and Box Plots to check skewness and outliers.
Feature Engineering

Extracted temporal characteristics: hour, day_of_week, day.
Formulated historical lags: lag_1, lag_2, lag_3, lag_6, lag_12, and lag_24 to capture direct dependencies.
Built statistical context rolling windows: 12 and 24-interval rolling_mean and rolling_std to inform the model of local trend shifts.
Anomaly Detection Methodologies

Z-Score Anomaly Detection: Used a standard statistical threshold ( |Z|>3 ) to locate extreme deviation spikes across the full dataset.
Isolation Forest: Split the dataset chronologically ( 80%  train,  20%  test) and trained an unsupervised forest estimator to map multi-dimensional anomalies.
Sensitivity & Model Evaluation

Conducted a sensitivity evaluation sweeping contamination factors ( 1%  to  10% ) to understand how strictly the forest filters anomalies.
Plotted a detailed Confusion Matrix verifying performance against the statistical Z-Score baseline.
‐‐‐

intern id:CITS9576
