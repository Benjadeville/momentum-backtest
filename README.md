# Momentum Strategy Backtest — SPY (2015–2024)

Backtest of a 12-month momentum strategy on the S&P 500 ETF (SPY).
Signal: go long if the 12-month return is positive, stay in cash otherwise.

## Results

| Metric | Strategy | Buy & Hold |
|---|---|---|
| Annualized Return | 8.4% | 13.3% |
| Sharpe Ratio | 0.53 | 0.67 |
| Max Drawdown | -31.2% | -33.7% |
| Days invested | 75% | 100% |

![Performance](assets/performance.png)

## Key Findings

The momentum strategy reduces max drawdown (-31.2% vs -33.7%) by staying in cash
during bearish periods (25% of the time). However, it underperforms Buy & Hold on
raw returns over this period — an honest and realistic result consistent with
academic literature on trend-following strategies.

## Approach

- **Data**: Adjusted closing prices for SPY via `yfinance` (2015–2024)
- **Signal**: 252-day momentum (≈ 12 months)
- **Rule**: Long if momentum > 0, cash otherwise
- **Look-ahead bias prevention**: signal shifted by 1 day (`shift(1)`)

## Stack

Python · pandas · numpy · matplotlib · yfinance · Jupyter

## Run it

pip install pandas numpy matplotlib yfinance jupyter
jupyter notebook momentum_backtest.ipynb