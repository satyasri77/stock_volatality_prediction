# Prediction of Stock Volatility Using GARCH and LSTM

The goal of this project is to predict the **future volatility of the S&P 500 index using historical market data.**

To achieve this, we combine the strengths of two powerful models — GARCH and LSTM — to build a hybrid architecture that captures both statistical and deep learning insights.

**Why Combine GARCH and LSTM?**
Both models are individually strong in modeling volatility, but they excel in different ways:

GARCH (Generalized Autoregressive Conditional Heteroskedasticity)
Captures volatility clustering and provides conditional volatility estimates
Models the persistence and shocks in market volatility using past squared returns
Produces residuals and volatility estimates that serve as engineered features
LSTM (Long Short-Term Memory)
Learns non-linear patterns in time series
Remembers long-term dependencies in sequential data
Uses a sliding window of past information to predict future behavior

By feeding GARCH outputs (volatility and standardized residuals) into an LSTM, we create a hybrid model that leverages the strengths of both approaches.

**Depedent variable** 
On a given day t, the model predicts the realized volatility of the S&P 500 over the next 5 trading days — that is, from t+1 to t+5.
This target is calculated as the 5-day rolling standard deviation of log returns, shifted backward by one step to align with the prediction input.

