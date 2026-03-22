# 📈 Momentum Strategy Backtest — SPY (2015–2024)

Backtest d'une stratégie momentum sur le S&P 500.
Signal : rendement sur 12 mois. Position longue si positif, cash sinon.

## Résultats

| Métrique | Stratégie | Buy & Hold |
|---|---|---|
| Rendement annualisé | ~X% | ~X% |
| Sharpe Ratio | X.XX | X.XX |
| Max Drawdown | -X% | -X% |

![Performance](assets/performance.png)

## Approche

- **Données** : prix ajustés SPY via `yfinance` (2015–2024)
- **Signal** : momentum 252 jours (≈ 12 mois)
- **Règle** : long si momentum > 0, cash sinon
- **Anti look-ahead bias** : signal décalé d'un jour (`shift(1)`)

## Stack

Python · pandas · numpy · matplotlib · yfinance · Jupyter

## Lancer le notebook

pip install -r requirements.txt
jupyter notebook momentum_backtest.ipynb