# Traffic Volume Prediction Using MLP

This project aims to predict traffic volume using a Multi-Layer Perceptron (MLP) regression model, and visualize traffic patterns based on various features from a real-world dataset.

## 📌 Project Structure

- `traffic_data.csv`: Main dataset containing traffic volume and relevant features.
- `traffic_mlp_prediction.ipynb`: Notebook for building and training an MLP model to predict traffic volume.
- `traffic_visualization.ipynb`: Notebook for visualizing traffic patterns and insights.

## 🎯 Project Objective

The goal is to build a traffic volume prediction model that can capture non-linear relationships in traffic data. The model can be used to support traffic planning and intelligent transportation system design.

## 📊 Dataset Description

The dataset (`traffic_data.csv`) includes the following key fields:

- `时间` (Time): Timestamp of observation
- `车流量` (Traffic volume): Target variable to predict
- `天气`, `温度`, `风速`, `节假日` 等: Features influencing traffic conditions

> Data may be collected from sensors, weather APIs, or road monitoring platforms.

## 🧠 Model Summary

We use a **Multi-Layer Perceptron (MLP)** model implemented with `sklearn.neural_network.MLPRegressor`.

- **Preprocessing**:
  - Standardization of features
  - Log smoothing of volume
  - Handling missing values
- **Model structure**:
  - Hidden layers: (64, 32)
  - Activation: ReLU
  - Early stopping: Enabled
- **Evaluation**:
  - Metrics: R², MAE, RMSE
  - Visual diagnostics for model performance

## 📈 Visualization Highlights

- Time-series trends of traffic volume
- Volume variation by weather, time, and holidays
- Heatmaps, bar plots, and line charts to support EDA

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/traffic-volume-prediction-mlp.git
   cd traffic-volume-prediction-mlp
