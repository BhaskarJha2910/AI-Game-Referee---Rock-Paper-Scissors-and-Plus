# Churn Prediction using LSTM Sequence Modeling 

This project predicts customer churn using Long Short-Term Memory (LSTM) neural networks by modeling customer behavior as sequential data.

## Problem Statement
Customer churn is a major concern for subscription-based businesses. Traditional ML models fail to capture temporal patterns. This project uses LSTM to learn sequential behavior and predict churn effectively.

## Approach
- Convert customer activity into time-series sequences
- Train an LSTM-based deep learning model
- Predict churn probability for each customer

## Tech Stack
- Python
- TensorFlow / Keras
- NumPy, Pandas
- Scikit-learn
- Matplotlib
- Google Colab
## How to Run
1. Open `churn_lstm.ipynb` in Google Colab
2. Install dependencies using `requirements.txt`
3. Load dataset from `data/`
4. Train LSTM model
5. Predict churn probabilities

## Key Results
- Captures temporal behavior
- Improves churn prediction accuracy
- Suitable for subscription businesses