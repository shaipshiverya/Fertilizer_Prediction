# 🌱 Fertilizer Recommendation Analysis

A beginner-level agriculture data analytics project exploring soil nutrients, crop types, and fertilizer recommendations.

---

## 📌 Project Overview

Incorrect fertilizer use is one of the biggest challenges in Indian agriculture — overuse degrades soil, underuse reduces yield[cite: 2]. This project analyzes soil nutrient data and environmental conditions to understand which factors drive fertilizer recommendations and build a simple prediction model[cite: 2].

**Domain:** Agriculture / Precision Farming[cite: 2]  
**Tools:** Python, pandas, matplotlib, seaborn, Plotly, scikit-learn[cite: 2]  
**Dataset:** [Fertilizer Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/gdabhishek/fertilizer-prediction)[cite: 2]

---

## 📂 Dataset

| Feature | Description |
| :--- | :--- |
| Temparature | Soil temperature (°C)[cite: 2] |
| Humidity | Air humidity (%)[cite: 2] |
| Moisture | Soil moisture (%)[cite: 2] |
| Soil Type | Type of soil (Clayey, Loamy, Sandy, etc.)[cite: 2] |
| Crop Type | Type of crop grown[cite: 2] |
| Nitrogen | Soil Nitrogen level[cite: 2] |
| Potassium | Soil Potassium level[cite: 2] |
| Phosphorous | Soil Phosphorous level[cite: 2] |
| Fertilizer Name | Recommended fertilizer (Target)[cite: 2] |

---

## 🚧 Challenges Faced

*   **Column name whitespace** — The `Humidity` column had a trailing space (`'Humidity '`)[cite: 2]. This caused silent errors in groupby operations[cite: 2]. Fixed with `df.columns = df.columns.str.strip()`[cite: 2].
*   **Multiclass target** — Unlike binary classification (stroke yes/no), this project has 7 fertilizer classes to predict[cite: 2]. Required `stratify=y` in train/test split to ensure all classes appear in both sets[cite: 2].
*   **Small dataset** — Only 99 records total[cite: 2]. This limits model reliability but makes EDA patterns very clear and interpretable[cite: 2].
*   **ML-heavy first version** — Initial approach had too much feature engineering and complex pipelines[cite: 2]. Rebuilt to keep it simple, readable, and explainable[cite: 2].

---

## 📊 Key Findings

1. **Nitrogen** is the #1 predictor — low Nitrogen → Urea recommended[cite: 2].
2. **Phosphorous deficiency** → DAP recommended (consistent with real agronomic practice)[cite: 2].
3. **Crop Type** matters as much as soil nutrients[cite: 2].
4. **Soil Type** interacts strongly with NPK levels[cite: 2].
5. **Temperature and humidity** are secondary signals — nutrients dominate[cite: 2].

---

## 🧠 Model

| Detail | Value |
| :--- | :--- |
| **Algorithm** | Random Forest Classifier[cite: 2] |
| **Train/Test Split** | 80% / 20%[cite: 2] |
| **Classes** | 7 fertilizer types[cite: 2] |
| **Class Handling** | class_weight='balanced'[cite: 2] |

---

## 📁 Project Structure

```text
Fertilizer_Prediction/
│
├── Fertilizer_Prediction_v2.ipynb   # Main notebook
├── Fertilizer_Prediction.csv
└── README.md
