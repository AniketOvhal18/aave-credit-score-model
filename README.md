# 🧠 DeFi Wallet Credit Scoring using Aave V2 (ML Model)

This project builds a machine learning pipeline that assigns **credit scores (0–1000)** to Ethereum wallets based on their interaction history with the **Aave V2 protocol**. It evaluates responsible vs. risky behavior by aggregating user actions such as `deposit`, `borrow`, `repay`, `redeem`, and `liquidation`.

> 📈 Model: Random Forest Regressor  
> 📦 Input: Aave V2 transaction-level JSON  
> 📊 Output: Per-wallet credit score (0–1000)

---

## 🚀 Objectives

- Load and preprocess raw Aave V2 JSON transaction data  
- Engineer wallet-level behavioral features  
- Assign rule-based credit scores  
- Train a machine learning model to predict credit scores  

---

## 📐 System Architecture

Raw JSON Data

#    ↓
Preprocessing & Flattening

#    ↓
Wallet-Level Feature Engineering

#    ↓
Rule-Based Scoring (Supervised Labels)

#    ↓
Random Forest Model Training

#    ↓
Predicted Credit Scores (0–1000)

---

## 📁 Folder Structure

aave-credit-score-model/
│

├── data/

│  └── aave_sample.json # Raw transaction data

├── notebooks/

│  └── aave_credit_score_rf.ipynb # Jupyter Notebook

├── requirements.txt # Python dependencies

└── README.md # You're here!

---
## ⚙️ How It Works

### 🧹 Preprocessing
- Parses nested JSON using `pd.json_normalize()`
- Converts `amount` and `priceUSD` to real dollar values
- Extracts timestamps, wallet addresses, and actions

### 🧠 Feature Engineering
Wallet-level features include:
- `sum`, `mean`, `count` of USD value per action
- Counts of `repay`, `liquidationcall`, etc.
- Activity duration per wallet

### 🎯 Rule-Based Score
Assigns a credit score using a basic function:

rule_based_score()

---
### 🤖 Model: Random Forest Regressor
- No scaling required

- Supports feature importance

- Robust to noise & missing values
---
### ✅ Evaluation Results

MAE =	          2.47

RMSE =	        11.65

R² =	          0.9919  

---

### 🧰 Tech Stack

# Python 3.x

- pandas

- scikit-learn (Random Forest)

- matplotlib & seaborn

- JSON for input, CSV for output



