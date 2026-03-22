# Momentum Strategy Backtest — Multi-Asset (2015–2024)

Backtest of a 12-month momentum strategy across 4 asset classes.
Signal: go long if the 12-month return is positive, stay in cash otherwise.

## Results

### Multi-Asset Performance
| Asset | Strategy | Buy & Hold | Sharpe | Max Drawdown | In Market |
|---|---|---|---|---|---|
| S&P 500 (SPY) | 8.4% | 13.3% | 0.53 | -31.2% | 75% |
| Nasdaq 100 (QQQ) | 12.7% | 18.6% | 0.64 | -31.2% | 76% |
| Gold (GLD) | 2.9% | 7.6% | 0.13 | -33.3% | 62% |
| Bonds (BND) | 1.9% | 1.4% | 0.00 | -8.7% | 57% |

### Momentum Window Comparison — SPY
| Window | Ann. Return | Sharpe | Max Drawdown | In Market |
|---|---|---|---|---|
| 3 months | 6.8% | 0.46 | -23.7% | 74% |
| 6 months | 7.6% | 0.51 | -23.3% | 75% |
| 12 months | 8.4% | 0.53 | -31.2% | 75% |

## Charts

![Performance](assets/performance.png)
![Drawdown](assets/drawdown.png)
![Window Comparison](assets/window_comparison.png)

## Key Findings

- Momentum works best on **equities** (QQQ: 12.7% annualized) vs commodities or bonds
- Bonds (BND) is the only asset where the strategy **beats Buy & Hold** (1.9% vs 1.4%)
- Longer lookback windows (12M) maximize returns but increase drawdown vs shorter windows (3M: -23.7%)
- The strategy is in cash 25-38% of the time, providing meaningful downside protection

## Approach

- **Data**: Adjusted closing prices via `yfinance` (2015–2024)
- **Signal**: N-day momentum — long if positive, cash otherwise
- **Look-ahead bias prevention**: signal shifted by 1 day (`shift(1)`)
- **Assets**: SPY, QQQ, GLD, BND

## Stack

Python · pandas · numpy · matplotlib · yfinance · Jupyter

## Run it

pip install pandas numpy matplotlib yfinance jupyter
jupyter notebook momentum_backtest.ipynb