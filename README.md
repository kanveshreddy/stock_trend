Stock Price Trend Analysis Using Historical Data (NVIDIA – NVDA)
ITM University Gwalior · School of Computing and Intelligent Systems
Project-Based Learning (PBL) – Mini Project
	
Course	Data Analytics Using Python (CSL0312)
Program	B.Tech. CSE (Artificial Intelligence & Machine Learning)
Semester / Section	III / F
Academic Session	July–Dec 2026
Domain	Financial & Economics Analysis
Faculty Mentor	Dr. Sanjay Jain
Team
Role	Name	Roll No.
Team Leader	K Anvesh Reddy	BETN1AI25168
Team Member	G Madhava Reddy	BETN1AI25161
Team Member	K Karthik	BETN1AI25179
Project Overview
Stock prices change every day because of market demand, company performance, economic news and investor sentiment. Raw historical prices alone make it hard to see the direction of the market. This project analyses the historical share price of NVIDIA Corporation (NVDA) from 2 January 2020 to 30 July 2026 and uses technical indicators to identify the direction, strength, momentum and volume support of the price trend.
The project covers data cleaning, exploratory data analysis (EDA), technical indicator calculation, rule-based trend classification, visualization and interpretation using Python.
> **Disclaimer:** This is an academic project that describes past data. Technical indicators are signals, not guaranteed predictions, and nothing here is investment advice.
Dataset
	
Name	NVIDIA Corporation (NVDA) Historical Price Data
Source	Yahoo Finance – https://finance.yahoo.com/quote/NVDA/history/
Type	Public
Format	CSV (`NVDA_Historical_Data.csv`)
Records	1,652 trading days
Columns	6 – `Date`, `Close`, `High`, `Low`, `Open`, `Volume`
Methodology
Data collection – load the Yahoo Finance CSV into pandas.
Data cleaning – remove the two extra header rows ("Ticker", "Date"), rename `Price` to `Date`, convert `Date` to datetime and price/volume columns to float, check for missing values, duplicates, zero/negative prices, date order and High/Low consistency.
Exploratory data analysis – summary statistics (`describe()`), daily percentage returns.
Technical indicators
EMA 20 / EMA 50 – trend direction and crossovers
MACD (12, 26, 9) – momentum, signal line, histogram and crossovers
ADX (14) with +DI / −DI – trend strength and directional pressure (via the `ta` library)
Volume analysis – peak volume and high-volume days (> 2 × average volume)
Overall trend classification – each day is labelled Strong Bullish, Strong Bearish or Mixed/Weak:
Strong Bullish: EMA 20 > EMA 50, MACD > signal, ADX > 25, +DI > −DI
Strong Bearish: EMA 20 < EMA 50, MACD < signal, ADX > 25, −DI > +DI
Otherwise: Mixed/Weak
Visualization – price, EMA, daily-return histogram, price with volume, MACD, MACD histogram, ADX and +DI/−DI charts.
Key Results
Closing price rose from 5.96 USD (2020-01-02) to 193.54 USD (2026-07-30), with a maximum close of 235.47 USD – a strong long-term uptrend.
The dataset is clean: 0 missing values, 0 duplicates, 0 invalid prices, and it is sorted by date.
EMA crossovers: 18 bullish + 18 bearish. MACD crossovers: 66 bullish + 66 bearish.
Overall trend: Mixed/Weak 1,299 days (78.6%), Strong Bullish 282 days (17.1%), Strong Bearish 71 days (4.3%).
Peak volume: 1,543,911,000 shares on 2023-05-25 (daily return +24.37%).
Latest reading (2026-07-30): EMA 20 (201.97) is below EMA 50 (203.44), the MACD histogram is negative (−1.465) and −DI (23.52) is above +DI (14.05), but ADX is only 15.25, so the downward move is not yet a strong trend.
Repository Contents
File	Description
`Untitled8_ordered.ipynb`	Google Colab notebook with all code and outputs
`NVDA_Historical_Data.csv`	Raw NVDA historical data from Yahoo Finance
`PBL_Report_NVDA_Stock_Trend_Analysis.docx`	Final PBL mini project report (includes code and outputs in Appendix A)
`README.md`	This file
How to Run
Open `Untitled8_ordered.ipynb` in Google Colab.
Upload `NVDA_Historical_Data.csv` to the Colab session (it is read from `/content/NVDA_Historical_Data.csv`).
Run all cells in order. The notebook installs the `ta` library with `!pip install ta`.
To run locally, install the requirements and change the file path in the first cell:
```bash
pip install numpy pandas matplotlib seaborn ta
```
Tools and Libraries
Language: Python 3
Environment: Google Colab
Libraries: NumPy, pandas, Matplotlib, Seaborn, `ta` (Technical Analysis Library)
Future Scope
Add Price Action (swing highs/lows) and On-Balance Volume (OBV) for further trend confirmation.
Back-test the EMA and MACD crossover signals and tune indicator periods.
Build interactive Plotly dashboards.
Extend the analysis to multiple stocks or sector indices.
Apply machine-learning models to forecast trend direction.
AI Tool Declaration
Claude (Anthropic) was used to draft and format the project report and this README from the notebook outputs. No new analysis or charts were created by the AI tool.
References
Yahoo Finance – NVDA historical data: https://finance.yahoo.com/quote/NVDA/history/
NumPy: https://numpy.org/ · pandas: https://pandas.pydata.org/ · Matplotlib: https://matplotlib.org/ · Seaborn: https://seaborn.pydata.org/
`ta` library: https://github.com/bukosabino/ta
Wilder, J. W. (1978). New Concepts in Technical Trading Systems. Trend Research.
