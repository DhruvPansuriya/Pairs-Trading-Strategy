# Quantum Spread: A Cointegration-Based Pairs Trading Framework

A sophisticated market-neutral trading strategy that exploits statistical relationships between cointegrated asset pairs to generate consistent returns regardless of market direction.

## 📊 Project Overview

This project implements a systematic pairs trading strategy using cointegration analysis to identify and trade mean-reverting relationships between stocks. The strategy is designed to be market-neutral, profiting from relative price movements while minimizing exposure to overall market risk.

### Key Features
- **Statistical Arbitrage**: Exploits temporary price divergences between cointegrated pairs
- **Market Neutral**: Profits in bull, bear, and sideways markets
- **Risk Management**: Built-in stop-loss and position sizing controls
- **Automated Signals**: Z-score based entry and exit conditions
- **Comprehensive Backtesting**: 3-year out-of-sample performance validation

## 🔧 Technical Implementation

### Methodology
1. **Pair Selection**: Engle-Granger two-step cointegration test on 25 IT sector stocks
2. **Signal Generation**: Z-score based trading signals with dynamic thresholds
3. **Position Sizing**: Dynamic capital allocation maintaining market neutrality
4. **Risk Management**: 5% stop-loss with continuous portfolio rebalancing

### Mathematical Framework
- **Spread Calculation**: `spread_t = P^A_t - β * P^B_t`
- **Z-Score**: `Z_t = (spread_t - μ_t) / σ_t`
- **Entry Signals**: Long A/Short B when Z < -1, Short A/Long B when Z > 1
- **Exit Signals**: Close positions when |Z| < 0.25

## 📈 Performance Metrics

### Backtesting Period
- **Selection Period**: April 2019 - March 2022
- **Trading Period**: April 2022 - March 2025
- **Initial Capital**: ₹1,00,000

### Key Results
- **Strategy Type**: Market-neutral statistical arbitrage
- **Risk Management**: 5% stop-loss per position
- **Rebalancing**: Dynamic position sizing on signal events
- **Diversification**: Equal capital allocation across selected pairs

## 🛠️ Installation & Usage

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn
pip install yfinance statsmodels scipy
pip install jupyter notebook
```

### Quick Start
1. Clone the repository:
```bash
git clone https://github.com/yourusername/quantum-spread-pairs-trading.git
cd quantum-spread-pairs-trading
```

2. Run the Jupyter notebook:
```bash
jupyter notebook pairs_trading_strategy.ipynb
```

3. Execute cells in order to:
   - Download historical data
   - Perform cointegration tests
   - Generate trading signals
   - Run backtesting analysis


## 📊 Visualizations

- **Equity Curve**: Cumulative portfolio returns over time
- **Spread Evolution**: Price spread behavior and mean reversion
- **Z-Score Bands**: Signal generation with entry/exit points
- **Trade Analysis**: Individual trade performance metrics
- **Risk Metrics**: Drawdown analysis and volatility measures

## 🎯 Strategy Logic

### Entry Conditions
- **Long Position**: Enter when spread Z-score < -1 (Stock A undervalued)
- **Short Position**: Enter when spread Z-score > 1 (Stock A overvalued)

### Exit Conditions
- **Mean Reversion**: Close when |Z-score| < 0.25
- **Stop Loss**: Close if position loss exceeds 5%
- **Cointegration Break**: Exit if statistical relationship deteriorates

### Risk Management
- Equal capital allocation across pairs
- Dynamic hedging to maintain market neutrality
- Continuous monitoring of cointegration relationships
- Portfolio rebalancing on signal events

## 📚 Research & References

This implementation is based on established academic research in statistical arbitrage:

- Engle-Granger Cointegration Methodology
- Mean Reversion in Financial Markets
- Statistical Arbitrage Theory
- Risk Management in Pairs Trading

### Academic Sources

- QuantInsti: [Pairs Trading Basics](https://blog.quantinsti.com/pairs-trading-basics/)
- Hudson Thames: [Introduction to Cointegration](https://hudsonthames.org/an-introduction-to-cointegration/)
- Educational Video Lecture: [Pairs Trading Strategy](https://youtu.be/g-qvFjvyqcs?t=266)
