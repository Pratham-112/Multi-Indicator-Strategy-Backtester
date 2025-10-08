# Multi-Indicator Strategy Backtester (RSI + Bollinger Bands + Parabolic SAR)

A Python **rule-based trading strategy** that combines **RSI**, **Bollinger Bands**, and **Parabolic SAR** to generate entry/exit signals and backtest them on historical data.

## 📈 Strategy Logic
- **Enter long** when:
  - (RSI < 35 AND price < lower band) **OR**
  - (RSI < 25 AND price > SAR)      ← stricter RSI for SAR-only trigger
- **Exit** when:
  - RSI > 65 **OR**
  - price > upper band **OR**
  - price < SAR

## ⚙️ Parameters
- RSI period: 14
- Bollinger Bands: period 20, 2σ
- Parabolic SAR: step 0.02, max 0.2
- Commission: 0.10% (configurable)
- Initial cash: 1,000,000
- Position sizing: PercentSizer

## 📊 Features
- Backtest built in **Backtrader**
- Generates performance metrics (Sharpe, Max Drawdown, SQN, etc.)
- Visualizes equity curve & trades with indicator overlays
- Shows impact of graduated RSI thresholds to control over-trading

## 📊 Backtest Results (Sample Run)

| Metric              | Value       |
|---------------------|-------------|
| Start Value         | ₹1,000,000  |
| End Value           | ₹992,144    |
| Cumulative Return   | –0.79 %     |
| Sharpe Ratio        | –1.48       |
| Max Drawdown        | –1.40 %     |
| Total Trades        | 6 (3 winners / 3 losers) |
| Avg Win / Loss      | +₹2,569  / –₹5,188 |
| Net P&L             | –₹7,855     |
| SQN                 | –0.61       |

> Strategy currently slightly unprofitable but **demonstrates multi-indicator signal generation, risk control and full analytics**.

> ⚠️ **Disclaimer:** Educational / research project only – not investment advice.
