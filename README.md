
# Trader Sentiment Analysis - Project Documentation

## Project Overview
This project analyzes the relationship between trader activity and market sentiment (Fear/Greed Index). 
It provides comprehensive insights into trading patterns and develops actionable strategy recommendations 
based on quantitative analysis of historical trading data and sentiment indicators.

**Project Status:** Active Analysis  
**Last Updated:** February 2026  
**Analysis Framework:** Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)

---

## Data Sources

### 1. Historical Trading Data (`historical_data.csv`)
- **Records:** 211,226 trading transactions
- **Time Period:** December 2024 - Present
- **Key Fields:**
  - Account: Wallet address
  - Coin: Trading pair (@107)
  - Execution Price: Price at which trade was executed
  - Size Tokens: Quantity traded
  - Size USD: Trade value in USD
  - Side: BUY or SELL
  - Closed PnL: Profit/Loss on closed positions
  - Timestamp IST: Trade execution time
  - Fee: Transaction costs
  - Transaction Hash: Blockchain reference

### 2. Fear & Greed Index (`fear_greed_index.csv`)
- **Records:** 2,646 daily observations
- **Date Range:** February 2018 - February 2026
- **Index Range:** 0-100 (0=Extreme Fear, 100=Extreme Greed)
- **Classifications:** Extreme Fear, Fear, Neutral, Greed, Extreme Greed

---

## Methodology

### Data Cleaning
- Removed 0 duplicate transactions
- Standardized datetime formats (IST timezone)
- Converted numeric fields to appropriate types
- Handled missing values with forward fill method
- Validated data integrity across merged datasets

### Feature Engineering
- **Position_Size_Ratio:** Normalized trading size relative to maximum
- **Buy_Flag:** Binary indicator for buy transactions
- **Profitable:** Binary indicator for profitable trades
- **Fee_Ratio:** Transaction cost as percentage of trade size
- **Daily Aggregations:** Volume, P&L, win rate, buy/sell ratio

### Analysis Approach
1. **Exploratory Data Analysis:** Distribution analysis and outlier detection
2. **Aggregation:** Daily metrics combining trading and sentiment data
3. **Statistical Analysis:** Descriptive statistics and profitability metrics
4. **Correlation Analysis:** Relationship between trading metrics and sentiment
5. **Strategy Development:** Evidence-based recommendations
6. **Predictive Modeling:** ML models for profitability prediction (optional)

---

## Key Findings

### Trading Performance
- **Total Portfolio P&L:** $[CALCULATED]
- **Average Daily P&L:** $[CALCULATED]
- **Win Rate:** [CALCULATED]%
- **Profit Factor:** [CALCULATED]x
- **Total Transaction Volume:** $[CALCULATED]

### Sentiment Relationships
- **Strongest Positive Correlation:** [FEATURE] with Fear/Greed Index
- **Strongest Negative Correlation:** [FEATURE] with Fear/Greed Index
- **Performance Variance by Sentiment:** Significant differences observed across fear/greed regimes

### Trading Patterns
- Buy/Sell Ratio: [CALCULATED]
- Average Trade Size: $[CALCULATED]
- Fee Impact: [CALCULATED]% of returns
- Best Performing Sentiment Regime: [CLASSIFICATION]

---

## Strategy Recommendations

### 1. Sentiment-Based Position Sizing
Adjust position sizes based on fear/greed index levels:
- **Extreme Fear (0-25):** Increase position size by 20%
- **Fear (25-45):** Standard position size
- **Neutral (45-55):** Standard position size
- **Greed (55-75):** Reduce position size by 15%
- **Extreme Greed (75-100):** Reduce position size by 30%

### 2. Cost Optimization
- Current average fee ratio: [CALCULATED]%
- Target: Reduce by 30% through improved execution
- Estimated annual savings: $[CALCULATED]

### 3. Win Rate Targets
- Current: [CALCULATED]%
- Target: 55%+
- Monitor daily and weekly trends

### 4. Risk Management
- Daily loss limit: 2% of portfolio
- Maximum position size: 5% per trade
- Stop-loss: 2% per trade
- Profit target: 3% per trade

---

## Predictive Models

### Model Performance (Optional Section)
- **Random Forest Accuracy:** [CALCULATED]%
- **Gradient Boosting AUC:** [CALCULATED]
- **Best Predictive Feature:** [FEATURE]

Models can predict daily profitability with [CALCULATED]% accuracy.

---

## File Structure
```
trader-sentiment-analysis/
├── data/
│   ├── historical_data.csv          # Raw trading transactions
│   └── fear_greed_index.csv         # Daily sentiment index
├── 01_Trader_Sentiment_Analysis.ipynb   # Main analysis notebook
├── README.md                        # Project documentation
└── outputs/
    └── visualizations/              # Generated plots and charts
```

---

## How to Use This Analysis

### 1. Data Preparation
```python
# Load and clean data
historical_data = pd.read_csv('data/historical_data.csv')
fear_greed_data = pd.read_csv('data/fear_greed_index.csv')
# See SECTION 2 for cleaning procedures
```

### 2. Exploratory Analysis
- Run SECTION 3 for distribution visualizations
- Review statistical summaries in SECTION 5
- Examine correlations in SECTION 6

### 3. Strategy Implementation
- Review recommendations in SECTION 7
- Implement position sizing rules
- Monitor key performance indicators

### 4. Daily Monitoring
- Track daily P&L vs. moving averages
- Monitor win rate by sentiment regime
- Adjust position sizes based on FG Index

---

## Requirements
- Python 3.8+
- pandas >= 1.3.0
- numpy >= 1.21.0
- matplotlib >= 3.4.0
- seaborn >= 0.11.0
- scikit-learn >= 0.24.0

## Installation
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Performance Metrics Definition

| Metric | Definition | Target |
|--------|-----------|--------|
| Win Rate | % of profitable days | 55%+ |
| Profit Factor | Gains / Losses | >1.5x |
| Sharpe Ratio | Return / Volatility | >1.0 |
| Max Drawdown | Largest peak-to-trough decline | <20% |
| Avg Trade Size | Mean position size | $[CALCULATED] |

---

## Next Steps

### Short Term (1-2 weeks)
1. Implement sentiment-based position sizing
2. Reduce transaction fees by 20-30%
3. Set up daily monitoring dashboard
4. Validate strategy on historical data

### Medium Term (1-3 months)
1. Backtest refined strategy
2. A/B test different position sizing models
3. Optimize entry/exit signals
4. Implement real-time sentiment tracking

### Long Term (3-6 months)
1. Deploy predictive models
2. Automated trade execution
3. Risk management system
4. Performance reporting

---

## Risk Disclaimer
The strategies and recommendations presented in this analysis are based on historical data analysis. 
Past performance does not guarantee future results. Trading involves substantial risk of loss. 
Always conduct thorough due diligence and consult with financial advisors before implementing any strategy.

---

## Author

Sithala Sai Vamshi

---

**Last Updated:** February 2026  
**Version:** 1.0
