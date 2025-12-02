# 📊 Backtest Reports

## 📍 Report Location

This directory contains historical backtest reports and charts:

```
/root/AIFX_v2/ml_engine/backtest/reports/
├── historical_backtest_report.html    # HTML Backtest Report
└── backtest_charts/                   # Charts Directory
    ├── win_rate_by_period_All.png    # Win Rate Bar Chart
    ├── profit_factor_by_pair.png      # Profit Factor Chart
    ├── equity_curve_All.png           # Equity Curve
    ├── trade_distribution_All.png     # Trade Distribution
    ├── performance_heatmap.png        # Performance Heatmap
    └── drawdown_All.png               # Drawdown Chart
```

## 🚀 How to View Reports

### Method 1: Start HTTP Server (Recommended)

Start a simple HTTP server in this directory:

```bash
cd /root/AIFX_v2/ml_engine/backtest/reports
python3 -m http.server 8888
```

Then access via browser:
```
http://144.24.41.178:8888/historical_backtest_report.html
```

### Method 2: Open HTML File Directly

If you have a GUI on the server:

```bash
firefox /root/AIFX_v2/ml_engine/backtest/reports/historical_backtest_report.html
# or
google-chrome /root/AIFX_v2/ml_engine/backtest/reports/historical_backtest_report.html
```

### Method 3: Copy to Local Computer

Use `scp` to copy the entire report directory to local:

```bash
# Execute on your local computer
scp -r root@144.24.41.178:/root/AIFX_v2/ml_engine/backtest/reports ./backtest_reports
```

Then open `backtest_reports/historical_backtest_report.html` locally.

## 📊 Report Content

### Backtest Configuration
- **Currency Pairs:** EUR/USD, USD/JPY, GBP/USD
- **Trading Periods:** Intraday (15min), Swing (1h), Monthly (1d), Position (1w)
- **Exit Strategy:** Signal Reversal Exit
- **Initial Capital:** $10,000
- **Data Period:** Last 90 days historical market data
- **Signal Source:** ML model prediction + Technical Analysis backup (SMA crossover)

### Performance Metrics (8 Items)
1. **Win Rate** - Winning trades / Total trades
2. **Total Trades** - All completed trades
3. **Winning Trades / Losing Trades** - Classified statistics
4. **Avg Win vs Avg Loss** - Average amount per trade
5. **Profit Factor** - Gross Profit / Gross Loss
6. **Total Return** - Net Profit / Initial Capital
7. **Max Drawdown** - Maximum decline in equity curve
8. **Sharpe Ratio** - Risk-adjusted return

### Chart Description
1. **Win Rate Bar Chart** - Compare win rates by period (Intraday/Swing/Monthly/Position)
2. **Profit Factor Chart** - Compare profit factors by currency pair
3. **Equity Curve** - Account balance over time, marking profit/loss points
4. **Trade Distribution** - Profit/loss distribution histogram + Win rate pie chart
5. **Performance Heatmap** - Currency pair vs Period win rate heatmap
6. **Drawdown Chart** - Max drawdown time series analysis

## 💾 Database Query

All backtest results are also stored in PostgreSQL database:

```sql
-- View all backtest results summary
SELECT pair, period, timeframe, total_trades, win_rate,
       profit_factor, net_profit, max_drawdown_pct, sharpe_ratio
FROM backtest_results
ORDER BY pair, period;

-- View best performance
SELECT * FROM backtest_results
ORDER BY net_profit DESC
LIMIT 5;

-- View trade details
SELECT bt.entry_time, bt.exit_time, bt.direction,
       bt.entry_price, bt.exit_price, bt.profit_loss, bt.profit_loss_pips
FROM backtest_trades bt
JOIN backtest_results br ON bt.backtest_result_id = br.id
WHERE br.pair = 'EUR/USD' AND br.period = 'swing'
ORDER BY bt.entry_time;
```

## 🔄 Rerunning Backtest

If you need to rerun the backtest:

```bash
cd /root/AIFX_v2/ml_engine
python3 backtest/run_historical_backtest.py
```

New reports will be automatically generated and overwrite files in this directory.

## 📝 Notes

⚠️ **Risk Warning**
- This is historical simulation backtest result, not representing future performance
- Actual trading involves slippage, fees and other extra costs
- Past performance does not guarantee future results
- Please trade cautiously and manage risks well

## 📞 Technical Support

If you have questions, please check:
- Backtest Engine Code: `/root/AIFX_v2/ml_engine/backtest/historical_backtest.py`
- Chart Generator: `/root/AIFX_v2/ml_engine/backtest/chart_generator.py`
- Execution Script: `/root/AIFX_v2/ml_engine/backtest/run_historical_backtest.py`

---

Generated at: 2025-11-29
System Version: AIFX v2
Engine: ML-Powered Historical Backtest Engine
