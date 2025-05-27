# 🚦 Traffic Flow Prediction Using Deep MLP

This project applies a deep MLPRegressor with **log smoothing** and **Gaussian noise** to predict traffic volume on the I-94 highway.

---

## 📁 Project Structure

```
Traffic_Flow_Prediction_Final_MLP/
├── data/
│   └── traffic_data.csv               # Cleaned traffic volume data
├── traffic_mlp_prediction.ipynb      # Main notebook for modeling
├── traffic_visualization.ipynb       # Supplementary visual analytics
└── README.md
```

---

## 🔧 Model Setup

- **Model**: `MLPRegressor` (scikit-learn)
- **Target**: `log1p(traffic_volume) + N(0, 0.1)`
- **Features**: Hour, weekday, weather, holiday, rain, etc.
- **Preprocessing**: StandardScaler
- **Architecture**: (256, 128, 64), relu, early stopping

---

## 🧪 Results

- **R²**: 0.911
- **RMSE**: 604.4
- **MAE**: 407.1
- **Highlights**: 
  - Resolved prediction collapse at 5000
  - Achieved smooth, continuous output using log smoothing + noise

---

## ✅ How to Use

1. Open `traffic_mlp_prediction.ipynb` and run all cells
2. Modify/replace `/data/traffic_data.csv` if needed
3. Visualize results in `traffic_visualization.ipynb`
