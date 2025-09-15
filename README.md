 Objective 
The objective of this analysis is to identify anomalies in stock price trends that may indicate 
unusual market behavior, potential manipulation, or early warning signals for traders. We 
combine technical indicators, unsupervised anomaly detection, and time-series forecasting 
to build a robust anomaly detection framework. 
2. Data Preprocessing 
We pulled historical stock data from Yahoo Finance for selected companies (e.g., Apple, 
Microsoft, Tesla) and cleaned the dataset: 
 Handled missing values 
 Converted date columns to datetime format 
 Calculated percentage change in closing price for better model stability 
3. Technical Indicators 
We engineered the following financial indicators: 
 SMA (Simple Moving Average) 
 EMA (Exponential Moving Average) 
 RSI (Relative Strength Index) 
 Bollinger Bands 
These indicators help capture trend, momentum, and volatility, which are crucial for 
identifying outliers in price movements. 
4.  Anomaly Detection – Isolation Forest 
We applied Isolation Forest, an unsupervised learning algorithm that detects anomalies by 
isolating points in the feature space. It works well for identifying unusual patterns in price and 
volatility. 
Interpretation: 
 Red dots represent anomalies, i.e., data points where price behavior diverged 
significantly from the norm. 
 Many anomalies align with major market events (e.g., earnings, sudden market drops) 
5. Forecasting-Based Anomaly Detection – Prophet 
We used Facebook Prophet, a time-series forecasting model, to model the expected trend of 
stock prices and flag deviations: 
Interpretation: 
 Blue line shows the forecasted trend 
 RedRed dots are the actual prices 
 Points far outside the confidence interval are flagged as forecast anomalies 
6. 📌 Comparison of Anomalies: Isolation Forest vs. Prophet 
Insights: 
 Prophet is more trend-sensitive and flags sustained deviations. 
 Isolation Forest is point-sensitive, flagging sharp or subtle outliers. 
 Together, they offer complementary insights — Prophet catches broader shifts; 
Isolation Forest detects point anomalies. 
7. Key Takeaways 
 Unsupervised methods like Isolation Forest are effective at detecting sudden, spiky 
anomalies. 
 Prophet is more suited to identifying longer-term deviations from expected market 
behavior. 
 Combining both provides a robust detection system for financial anomalies.
