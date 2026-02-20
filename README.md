# Stock Direction Prediction Using Time-Series Machine Learning

## Overview

This project builds an end-to-end time-series machine learning pipeline to predict next-day stock price direction (up/down) using technical indicators.

The goal is not profitability, but to explore signal strength, model generalization, and overfitting behavior in financial data.

---

## Dataset

Historical OHLCV stock data including:
- Open
- High
- Low
- Close
- Volume

Daily frequency.

---

## Feature Engineering

Engineered rolling time-series features:

- 5-day Moving Average (MA5)
- 20-day Moving Average (MA20)
- 5-day Rolling Volatility
- Daily Returns

Target variable:
- Binary classification (1 = next day up, 0 = next day down)
- Created using forward shift to prevent data leakage

---

## Modeling Approach

- Time-aware train/test split (no shuffling)
- Random Forest Classifier
- Regularization applied (max_depth, min_samples_split)
- Out-of-sample evaluation

---

## Results

- Training Accuracy: ~53%
- Testing Accuracy: ~47%

Findings:
- Model overfitted without regularization
- Limited predictive signal at daily frequency
- Market direction appears close to random under current features

---

## Key Learnings

- Importance of preventing data leakage in time-series ML
- Diagnosing overfitting via train vs test comparison
- Feature engineering limitations in noisy financial data
- Proper evaluation of baseline vs model performance

---

## Future Improvements

- Add lagged return features
- Incorporate volume-based indicators
- Test Logistic Regression baseline
- Implement time-series cross-validation
- Backtest trading strategy performance

---

## Tech Stack

- Python
- Pandas
- Matplotlib
- Scikit-learn
