# Bitcoin Trader Behavior & Market Sentiment Analysis

## Overview
This project analyzes the relationship between trader behavior (profitability, risk, volume, leverage) and Bitcoin market sentiment (Fear vs Greed).  
Two datasets are combined:
- **Bitcoin Market Sentiment Dataset** — daily sentiment index (Fear, Greed, Extreme Fear, Extreme Greed, Neutral) with score values.
- **Historical Trader Data from Hyperliquid** — trade-level execution details, profitability, and risk metrics.

The goal is to identify how trading performance aligns or diverges from market emotions and to detect hidden trends or signals that could improve trading strategies.

---


---

## How to Run

1. **Open Notebook in Google Colab**  
   - [https://colab.research.google.com/drive/1r4qK43sX2zx8Libq-QtXEDvri9o53clZ?usp=sharing]

2. **Upload Input Data**  
   - Place both datasets inside the `csv_files/` folder:
     - `market_sentiment.csv`
     - `trader_data.csv`

3. **Run All Cells**  
   - The notebook will:
     - Load & clean both datasets
     - Merge trader data with sentiment
     - Perform EDA (exploratory analysis)
     - Calculate aggregated metrics
     - Run statistical tests (e.g., t-tests between Fear vs Greed)
     - Save all result plots & summary CSVs to `outputs/`

4. **Review Results**  
   - Open `outputs/` for generated charts and tables.
   - See `ds_report.pdf` for key insights and strategic recommendations.

---

## Features & Analysis Performed

- **Data Cleaning & Preparation**
  - Handles duplicates & missing values
  - Standardizes categorical, numeric, and datetime formats
  - Ensures safe merging on date fields

- **Exploratory Data Analysis**
  - Sentiment distribution and time-series trends
  - Profitability & trade volume distributions
  - Trade side (BUY/SELL) and direction breakdown by sentiment

- **Core Analysis**
  - Aggregated metrics (mean/median PnL, volume, fees) by sentiment
  - Leverage & risk patterns
  - Win/loss rate computation
  - Outlier and extreme trade detection
  - BUY/SELL percentages by sentiment class

- **Statistical Testing**
  - Independent t-test: “Fear” vs “Greed” profitability  
    - Finding: **Average profitability in Fear periods is significantly lower than in Greed periods** (p << 0.001)

---

## Key Insights
- **Greed periods**: Higher average PnL despite smaller per-trade volumes.  
- **Fear periods**: Larger average trade size but lower average profitability.  
- **Extreme Greed**: High volumes with diluted per-trade returns, indicating overconfidence effects.  
- **SELL dominance** in Greed phases — possible profit-taking behavior.  
- A few **top accounts** control the majority of traded volume.

---

## Requirements
- Python 3.x
- Google Colab or local Jupyter Notebook
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `fpdf` (for PDF generation)

---

## Author
Prepared by: *[Hemanth_Tempalli]*  
Date: August 8, 2025

---

