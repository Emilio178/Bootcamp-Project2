# Bootcamp-Project2
Machine Learning Project -Team 9

## Business Proposal
### **1. Project Objective** 

To predict the likelihood (odds ratio) of a positive return (r>x%) in the next n trading days following the quarterly earning releases. <br />

For example, if I buy company A's stock at its closing price on Jun 8th when company A announces its quarterly result right after closing bell, what's my chance of making a profit by just holding for the next few days. Here we try to make a prediction on a short-term price movement without knowing the earning result, which could be a tool for traders who'd like to 'bet' on quarterly earning release.

### **2. Model Target** <br />

Positive return during the next 5 trading days since a new quarterly earning realease (e.g. x=0, n=5)

### **3. Model Base** <br />

**Sample base** --- Companies in S&P 500 as of May 31, 2022 (rationale: good liquidity and publicity)<br />
**Sample period** --- 10 years from 2012Q1 to 2022Q1<br />

**Features:**
  * Foundamental Metrics<br />
    * Basic Metrics: industry, market cap, institution holding% etc.<br />
    * Valuation Metrics: PE PB PS PEG <br />
    * Profitability and Growth: Y/Y, Q/Q, 3-year avg growth, 5-year avg growth on EPS, Revenue, Gross Margin, FCF, Operating Cash Flow etc. <br />
    * Volatility: implied volatility from its option
  * Techniqual Indicators<br />
    MA, EMA, MACD, RSI, Bollinger Bands, Indicators Fibonacci Retracement Indicators<br />
    Implied volatility, short ratio, short interest <br />
  * Broad Market Variables<br />
    * Financial Market: indices such as Russell 2000 (^RUT), CBOE Volatility Index (^VIX), etc.
    * Commodity Market: crude oil future price, gold future
    * Economic Environment: Treasury Yield 10 years (^TNX), GDP growth, unemployement ratio, PPI, CPI, inflation rate etc.
  * Sentiment Analysis<br />
    * sentiment score from major financial news website and forum: WSJ, Bloomberg, CNBC, Reuters, Twitter etc.  
 
 ### **4. Technology and Data Source** <br />
    Coding Language
      * Python
      * SQL
    Data Source
      * Yahoofinance API
      * Morningstar API
      * Tradingview API
      * Twelvedata API
      * (API for NEWS: TBD)
    ML Techniques
      * Scikit-learn (for classification and logistic regression model)
      * Tensorflow (for DNN model)
      * NLP
      * Webscraping
