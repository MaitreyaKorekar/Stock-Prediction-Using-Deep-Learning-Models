## Stock Prediction Using Deep Learning Models

# Introduction
The project focuses on predicting stock prices using deep learning models, specifically Long Short-Term Memory (LSTM) and Gated Recurrent Unit (GRU) networks.

# Problem Statement
The aim is to develop an efficient model to forecast stock prices based on historical data and improve prediction accuracy using deep learning techniques.

# Data Collection and Preprocessing
Data Source: Yahoo Finance API (yfinance library)
Stock Ticker: Apple Inc. (AAPL)
Time Period: 10 years of daily historical stock prices
Selected Features: 
  ~ Close Price (Primary target variable)
  ~ 50-day & 200-day Simple Moving Averages (SMA) for trend analysis

# Preprocessing Steps:

Handling missing values using linear interpolation
Min-Max Scaling (0 to 1) to normalize data
Time-Series Transformation: Using the last 100 days to predict the next day's price

# Deep Learning Models: LSTM & GRU
Why RNNs? They efficiently handle sequential data.
Why LSTM & GRU over standard RNNs? They solve the vanishing gradient problem.
Key Differences:
LSTM: Uses a cell state + three gates (input, forget, output)
GRU: Uses a single update gate, making it more computationally efficient
Advantage: Both models retain long-term dependencies effectively.

# Model Architectures & Hyperparameter Tuning
Optimized Hyperparameters:
Epochs: 50 (with early stopping)
Batch Size: Tested 32, 64, 128 (Best: 64)
Learning Rate: 0.001, 0.0005, 0.0001 (Best: 0.001)
Dropout Rate: 0.2 (to prevent overfitting)
Optimizers Tried:
  ~ SGD and RMSprop (less effective)
  ~ Adam optimizer (Best Performance)

# Tuning Techniques:
Grid Search: Exhaustive search for best parameters
Random Search: Faster but slightly less accurate
Learning Rate Scheduling: Helps reduce overfitting

# Model Training & Performance Evaluation
The models were trained and evaluated using standard performance metrics and visualization techniques.

# Stock Price Forecasting (Results)
Prediction Strategy:
Use the last 100 days as input
Predict the next day's price
Append prediction to input and repeat for 10 days
Comparison with Actual Prices:
LSTM: Performed slightly better in trend-following
GRU: Provided close predictions with faster computation
Visualization:
Line charts comparing actual vs predicted stock prices
