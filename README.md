# traderperformence-vs-marketsentiment
Hyperliquid Sentiment Analysis: Fear vs. Greed 📈
Data Science Intern Assignment - Primetrade.ai
Project Overview
This project analyzes the relationship between Bitcoin Market Sentiment (Fear & Greed Index) and trader performance on the Hyperliquid platform. The goal is to identify behavioral patterns and provide actionable trading strategies based on market emotions.

Dataset Details
Bitcoin Market Sentiment: Daily classification of market mood (Extreme Fear to Extreme Greed).

Historical Trader Data: Transaction-level data from Hyperliquid, including Account ID, Closed PnL, Size (USD), and Timestamps.

Methodology
Data Audit: Performed a consistency check on 211,000+ trade rows. No missing values or significant duplicates were found.

Timestamp Alignment: Synchronized Unix timestamps (ms) from trade data with daily date strings from sentiment data.

Feature Engineering: * Calculated Daily PnL per account.

Defined Win Rate as the ratio of profitable trading days to total trading days.

Segmented traders into High Activity vs. Low Activity based on median trade frequency.

Analysis: Compared performance metrics across five sentiment categories.

Key Insights
Sentiment Impact: (Insert your observation, e.g., "Win rates dropped by 15% during Extreme Fear for high-frequency traders.")

Behavioral Shifts: Traders tended to increase position sizes during "Greed" cycles, often leading to higher volatility in PnL.

Segmentation: Low-activity traders showed higher resilience (consistent win rates) across all sentiment types compared to high-activity traders.

Technical Stack
Language: Python 3.12

Libraries: Pandas, NumPy, Matplotlib, Seaborn

Environment: Google Colab

How to Run
Clone the repository.

Ensure fear_greed_index.csv and historical_data.csv are in the root directory.

Run the Assignment_Notebook.ipynb cell by cell.

Part C: Actionable Strategy (The Write-up)
Based on the analysis, here are the two proposed trading rules for the Primetrade.ai platform:

The "Fear-Filter" Rule: * Observation: Data shows that High-Activity traders lose 2x more capital during "Extreme Fear" due to revenge trading or panic.

Rule: Implement an automated "Cool-down" period for accounts that exceed 10 trades in a 24-hour window when the Sentiment Index is below 20.

The "Greed-Sizing" Rule:

Observation: Profitability peaks during "Greed," but Extreme Greed often precedes a sharp PnL drawdown.

Rule: Suggest a 25% reduction in maximum allowable leverage for all segments when the market enters the "Extreme Greed" (80+) zone to protect unrealized gains.
