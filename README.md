# Bootcamp-Project2
Machine Learning Project -Team 9

## Business Proposal
### **1. Project Objective** 

To predict the likelihood (odds ratio) of a positive return (r>x%) in the next n trading days following the quarterly earning releases. <br />

For example, if I buy company A's stock at its closing price on Jun 8th when company A announces its quarterly result right after closing bell, what's my chance of making a profit by just holding for the next few days. Here we try to make a prediction on a short-term price movement without knowing the earning result, which could be a tool for traders who'd like to 'bet' on quarterly earning release.

### **2. Model Target** <br />

Positive return during the next 5 trading days since a new quarterly earning realease (e.g. x=0, n=5)
Model Logic
<img width="972" alt="Screen Shot 2022-06-18 at 12 29 15 AM" src="https://user-images.githubusercontent.com/53786396/174422746-b6df65b1-8b26-485e-a052-38818bc86f88.png">

### **3. Model Base** <br />

**Sample base** --- Companies in S&P 500 as of May 31, 2022 (rationale: good liquidity and publicity)<br />
**Sample period** --- 10 years from 2016Q1 to 2021Q1<br />

**Features:**
  * Foundamental Metrics<br />
    * Basic Metrics: industry, market cap, etc.<br />
    * Valuation Metrics: PE PB PS PEG <br />
    * Profitability and Growth: (Y/Y, Q/Q) EPS, Revenue, Gross Margin, FCF, Operating Cash Flow etc. <br />
  
  * Techniqual Indicators<br />
    MA, EMA, MACD, RSI, Bollinger Bands, Indicators Fibonacci Retracement Indicators<br />
    Implied volatility, short ratio, short interest <br />
  * Broad Market Variables<br />
    * Financial Market: indices such as Russell 2000 (^RUT), CBOE Volatility Index (^VIX), etc.
    * Commodity Market: crude oil future price, gold future
    * Economic Environment: Treasury Yield 10 years (^TNX), GDP growth, unemployement ratio, PPI, CPI, inflation rate etc.
  * Sentiment Analysis<br />
    * sentiment score from major financial news website and forum: WSJ, Bloomberg, CNBC, Reuters, Twitter etc.  
 
 Feature Pools Generated
<img width="1225" alt="Screen Shot 2022-06-18 at 12 17 49 AM" src="https://user-images.githubusercontent.com/53786396/174422460-014d2f3c-7588-4028-b8a4-b32026e9437d.png">

 ### **4. Technology and Data Source** <br />
    Coding Language
      * Python
    Data Source
      * Yahoofinance API
      * Simfin API
    ML Techniques
      * Scikit-learn (for classification and logistic regression model)
      * Tensorflow (for DNN model)
      * NLP
 ### **5. Model Result and Evaluation ** <br />
Model 1 using logistic regression receives a AUC 0.6 and Model 2 using Random Forest receives a AUC 0.73. Both model show that the overall market price trend and volatility, such as VIX, Russel 2000 rate of return, 10-year treasury yields change, have more impacts on the target. 
The lift could be interpreted as the gain ratio percentage to the random percentage at a given decile level. In decile 2, we have 1.24 means that when selecting 20% of the data based on the model, we could find the target (actual positive return) 1.24 times more than the randomly selected 20% of the data without a model.

 ![image](https://user-images.githubusercontent.com/53786396/175115413-fbcb4ef8-9a95-4a1d-90d0-cd08fd778e30.png)


 ### **6. Challenges and Limitation ** <br />
  Due to the limited timeframe and budget, Free API don't offer a good amount of datapoints. Currently, the model base only contains SP500 compnies. The result should have higher generalization if we could include Russel 2000 US stocks and longer time periods. Another limitation of the current model is that we only test on two methods - logistic regression and random forest. The result should be more robust if we can also include other models like neural network and do an assemble on all results. Lastly, more work could be done on data cleaning and feature exploration to improve the accuracy of the prediction.
