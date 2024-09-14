# Anomaly Detection in CloudMonitor Data
## Overview
This project was built as part of a hackathon challenge to develop an anomaly detection system for CloudMonitor. CloudMonitor provides real-time monitoring data (such as CPU utilization, network traffic, disk usage, etc.) in cloud environments. Anomalies in this data can indicate serious issues such as system overloads, network attacks, or resource misconfigurations. Our goal is to detect these anomalies, categorize them, and assign a severity score so that they can be addressed promptly.

## Objectives
### 1. Anomaly Detection: 
Automatically detect unusual patterns in cloud monitoring data that deviate from normal behavior.
### 2. Anomaly Categorization: 
Classify the detected anomalies into different types such as:
#### Spikes: 
Sudden increases in resource usage.
#### Drifts: 
Gradual changes over time.
#### Drops: 
Sudden decreases in resource usage.
### 3. Anomaly Scoring: 
Assign severity scores to anomalies based on how critical they are to the system's performance and security.
### 4. Visualization Dashboard: 
Display the detected anomalies, their categories, and severity scores in an easy-to-understand visual format.

## How It Works
### 1. Data Collection
The system analyzes multiple CSV files, each containing time-series data of different metrics (e.g., CPU usage, network traffic). Each file consists of a timestamp and a value.

### 2. Data Preprocessing
Resampling: Ensures all data is consistently measured at regular intervals.
Normalization: Scales the data so that different metrics (CPU, network, etc.) are on the same scale.
Handling Missing Data: Uses interpolation to fill in any missing values.
### 3. Feature Engineering
To better detect anomalies, the system extracts new features such as:

1. Rolling Mean & Standard Deviation: Helps identify trends and variability over short periods.
2. Difference Feature: Captures sudden changes in data points.
3. Lag Features: Includes previous data points to understand time dependencies.
### 4. Anomaly Detection
We used a machine learning model called Isolation Forest, which identifies anomalies by isolating data points that are very different from the rest. This helps detect anomalies without needing prior labels or historical anomalies.

### 5. Anomaly Categorization
Each detected anomaly is categorized as:

Spike: A sudden, large increase in the metric.
Drop: A sudden, large decrease in the metric.
Drift: A slow, gradual change over time.
### 6. Anomaly Scoring
The severity of each anomaly is determined by how far the data deviates from the normal range. More extreme deviations receive higher severity scores.

### 7. Visualization Dashboard
An interactive dashboard displays:

Original data: A line graph showing how the system metrics changed over time.
Anomalies: Red markers showing where anomalies were detected.
Severity: Color-coded severity scores, helping prioritize which anomalies need immediate attention.


