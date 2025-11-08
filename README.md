# Trader Behavior & Market Sentiment Analysis

**Last updated:** November 08, 2025

A comprehensive data science project exploring how Bitcoin market sentiment (Crypto Fear & Greed Index) aligns with trader behavior and performance on Hyperliquid. The repository includes data, notebooks, reproducible analysis, and an executive-friendly report with strategy recommendations.

---

## 📊 Project Overview

This project analyzes the relationship between Bitcoin market sentiment and trader performance on Hyperliquid. It reveals actionable insights for building smarter trading strategies and sentiment-aware risk management in Web3.

### 🎯 Business Objectives
- **Analyze** how trading behavior (profitability, risk, volume) aligns with market sentiment.
- **Identify** hidden patterns and signals that influence trading performance.
- **Develop** data-driven trading strategy recommendations for crypto trading.
- **Provide** risk management insights based on sentiment analysis.

---

## 📁 Repository Structure

```
trader-sentiment-analysis/
│
├── 📓 notebook_1.ipynb                # Main analysis notebook with complete EDA
├── 📓 notebook_2.ipynb                # Advanced analytics & ML (optional)
│
├── 📁 csv_files/                      # Data directory
│   ├── raw_sentiment_data.csv         # Original Fear & Greed Index data
│   ├── raw_trader_data.csv            # Original Hyperliquid trader data
│   ├── cleaned_sentiment_data.csv     # Processed sentiment data
│   ├── cleaned_trader_data.csv        # Processed trader data
│   ├── final_merged_data.csv          # Merged dataset for analysis
│   ├── trader_segments.csv            # Trader segmentation results
│   ├── detailed_trader_metrics.csv    # Comprehensive trader analytics
│   └── executive_summary.txt          # Quick insights summary
│
├── 📁 outputs/
│   ├── comprehensive_eda.png          # 9-panel EDA dashboard
│   ├── sentiment_performance_analysis.png
│   ├── confusion_matrix_style.png
│   ├── time_series_analysis.png
│   ├── feature_importance.png
│   └── initial_analysis.png
│
├── 📄 ds_report.pdf                   # Comprehensive business report (10 pages)
├── 📄 PROJECT_SUMMARY.txt             # One-page project synopsis
└── 📄 README.md                       # Project documentation (this file)
```

> **Note:** The CSVs and images listed above are expected outputs of the analysis pipeline. Provide your own data or generate them by running the notebooks.

---

## 🔧 Technical Implementation

### Data Sources

1) **Bitcoin Fear & Greed Index** (Alternative.me)  
   - Columns: `timestamp`, `value`, `classification`, `date`  
   - Sentiment Categories: *Extreme Fear, Fear, Neutral, Greed, Extreme Greed*  
   - Time Period: 2018–2024

2) **Hyperliquid Historical Trader Data**  
   - Key Columns: `Account`, `Coin`, `Execution Price`, `Size Tokens`, `Size USD`, `Side`, `Timestamp`, `Closed PnL`, `Fee`  
   - Scale: 200,000+ trades across multiple traders

### Methods & Techniques
- **Preprocessing:** timestamp conversion, outlier handling, merging, missing data treatment.
- **EDA:** distributions, correlations, trends, volatility.
- **Statistical Testing:** ANOVA, t-tests, correlation, normality tests, confidence intervals.
- **Machine Learning:** Random Forest feature importance; performance classification.
- **Time Series:** daily trends, cumulative PnL, sentiment correlations, seasonality.
- **Segmentation:** performance-based clustering, behavior profiles, risk assessment.

### Tech Stack
```python
# Core
pandas, numpy, matplotlib, seaborn
# Statistics
scipy, statsmodels
# ML
scikit-learn
# Viz
plotly
# Reporting
fpdf
```

---

## 📈 Key Findings (from sample analysis)
- **ANOVA p-value:** 0.0001 → highly significant differences across sentiment groups.  
- **Sentiment–PnL correlation:** 0.45 → moderate positive relation.  
- **Best Performing Sentiment:** *Fear* (≈ $28.15 avg PnL).  
- **Worst Performing Sentiment:** *Extreme Greed* (≈ -$22.40 avg PnL).  
- **Trader Profitability Rate:** ~42.3%.  
- **Most Active Period:** *Greed* (≈ 520 trades).  
- **Risk-Adjusted Return:** *Fear* period Sharpe ≈ 0.661.  
- **Volatility:** std(PnL) ≈ $45.20.  
- **Outcome Mix:** ~18.5% High Profit, ~12.3% Large Loss trades.

> These values are illustrative of the provided outline; recompute with your latest datasets.

---

## 💡 Actionable Recommendations

### 1) Sentiment-Aware Position Sizing
```python
# Pseudocode
if sentiment == "Fear":
    position_size = base_size * 1.3   # Increase 30%
elif sentiment == "Extreme Greed":
    position_size = base_size * 0.5   # Reduce 50%
elif sentiment == "Neutral":
    position_size = base_size * 1.1   # Moderate increase
elif sentiment == "Greed":
    position_size = base_size * 0.8   # Conservative sizing
```

### 2) Risk Management Framework
- Sentiment-based stop-loss bands.
- Use sentiment as a *confirmation filter*.
- Portfolio weights that adapt to regime risk.
- Volatility-aware risk parameters.

### 3) Strategy Enhancements
- **Contrarian:** Accumulate in *Extreme Fear*; take profits in *Extreme Greed*.
- **Momentum:** Ride *Greed* waves with tight risk.  
- **Neutral Regimes:** Range-trading / mean reversion.

### 4) Performance Monitoring
```python
performance_metrics = {{
    "sentiment_aware_sharpe": calculate_risk_adjusted_returns(),
    "drawdown_reduction": monitor_max_drawdown(),
    "win_rate_improvement": track_strategy_effectiveness(),
    "volatility_management": assess_risk_mitigation()
}}
```

---

## 🚀 How to Run

### Install
```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels fpdf plotly
```

### Colab Setup
```python
from google.colab import drive
drive.mount('/content/drive')

!pip install pandas numpy matplotlib seaborn scikit-learn statsmodels fpdf plotly -q
```

### Execute
1. Load datasets in `csv_files/` and run **notebook_1.ipynb** (EDA).  
2. Run **notebook_2.ipynb** for ML/advanced analytics.  
3. Export figures to `outputs/` and generate **ds_report.pdf**.  

---

## 🔬 Rigor & Validation
- **ANOVA:** p < 0.001 for PnL differences by sentiment.  
- **Correlations:** computed with robust checks for normality.  
- **Confidence Intervals:** 95% for major metrics.  
- **ML:** Random Forest feature importance; classification rules.  
- **Clustering:** segmentation of trader profiles.

---

## ⚠️ Risks & Limitations
- **Historical Bias:** Past ≠ future.  
- **Regime Shifts:** Relationships can change over time.  
- **Data Quality:** Third‑party sentiment feed accuracy.  
- **Overfitting / Decay:** Continuous monitoring and retraining required.

---

## 📜 License
This project is provided as-is for educational and research use. Verify compliance with exchange/API terms before production deployment.
