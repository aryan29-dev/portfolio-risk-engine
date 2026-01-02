# Portfolio Risk Engine ⚙️

A Python-based portfolio analysis and optimization tool that uses **Monte Carlo simulation** to construct and evaluates a user-defined number of portfolios using historical market data (yFinance API), selecting the allocation that maximizes the **Sharpe ratio** (measures unit of return per unit of risk).

---

## Overview

The Portfolio Risk Engine:
- Downloads real historical price data (yfinance API)
- Converts prices into daily returns
- Simulates thousands of random portfolios (in this project - 5000)
- Evaluates risk and return metrics
- Selects the portfolio with the highest risk-adjusted performance (Sharpe Ratio)
- Visualizes results through equity curves and risk–return plots

The optimization is based on the Monte Carlo simulation method, meaning results vary slightly between runs as different random portfolios are sampled.

---

## Features

- **Data ingestion** using real market prices
- **Daily return calculation** from historical prices
- **Monte Carlo portfolio simulation** (long-only, fully invested)
- **Annualized Metrics**
  - Expected return
  - Volatility
  - Sharpe ratio
- **Risk Analysis**
  - Maximum drawdown (MDD)
  - Value at Risk (VaR)
  - Conditional Value at Risk (CVaR)
- **Visualization**
  - Optimal portfolio equity curve
  - Risk–return scatter of all simulated portfolios

---

## Project Structure

```text
portfolio-risk-engine/
├── src/
│   ├── main.py            # Runs Monte Carlo simulation and analysis
│   └── risk_engine.py     # Core financial and risk calculations
│
├── data/
│   └── prices.csv         # Historical price data
│
├── make_prices_csv.py     # Downloads and prepares price data
├── requirements.txt
└── README.md
```

## How It Works

1. **Extracting Price Data**
   - Historical daily prices are downloaded for a set of equities.
   - Prices are converted into simple daily returns.

2. **Monte Carlo Simulation**
   - Thousands of random weight vectors are generated.
   - Each portfolio is fully invested and long-only.
   - For each portfolio, return and risk metrics are computed.

3. **Optimization**
   - The portfolio with the **maximum Sharpe ratio** is selected.
   - This represents the best risk-adjusted allocation found in the sampled space.

4. **Evaluation**
   - The optimal portfolio’s equity curve is constructed.
   - Drawdown, VaR, and CVaR are calculated to assess downside risk. (how much the portfolio can lose during unfavorable market periods)

## Libraries Used

- NumPy
- pandas
- yfinance
- Matplotlib
