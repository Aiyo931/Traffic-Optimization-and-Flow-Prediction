# 🚦 使用深度 MLP 模型进行交通流量预测

本项目使用带有 **对数平滑（log1p）+ 高斯扰动增强** 的深度多层感知机（MLP）模型，对 I-94 高速公路交通数据进行流量预测，有效缓解了传统回归模型中的“预测断层”和“塌堆”问题。

---

## 📁 项目结构

```
Traffic_Flow_Prediction_Final_MLP/
├── data/
│   └── traffic_data.csv               # 清洗后的交通流量数据
├── traffic_mlp_prediction.ipynb      # 主模型 notebook 文件
├── traffic_visualization.ipynb       # 可视化分析 notebook
└── README.md                         # 项目说明（本文件）
```

---

## 🧠 建模方案

- **模型类型**：`MLPRegressor`（多层感知机回归器，来自 scikit-learn）
- **目标处理**：`log1p(traffic_volume) + N(0, 0.1)`（对数平滑 + 高斯噪声扰动）
- **输入特征**：小时、星期、节假日、天气、云量、降雨、降雪等
- **预处理**：输入特征使用 `StandardScaler` 标准化
- **模型结构**：
  - 三层隐藏层：`(256, 128, 64)`
  - 激活函数：ReLU
  - 提前停止（early_stopping）防止过拟合
  - 最多训练 1000 次

---

## 📊 模型效果

- **决定系数 R²**：0.911
- **RMSE（均方根误差）**：604.4
- **MAE（平均绝对误差）**：407.1

### ✅ 效果亮点：

- 有效消除预测塌堆（5000 附近不再拥挤）
- 输出连续、平滑，图像自然贴近理想线
- 适合用于实际交通预测与智能调度系统应用

---

## ▶️ 使用方式

1. 打开 `traffic_mlp_prediction.ipynb`，从头运行所有单元格
2. 数据文件位于 `/data/traffic_data.csv`，如需替换可直接覆盖
3. 可使用 `traffic_visualization.ipynb` 查看预测结果分布和模型性能图

---

## 📌 项目说明

本项目是作者职业转型过程中对“交通工程 + 数据建模”融合实践的探索，旨在构建可推广的交通流量预测与优化方案。

