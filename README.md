# 📈 Thematic Quant Equity Portfolio: Advanced Risk & Allocation Optimizer

An institutional-grade quantitative portfolio optimization engine designed to build highly diversified, thematic equity baskets (e.g., AI Boom, Pharma GLP-1)[cite: 1]. The system upgrades standard Modern Portfolio Theory (Markowitz) with rigorous constraints and Machine Learning clustering to simulate real-world institutional compliance.

## 🎯 The Business Problem
A naive implementation of the Maximum Sharpe Ratio often results in **Corner Solutions**—the optimizer aggressively allocates the majority of capital (e.g., 90%+) into a single historical outlier stock (like NVIDIA), violating strict institutional diversification rules[cite: 1]. 
Furthermore, running optimization models on the same data used for testing introduces severe **Look-Ahead Bias**, rendering backtest results economically invalid[cite: 1].

## 💡 The Quant Solution
This script resolves these industry challenges through a robust Object-Oriented Programming (OOP) architecture[cite: 1], implementing three advanced quantitative techniques:

1. **L2 Regularization & Weight Bounds:** To enforce true diversification and simulate institutional compliance limits, the optimizer is constrained to a minimum weight of 5% and a maximum weight of 30% per asset[cite: 1]. An L2 regularization penalty (`gamma=0.1`) is injected into the objective function to actively penalize over-concentration[cite: 1].
2. **Look-Ahead Bias Elimination:** The data pipeline strictly splits the historical time-series into an **In-Sample / Train** period (2021-2024) for algorithm learning, and an **Out-of-Sample / Test** period (2025-2026) for blind backtesting[cite: 1].
3. **K-Means Risk Clustering:** Prior to optimization, unsupervised Machine Learning (K-Means) clusters assets based purely on their annualized volatility and expected returns, uncovering hidden behavioral correlations beyond traditional sector labels[cite: 1].

## 🛠 Technical Stack
* **Python** (OOP Architecture for scalable thematic testing)[cite: 1]
* **PyPortfolioOpt** (Max Sharpe, L2 Regularization, Efficient Frontier)[cite: 1]
* **yfinance & Pandas** (Data pipeline and robust NaN handling via forward-filling)[cite: 1]
* **Scikit-Learn** (StandardScaler, K-Means Clustering)[cite: 1]
* **NumPy** (Vectorized matrix operations / Dot products for high-speed backtesting)[cite: 1]

## 📊 The Algorithm in Action

### 1. Feature Engineering & Clustering
The system ingests raw Adjusted Close prices, converting them into stationary daily percentage returns[cite: 1]. It computes the annualized covariance matrix and groups the assets into 3 distinct Risk/Return clusters to inform structural diversification[cite: 1].

### 2. In-Sample Optimization
Using the training data, the `QuantPortfolio` class calculates the Efficient Frontier[cite: 1]. By applying the 30% cap and L2 regularization, it outputs a balanced allocation that captures the thematic mega-trend without exposing the fund to idiosyncratic single-stock ruin[cite: 1].

### 3. Out-of-Sample Backtest (Vectorized)
The weights generated from the past are rigidly applied to unseen future data[cite: 1]. The backtest avoids slow iterations by utilizing fully vectorized dot products between the daily returns matrix and the optimized weight array[cite: 1]. 

**Output visual analytics include:**
* A dual-axis chart featuring the Out-of-Sample **Equity Curve** (simulating a €10,000 initial investment)[cite: 1].
* An **Underwater Chart** dynamically tracking the Maximum Drawdown[cite: 1].

---
*Disclaimer: This repository is for educational and portfolio demonstration purposes only. It does not constitute financial advice.*
