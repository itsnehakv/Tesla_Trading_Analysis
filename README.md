# Tesla Stock Analysis (TSLA)

## Project Overview
This project analyzes **Tesla’s historical trading data (Jan 2021 – Jan 2026)** to uncover **market trends, short-term spikes, volatility, and medium-term momentum**. The analysis leverages daily Open, Close, High, and Low prices to provide **numeric insights and actionable takeaways** for investors and portfolio managers.
The goal is to provide **data-driven, executive-focused insights** into performance, risk, and trading patterns.

---
## Libraries Used
- Pandas
- Pandas Datareader
- Datetime
- Matplotlib
---

## Business Objectives
1. Identify **short-term price rallies and consolidation periods**.  
2. Evaluate **daily return, volatility, and percent change** to assess opportunity vs. risk.  
3. Use **rolling averages and resampling** to understand medium- and long-term trends.  
4. Quantify **risk-adjusted performance** for strategic decision-making.

---

## Data Snapshot
- **Source:** Stooq  
- **Coverage Period:** Jan 2021 – Jan 2026  
- **Frequency:** Daily trading days  
- **Metrics:** Open, Close, High, Low, Volume  

---
## Methodology
### 1. Data preparation
- Converted trading dates into a **DatetimeIndex** for time-series analysis and sorted the index.
```
tesla_df.index = pd.to_datetime(tesla_df.index)
tesla_df = tesla_df.sort_index()      
```
### 2. Initial Trend Exploration
- Plotted **daily High prices** to visualize overall trends.  
- Focused on **recent data (Jan 2024 – Jan 2026)** for closer inspection of the latest market behavior.  
- Calculated basic spike metrics for this period:  
  - **Peak High, Average High, Average Daily Volatility, Percent Change**<br>
- **Insight:** Identified a notable **price surge** between Nov 2024 – Mar 2025 with a sharp spike (~92% gain) with high volatility.  


### 3.Time Resampling
- Resampled data to **business-end periods** for trend clarity:  
  - **Monthly average High** (BM)  
  - **Quarterly max High** (BQ)  
  - **Annual average/max High** (BA)  
- Focused on **trends rather than daily noise**, providing executive-friendly insights into performance over different horizons.

### 4. Daily Return Analysis
- Calculated **daily returns** using Open and Close prices:
```
tesla_df['Daily_Return'] = (tesla_df['Close'] - tesla_df['Open']) / tesla_df['Open'] * 100
```
- Plotted daily returns and noted periods of **spikes and elevated volatility**.  
- **Insight:** Short-term rallies are visible in Q1 2023, Nov 2024–Mar 2025, and Q1 2025.

### 5. Short-Term Spike Analysis
- Isolated periods corresponding to **observed spikes in daily returns**.  
- Computed metrics for each spike period:  
- Avg Open/Close  
- Avg Daily Return  
- Avg Daily Volatility  
- Peak High  
- Percent Change  

**Insights:**  
- **Q1 2023:** Sustained short-term rally (~83% gain) with positive returns and moderate volatility.  
- **Q1 2025:** High volatility (~$18/day) but limited net gain (~12%) — period of consolidation and profit-taking.

### 6. Rolling Analysis
- Applied **30-day rolling average** to Open (and Close) prices.  
- Provided **smoothing effect** to identify **medium-term momentum**.
---

## Executive Highlights

### Short-Term Spikes
| Period | Peak High Price | Avg High Price | Avg Daily Volatility | Percent Change |
|--------|----------------|---------------|--------------------|----------------|
| Q1 2023 | $217.65 | $178.25 | $9.23 | 83.20% |
| Nov 2024 – Mar 2025 | $488.54 | $381.34 | $19.07 | 92.34% |
| Q1 2025 | $439.74 | $344.08 | $17.91 | 11.97% |

**Insights:**  
- Nov 2024 – Mar 2025 experienced the **largest short-term rally**, with a **92% increase in High price** and high daily volatility.  
- Q1 2023 and Q1 2025 reveal **early-year rallies**, suggesting recurring seasonal momentum.  
- These spikes highlight periods of **heightened opportunity and elevated risk**.

---

### Daily Returns
- Daily returns show the **percentage gain or loss each trading day**, helping assess **short-term performance and momentum**.  
- Spikes in daily returns correspond to **Q1 2023 and Q1 2025**, confirming **short-term rallies and corrections**.  
- Aggregated returns over weeks or months reveal **broader market trends** and **risk patterns**.

---

### Resampled Metrics (Monthly, Quarterly, Annual)
- **Monthly averages** capture short-term trends.  
- **Quarterly max prices** highlight peak trading points.  
- **Annual averages and max** reveal long-term trends.  
- Using **business-end periods** ensures the analysis reflects **actual trading days**, excluding weekends and holidays.
### Rolling Averages (30-Day)
- **30-day rolling averages** of Open and Close prices smooth daily fluctuations, highlighting **medium-term trends and momentum**.  
- This helps executives focus on **sustained market trends** rather than daily noise.  
- Rolling metrics complement spike and daily return analysis to provide a **complete view of Tesla’s trading dynamics**.


---

## Impact / Takeaways
- Identifies **key trading periods** with numeric insights (peak prices, volatility, percent change).  
- Provides a **clear picture of momentum, risk, and opportunity** for investors.  
- Rolling averages and resampled metrics give a **medium-term perspective**, enabling **data-driven portfolio decisions**.  
- Overall, this project delivers a **comprehensive, executive-ready view of Tesla’s historical market behavior**.
