# 📈 LSTM Time Series - Multivariate Stock Price Prediction

This project uses a **Long Short-Term Memory (LSTM)** model to predict future Google stock prices using a multivariate time series approach. The LSTM model is trained using historical stock data over a span of five years and forecasts future trends over a two-month window. The approach is useful for learning sequential patterns and long-term dependencies in stock market data.

---

## 🔍 Objective

To build and train a deep learning model using LSTM for accurate short-term forecasting of stock prices using historical daily stock data (open, high, low, close, volume).

---

## 📊 Dataset

- **Source**: [Yahoo Finance - Alphabet Inc. (GOOG)](https://finance.yahoo.com/quote/GOOG/history)
- **Features Used**:
  - Open Price
  - High Price
  - Low Price
  - Close Price
  - Adjusted Close
  - Volume

### ⏳ Time Periods Used:

| Phase        | Date Range           |
|--------------|----------------------|
| Training     | Jan 2019 – Jun 2023  |
| Validation   | Jul 2023 – Dec 2023  |
| Testing      | Jan 2024 – Feb 2024  |

---

## ⚙️ Project Pipeline

### ✅ PHASE 1 - Exploratory Data Analysis (EDA)

📁 `data-explanatory-analysis.ipynb`

- Load and inspect raw dataset.
- Generate summary statistics and visualize trends.
- Filter and store cleaned data for modeling.

---

### ⚙️ PHASE 2 - Data Preprocessing

📁 `data-preprocessing.ipynb`

- Handle missing values, validate data types.
- Select independent variables and target variable.
- Perform MinMax scaling to [0, 1].
- Split into training, validation, and test datasets.

---

### 🧠 PHASE 3 - Model Training and Inference

📁 `model-training.ipynb`

- Sequence generation for time series modeling.
- LSTM Model Architecture:
  - 4 LSTM layers (units=100)
  - 4 Dropout layers (rate=0.2)
  - Final Dense layer with 1 unit
- Compilation:
  - Optimizer: `Adam`
  - Loss Function: `Mean Squared Error`
- Training:
  - Epochs: `200`
  - Batch size: `64`
- Prediction and inverse scaling.
- Visualization of actual vs predicted prices.

---

## 🏗️ Model Architecture

```text
Input → LSTM → Dropout → LSTM → Dropout → LSTM → Dropout → LSTM → Dropout → Dense → Output
