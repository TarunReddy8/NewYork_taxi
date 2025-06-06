# SP25 Taxi Demand Forecasting - MLOps Project

An end-to-end MLOps pipeline for real-time NYC taxi demand forecasting. The project combines historical trip data, automated feature pipelines, robust model training, and live dashboards to enable accurate and maintainable predictions.

---

## Overview

This project predicts hourly taxi demand for NYC using the 2023 Yellow Taxi Trip dataset. It is designed with production-level MLOps best practices, supporting automated training, model tracking, and visualization. A future extension will add real-time streaming capabilities.

---

## Architecture

### 1. Static Data Pipeline (Model Development)

Data Source: NYC Yellow Taxi Trip Data (2023)

Components:
- Data ingestion and schema validation
- Hourly-level time series aggregation
- Feature engineering:
  - Sliding window features (lag, rolling mean)
  - Temporal features (hour, weekday, holidays)
- Model training:
  - Models: XGBoost, LightGBM
  - MLflow for experiment tracking
- Hyperparameter tuning using Optuna

---

### 2. Automated Batch Pipeline

MLOps Infrastructure:
- Hopsworks for Feature Store and Model Registry
- GitHub Actions for scheduled retraining and inference (hourly)
- Prediction storage and monitoring via Feature Store

Key Metrics:
- Hourly Mean Absolute Error (MAE)
- Historical prediction performance tracking

---

### 3. Real-Time Visualization

Streamlit Dashboards:
- Public Dashboard:
  - Interactive NYC taxi zone map with hourly demand predictions
- Internal Dashboard:
  - Model performance (MAE over time)
  - Feature and prediction distributions

Visualization Tools:
- Plotly for trend plots and time series
- Folium for geospatial mapping of NYC zones

---

## Tech Stack

Core:
- Python 3.9+

Machine Learning:
- XGBoost, LightGBM, Scikit-learn
- Optuna (for hyperparameter optimization)
- MLflow (for experiment tracking)

Data Processing:
- Pandas, NumPy, GeoPandas
- PyArrow, Great Expectations (for data validation)

MLOps:
- Hopsworks (Feature Store + Model Registry)
- GitHub Actions (CI/CD automation)
- Docker (containerization)

Visualization:
- Streamlit, Plotly, Folium

---

## Future Work

- Integration of Kafka and Spark for real-time streaming pipeline
- Dynamic model drift detection and retraining triggers
- Enhanced monitoring with Grafana and Prometheus

---

## License
MIT License © 2025 Tarun Kumar Reddy Nallagari


