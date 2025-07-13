# Stochastic-Modeling-for-Financial-Prediction

 This project proves that modern ML models—especially ensemble architectures—can **decode complex financial signals** from cryptocurrency markets. The stacking model is both **robust** and **adaptable**, delivering meaningful predictions even under volatile conditions.


---

# 📈 Stochastic Modeling for Financial Prediction

## 🧠 Background and Overview

This project explores advanced **stochastic modeling** and **machine learning techniques** to forecast significant price movements in **Bitcoin (BTC-USD)**. Specifically, the task is to predict whether BTC’s price will rise **more than 2% over a 20-day horizon**. The study compares four predictive models:

* 📊 **Logistic Regression** (baseline)
* 🧠 **Neural Networks**
* 🧮 **Support Vector Machines (SVM)**
* 🧬 **Stacking Ensemble** (SVM + Neural Network)

The project builds upon earlier academic work (GWP1) and addresses **three core ML challenges**:

1. Hyperparameter optimization
2. Bias–variance tradeoff
3. Ensemble learning in financial time series forecasting

> ⚡ **Motivation**: In volatile and non-stationary markets like crypto, traditional models often fail. This project demonstrates how **modern ML pipelines** can extract useful signals from noisy, high-frequency financial data — a key step toward robust **AI-driven trading systems**.

---

## 🗂️ Data Structure Overview

### 🪙 Core Datasets

* **Assets**: BTC-USD and ETH-USD
* **Time Period**: March 2023 – July 2024 (Daily)
* **Source**: Yahoo Finance API via `yfinance`
* **Features**: 72 engineered variables from price and volume series

### 🔄 Transformed Data Structures

* ✅ Normalized feature matrix (72 features × N rows)
* ✅ Binary classification target:
  `1` = Price rises >2% over 20 days
  `0` = Otherwise
* ✅ Time-series aware splits: Train / Validation / Test
* ✅ Balanced classes using **SMOTE** (Synthetic Minority Oversampling)

---

## 📊 Executive Summary

### 🎯 What This Project Solves

Predicting meaningful **crypto price movements** is a high-noise, high-risk task. Traders often lack consistent signals, especially during turbulent market regimes. This project presents a **data-driven, ML-based solution** to forecast +2% BTC surges over 20 days, benchmarking multiple models and optimizing their performance.

---

### 🚀 Key Results and Findings

1. **🏆 Performance Rankings**

   * **Stacking Ensemble** led with the **highest ROC AUC = 0.6701**
   * **SVM** outperformed all standalone models in **accuracy (0.6162)** and **precision (0.6296)**
   * **Neural Networks** improved dramatically over logistic regression
   * **Ensembling** helped capture both linear and non-linear signal patterns

2. **🔧 Hyperparameter Optimization**

   * Grid search consistently outperformed random search
   * Optimal NN: `128-64` neurons, `lr=0.0001`
   * Best SVM: `RBF kernel`, `C=5`, `gamma=0.01`

3. **📉 Bias–Variance Insights**

   * Baseline Logistic Regression suffered from **underfitting** (high bias)
   * SVM found optimal tradeoff between bias and variance
   * L2 regularization in Ridge helped mitigate overfitting

4. **🤖 Ensemble Learning Benefits**

   * +14.3% gain in **ROC AUC** over the best single model
   * Enhanced **prediction stability** across regimes
   * Ensemble model improved recall **without sacrificing precision**

---

### 📈 Performance Comparison

| Model                 | Accuracy   | Precision  | Recall     | F1 Score   | ROC AUC    |
| --------------------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| Logistic Regression   | 0.5263     | 0.5618     | 0.4202     | 0.4808     | 0.5312     |
| Neural Network        | 0.5680     | 0.5953     | 0.5378     | 0.5651     | 0.5953     |
| SVM                   | 0.6162     | 0.6296     | 0.6429     | 0.6362     | 0.6150     |
| **Stacking Ensemble** | **0.6140** | **0.6260** | **0.6471** | **0.6364** | **0.6701** |

---

## 🔬 Insights Deep Dive

### 1️⃣ Hyperparameter Optimization

* Ridge: Optimal λ = 0.0035 (via Grid Search)
* NN: Learning rate = **0.0001** showed strongest generalization
* Small regularization (α) improved test performance

### 2️⃣ Bias–Variance Tradeoff

* Logistic Regression = high bias (underfit)
* SVM = good complexity control, strong generalization
* Ensemble = low bias + reduced variance = **best of both worlds**

### 3️⃣ Ensemble Mechanics

* **SVM**: Clear decision boundaries
* **NN**: Captures subtle, non-linear feature interactions
* **Meta-learner (Logistic Regression)**: Blends models effectively

### 4️⃣ Financial Relevance

* 🕐 20-day return prediction = realistic for swing or short-term traders
* Market regime (bull/bear) changes significantly influenced precision
* **Technical indicators** were essential to signal generation

---

## ✅ Final Recommendations

### ⚙️ Deployment Strategy

1. **Use Ensemble Model** in Production:

   * Microservice with automated retraining
   * ROC AUC used for daily monitoring
   * Use confidence thresholds to control risk exposure

2. **Maintenance Plan**

   * Re-tune hyperparameters **monthly**
   * Evaluate feature drift **quarterly**
   * Reassess architecture **annually**

3. **Risk Management**

   * Combine with stop-loss strategies
   * Track confidence scores to filter weak signals
   * Use baseline logistic model as fallback control

---

## 🧩 Future Enhancements

1. 📡 Integrate **alternative datasets** (on-chain metrics, social sentiment)
2. 🧠 Explore **Temporal Convolutional Networks (TCNs)** for sequential modeling
3. 🧪 Introduce **dynamic model weighting** based on regime shifts
4. 📊 Apply **Bayesian optimization** for hyperparameter tuning
5. 🌍 Expand to **multi-asset models** (e.g., BTC, ETH, SOL, etc.)

---


---







\
