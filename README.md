# Stock-Price-Predictor
The model is capable of learning from multi-feature, sequential financial data, making it suitable for short-term return prediction tasks.
Its architecture, with stacked LSTM layers and dropout, is designed to handle overfitting and capture both short- and long-term dependencies.
The reported MAE indicates a relatively low average prediction error for the next day's log return, demonstrating reasonable predictive accuracy for a volatile financial time series

**Overview:**
The Stock Price Predictor model is a deep learning-based time series forecasting system designed to predict the next day's log return of ITC stock prices. It leverages historical stock data and advanced neural network techniques to model complex temporal dependencies in financial data.

**Key Features:**
Utilizes two years of historical daily data for ITC stock (ITC.NS), including Open, High, Low, Close, and Volume features.   
Computes the daily log return as the primary target variable.   
Input features include standardized values of Open, High, Low, Close, Volume, and the previous day's log return.
Standardizes all features using StandardScaler for improved neural network performance.    
Constructs input sequences of 60 consecutive days for each prediction, enabling the model to capture long-term temporal patterns.

**Data Preprocessing:**
Standardizes all features using StandardScaler for improved neural network performance.   
Constructs input sequences of 60 consecutive days for each prediction, enabling the model to capture long-term temporal patterns.

**Model Architecture:**
Type: Sequential LSTM (Long Short-Term Memory) neural network.

**Layers:**
First LSTM layer with 50 units, returning sequences.  
Dropout layer (rate 0.2) for regularization.    
Second LSTM layer with 50 units.    
Second Dropout layer (rate 0.2).
Dense output layer with 1 unit for regression.

**Training and Validation:**
Train/Test Split: 80% training, 20% testing, maintaining chronological order (no shuffling).    
Optimizer: Adam.   
Loss Function: Mean Squared Error (MSE).    
Epochs: 10.    
Batch Size: 32.

**Prediction and Evaluation:**
Predicts the next day's log return on the test set.    
Performance Metric: Mean Absolute Error (MAE) on the test set is 0.009357
