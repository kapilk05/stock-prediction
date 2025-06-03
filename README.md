# Stock Forecasting and Event Impact Analysis Using Time Series Models

## Overview

This project provides a comprehensive analysis of Big Tech stock performance over a 15-year period (2010-2025), combining multiple analytical approaches including time series forecasting, event study analysis, risk modeling, and portfolio optimization. The analysis focuses on five major technology stocks: Apple (AAPL), Amazon (AMZN), Google (GOOGL), Microsoft (MSFT), and NVIDIA (NVDA).

## Key Features

- **Time Series Forecasting**: Implementation of Facebook Prophet and ETS models with ensemble techniques
- **Event Study Analysis**: COVID-19 market crash impact assessment using abnormal returns
- **Risk Modeling**: GARCH(1,1) modeling with Student-t innovations for volatility forecasting
- **Portfolio Optimization**: Multiple allocation strategies with Monte Carlo simulations
- **Interactive Dashboard**: Power BI dashboard for visualizing insights and performance metrics

## Project Highlights

### 📈 Key Findings

- **NVIDIA's Exceptional Performance**: 300× indexed price growth, far outpacing other tech giants (10-40× growth)
- **Volatility Patterns**: NVDA exhibited highest volatility (~8% at peaks) while AAPL and MSFT remained most stable
- **COVID-19 Impact**: All five stocks showed positive Cumulative Abnormal Returns during Feb-Mar 2020 crash
- **Forecasting Accuracy**: ETS models outperformed Prophet on 4 out of 5 tickers

### 🔍 Analysis Components

1. **Exploratory Data Analysis**
   - Price trend analysis with linear and indexed scaling
   - Rolling volatility calculations (30-day windows)
   - Return distribution analysis with fat-tail identification

2. **Correlation & Factor Analysis**
   - Pairwise correlation matrix (0.48-0.64 range)
   - Principal Component Analysis revealing market factors
   - Factor structure identification (Market, NVDA differential, AAPL vs AMZN)

3. **Event Study: COVID-19 Market Crash**
   - Estimation window: Jan 2019 - Feb 2020
   - Event window: Feb 20 - Mar 31, 2020
   - Abnormal returns calculation using market model

4. **Time Series Forecasting**
   - ARIMA modeling on daily log-returns
   - ETS (Exponential Smoothing) on price series
   - Facebook Prophet with seasonality components
   - Inverse-MAPE ensemble methodology

5. **Risk Modeling**
   - GARCH(1,1) implementation with Student-t innovations
   - Value-at-Risk (VaR₉₅) and Expected Shortfall calculations
   - 1-day ahead volatility forecasting

6. **Portfolio Construction**
   - Four allocation strategies (Equal, Inverse-Risk, Return-Based, MV-Optimized)
   - Monte Carlo simulations (5,000 paths)
   - Multi-horizon analysis (1 month to 10 years)

## Technical Implementation

### Models Used

- **Facebook Prophet**: Handles seasonality and changepoints effectively
- **ETS (Exponential Smoothing)**: Superior performance on trend extrapolation
- **GARCH(1,1)**: Volatility clustering and risk measurement
- **Ensemble Methods**: Inverse-MAPE weighting for improved accuracy

### Evaluation Metrics

- **RMSE (Root Mean Square Error)**: Primary accuracy measure
- **MAPE (Mean Absolute Percentage Error)**: Relative error assessment
- **VaR₉₅ and ES₉₅**: Risk measurement at 95% confidence level
- **Cumulative Abnormal Returns (CAR)**: Event impact quantification

## Data

**Source**: Kaggle dataset  
**Period**: January 1, 2010 - January 1, 2025  
**Frequency**: Daily  
**Tickers**: AAPL, AMZN, GOOGL, MSFT, NVDA  
**Fields**: Date, Open, High, Low, Close, Volume  

## Results Summary

### Forecasting Performance
- ETS models demonstrated superior performance on 4/5 tickers
- GOOGL ensemble achieved ~50% reduction in RMSE and MAPE
- Ensemble techniques most beneficial for moderately predictable stocks

### COVID-19 Event Study Results
- **NVDA**: +40% Cumulative Abnormal Returns
- **AMZN**: +30% CAR
- **AAPL/MSFT**: ~+20% CAR each
- **GOOGL**: +10% CAR

### Risk Metrics (1-day VaR₉₅)
- **AAPL**: -2.1% (most stable)
- **NVDA**: -3.6% (highest risk)
- All stocks exhibited fat-tailed return distributions

### Portfolio Optimization
- No single strategy dominates across all time horizons
- Return-based and Inverse-Risk strategies excel at medium terms
- Constrained Mean-Variance optimization performs best long-term
- NVDA concentration risk managed through 30% allocation caps

## Business Impact

This analysis provides actionable insights for:
- **Investment Strategy**: Horizon-specific allocation recommendations
- **Risk Management**: Quantified tail-risk exposure across Big Tech
- **Market Timing**: Event-driven performance patterns
- **Diversification**: Correlation-based portfolio construction

## Future Enhancements

- Dynamic (time-varying) allocation strategies
- Regime-switching GARCH models
- Alternative risk measures (CVaR, Maximum Drawdown)
- Real-time model updating and backtesting
- Extended universe of technology stocks

## Technical Stack

- **Programming**: Python, R
- **Time Series**: Prophet, statsmodels, ETS
- **Risk Modeling**: GARCH, scipy.stats
- **Visualization**: Power BI, matplotlib, seaborn
- **Data Processing**: pandas, numpy
- **Statistical Analysis**: scikit-learn, PCA

## Repository Structure

```
├── data/
│   ├── raw/                 # Original stock data
│   └── processed/           # Cleaned and engineered features
├── notebooks/
│   ├── 01_exploratory_analysis.ipynb
│   ├── 02_correlation_pca.ipynb
│   ├── 03_event_study.ipynb
│   ├── 04_forecasting.ipynb
│   ├── 05_risk_modeling.ipynb
│   └── 06_portfolio_optimization.ipynb
├── src/
│   ├── data_processing.py
│   ├── forecasting_models.py
│   ├── risk_models.py
│   └── portfolio_optimization.py
├── results/
│   ├── forecasts/
│   ├── risk_metrics/
│   └── portfolio_simulations/
├── dashboard/
│   └── big_tech_analysis.pbix
└── README.md
```

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/big-tech-stock-analysis.git
   cd big-tech-stock-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the analysis**
   ```bash
   python src/main.py
   ```

4. **Open Power BI dashboard**
   - Launch Power BI Desktop
   - Open `dashboard/big_tech_analysis.pbix`

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

**Author**: Aditya Shah  
**Date**: May 2025  
**Project**: Big Tech Stock Analysis 2010-2025

---

*This analysis demonstrates the application of advanced time series techniques, risk modeling, and portfolio optimization in the context of Big Tech equity investments. The framework provides a robust foundation for data-driven investment decision making.*
