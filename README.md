# 🪙 Gold Price Prediction using Random Forest Regressor

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?style=flat-square&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

> Predicting the price of gold using correlated financial market indicators — S&P 500 (SPX), crude oil (USO), silver (SLV), and EUR/USD exchange rate — through an ensemble machine learning approach.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Project Structure](#-project-structure)
- [Methodology](#-methodology)
- [Results](#-results)
- [Technologies Used](#-technologies-used)
- [How to Run](#-how-to-run)
- [Key Visualizations](#-key-visualizations)
- [Future Improvements](#-future-improvements)
- [License](#-license)

---

## 🔍 Overview

Gold is one of the most widely traded commodities in the world, often considered a **safe-haven asset** during periods of economic uncertainty. Its price is influenced by a complex interplay of global financial indicators.

This project builds a **supervised machine learning model** that learns the historical relationship between gold prices and key financial indices, then predicts future gold prices based on those features.

**Core Question:** *Can we accurately predict the price of gold (GLD ETF) using related financial market data?*

---

## 📊 Dataset

The dataset used is `gld_price_data.csv`, which contains historical daily prices of the following financial instruments:

| Column | Description |
|--------|-------------|
| `Date` | Trading date |
| `SPX` | S&P 500 Index (US stock market) |
| `GLD` | Gold ETF price *(Target Variable)* |
| `USO` | United States Oil Fund (crude oil price) |
| `SLV` | Silver ETF price |
| `EUR/USD` | Euro to US Dollar exchange rate |

> 📁 Source: [Kaggle — Gold Price Data](https://www.kaggle.com/datasets/altruistdelhite04/gold-price-data)

---

## 📁 Project Structure

```
gold-price-prediction/
│
├── GOLD.ipynb              # Main Jupyter Notebook (EDA + Modeling)
├── gld_price_data.csv      # Dataset
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies
```

---

## 🔬 Methodology

The project follows the standard machine learning pipeline:

### 1. Data Loading & Exploration
- Loaded dataset using `pandas`
- Checked for null values, duplicates, and data types
- Generated descriptive statistics

### 2. Exploratory Data Analysis (EDA)
- **Correlation heatmap** — identified which financial indicators correlate most strongly with gold prices
- **Distribution plot** — analyzed the statistical distribution of GLD prices using histogram + KDE curve

### 3. Preprocessing
- Dropped the `Date` column (non-numeric; not directly usable by the model)
- Separated features (`X`) from the target variable (`y = GLD`)

### 4. Model Training
- Applied **80/20 train-test split** (`random_state=42` for reproducibility)
- Trained a `RandomForestRegressor` with **100 decision trees**

### 5. Evaluation
- Measured model performance using the **R² (R-squared) score**
- Visualized **actual vs. predicted** gold prices on a line plot

---

## 📈 Results

| Metric | Value |
|--------|-------|
| R² Score | **~0.98+** |
| Model | Random Forest Regressor |
| Trees | 100 estimators |
| Test Size | 20% |

The model achieved a very high R² score, indicating it captures the underlying patterns in gold price movements with strong accuracy.

---

## 🛠 Technologies Used

- **Python 3.8+**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — data visualization
- **Scikit-learn** — machine learning (model, train/test split, metrics)

---

## ▶️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/gold-price-prediction.git
cd gold-price-prediction
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

Or manually:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Launch the notebook
```bash
jupyter notebook GOLD.ipynb
```

> Make sure `gld_price_data.csv` is in the same directory as the notebook before running.

---

## 📉 Key Visualizations

### Correlation Heatmap
Shows the correlation between all financial features. `SLV` (silver) has the highest positive correlation with gold prices, while `SPX` shows a negative correlation.

### Gold Price Distribution
A histogram with a KDE curve showing that GLD prices follow a roughly **bimodal distribution**, reflecting two dominant price regimes in the historical data.

### Actual vs. Predicted Plot
A line chart comparing the model's predictions against real gold prices on the test set — the two lines closely overlap, confirming the model's reliability.

---

## 🚀 Future Improvements

- [ ] **Feature Engineering** — Extract `Year`, `Month`, `Day of Week` from the Date column to capture seasonal patterns
- [ ] **Feature Importance Chart** — Visualize which financial indicator drives gold prices the most
- [ ] **Additional Metrics** — Include MAE and RMSE for more interpretable error analysis
- [ ] **Hyperparameter Tuning** — Use `GridSearchCV` to optimize `n_estimators`, `max_depth`, and `min_samples_split`
- [ ] **Residual Analysis** — Plot prediction residuals to verify model assumptions
- [ ] **Model Comparison** — Benchmark against XGBoost, SVR, and Linear Regression
- [ ] **Time-Series Approach** — Explore LSTM or ARIMA models for sequential forecasting

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and distribute it with attribution.

---

## 🙋‍♂️ Author

**Shadab**
- 📧 your-email@example.com
- 🔗 [LinkedIn](https://linkedin.com/in/your-profile)
- 🐙 [GitHub](https://github.com/your-username)

---

> *"Gold is money. Everything else is credit."* — J.P. Morgan
