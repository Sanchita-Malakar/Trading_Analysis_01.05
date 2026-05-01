# 📊 Bitcoin Sentiment × Trader Performance Analysis

> Exploring how Bitcoin market sentiment (Fear & Greed Index) shapes real trading outcomes on Hyperliquid — a decentralized perpetuals exchange.

---

## 🧠 Project Overview

This project merges two datasets — the **Bitcoin Fear & Greed Index** and **Hyperliquid historical trade data** — to investigate whether market emotion is a meaningful predictor of trader profitability, win rate, volume, leverage usage, and directional performance.

Every trade in the dataset is tagged with the sentiment label for that day (Extreme Fear → Extreme Greed), enabling sentiment-sliced analysis across thousands of real trades.

---

## 📁 Repository Structure

```
📁 your-repo/
├── Trading_Analysis.ipynb        ← Main analysis notebook
├── charts/
│   ├── chart1_avg_pnl_by_sentiment.html
│   ├── chart2_winrate_by_sentiment.html
│   ├── chart3_volume_by_sentiment.html
│   ├── chart4_buysell_nested_donut.html
│   ├── chart4_buysell_sankey.html
│   ├── chart5_top_traders.html
│   ├── chart5_top_traders_combined.html
│   ├── chart6_trader_heatmap.html
│   ├── chart7_coin_radar.html
│   ├── chart7b_coin_heatmap.html
│   ├── chart_buy_vs_sell.html
│   ├── chart_coin_sentiment.html
│   ├── chart_coin_winrate_sentiment.html
│   ├── chart_correlation.html
│   ├── chart_cumulative_pnl.html
│   ├── chart_direction_pnl.html
│   ├── chart_fee_ratio.html
│   ├── chart_leverage_by_sentiment.html
│   ├── chart_leverage_heatmap.html
│   ├── chart_leverage_performance.html
│   ├── chart_position_by_sentiment.html
│   ├── chart_position_performance.html
│   ├── chart_risk_sentiment.html
│   ├── chart_risk_traders.html
│   ├── chart_seg_avg_pnl.html
│   ├── chart_seg_donut.html
│   ├── chart_seg_heatmap.html
│   └── dashboard_final.html
├── .gitignore
└── README.md
```

---

## 📂 Datasets

| # | Dataset | Key Columns |
|---|---------|-------------|
| 1 | **Bitcoin Fear & Greed Index** | `date`, `value`, `classification` (Extreme Fear / Fear / Neutral / Greed / Extreme Greed) |
| 2 | **Hyperliquid Historical Trader Data** | `account`, `coin`, `side`, `size_usd`, `execution_price`, `closed_pnl`, `leverage`, `start_position`, `timestamp_ist`, `event` |

The two datasets are merged on `date`, tagging each trade with the market sentiment of that day.

---

## 🔍 Analysis Modules

### 1. 💹 PnL by Sentiment
Average and total closed PnL grouped by sentiment class — answers: *"In which market mood do traders make the most money?"*

### 2. 🎯 Win Rate by Sentiment
Percentage of profitable trades per sentiment regime. Reference line at 50% (breakeven). No sentiment crosses the breakeven threshold.

### 3. 📦 Volume by Sentiment
Total and average trade size across sentiment classes — reveals whether traders are more aggressive during Fear or Greed.

### 4. 📊 BUY vs SELL Direction Analysis
Grouped bar chart comparing average PnL for long vs short trades within each sentiment — identifies which side is more profitable per regime.

### 5. ⚡ Leverage Analysis
- Leverage bucketed into: 1–2x, 3–5x, 6–10x, 11–20x, 21–50x, 50x+
- Avg PnL and win rate per leverage tier
- Leverage usage per sentiment (avg + median)
- Heatmap: Leverage × Sentiment → Avg PnL
- Correlation (Pearson & Spearman) between leverage and PnL

### 6. 📐 Position Size Analysis
- Position buckets: Zero, Micro, Small, Medium, Large, XLarge
- Avg PnL and win rate per position tier
- Position size trends across sentiment classes
- Correlation between position size and returns

### 7. 📉 Risk & Sharpe Analysis
- Sharpe ratio computed per trader and per sentiment
- Risk-adjusted performance scatter plots
- Cumulative PnL curves by sentiment (drawdown visualized)

### 8. 🏆 Top Traders
- Leaderboard by total PnL
- Heatmap of top traders × sentiment performance
- Combined performance charts

### 9. 🪙 Coin-Level Analysis
- PnL and win rate by coin × sentiment (radar and heatmap)
- Identifies which coins perform best under which sentiment

### 10. 🗂️ Trader Segmentation
- Traders clustered by behaviour and performance
- Segment donut, avg PnL per segment, and sentiment heatmap

---

## 📈 Interactive Charts

All 27+ charts are built with **Plotly** and saved as standalone `.html` files — open any of them in a browser, no server needed.

| File | What it shows |
|------|--------------|
| `chart1_avg_pnl_by_sentiment.html` | Average PnL per sentiment class |
| `chart2_winrate_by_sentiment.html` | Win rate % per sentiment |
| `chart3_volume_by_sentiment.html` | Total & avg trade volume |
| `chart4_buysell_*.html` | BUY vs SELL breakdowns (donut + sankey) |
| `chart5_top_traders*.html` | Top trader leaderboard |
| `chart_leverage_*.html` | Leverage performance & sentiment heatmap |
| `chart_position_*.html` | Position size analysis |
| `chart_risk_*.html` | Sharpe ratio & cumulative PnL |
| `chart_coin_*.html` | Coin-level sentiment analysis |
| `chart_seg_*.html` | Trader segmentation visuals |
| `dashboard_final.html` | **Combined interactive dashboard** |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3 | Core language |
| Pandas & NumPy | Data cleaning and transformation |
| Plotly | Interactive chart generation |
| SciPy | Statistical correlation (Pearson, Spearman) |
| Jupyter Notebook | Development environment |

---

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/your-username/your-repo.git
cd your-repo

# 2. Install dependencies
pip install pandas numpy plotly scipy

# 3. Open the notebook
jupyter notebook Trading_Analysis.ipynb

# 4. Update dataset paths in cells 2 & 3
#    Change: pd.read_csv(r'C:\Users\...\fear_greed_index.csv')
#    To:     pd.read_csv('data/fear_greed_index.csv')

# 5. Run All Cells
# Charts will be generated in the /charts folder
```

> 💡 To view charts without running the notebook, just open any `.html` file in `/charts` directly in your browser.

---

## 🔑 Key Questions Explored

- Do traders profit more during **Fear** or **Greed**?
- Does high leverage **help or hurt** returns?
- Which sentiment produces the **highest win rate**?
- Are **BUY or SELL** trades more profitable per sentiment?
- Which **coins** perform best under each sentiment?
- Can traders be **segmented** by behaviour and performance?

---

## 👤 Author
Sanchita Malakar
