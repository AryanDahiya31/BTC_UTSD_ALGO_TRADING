# **Trading Model Documentation**

## **Overview**
We developed a predictive trading model as part of the KGP Data Science Hackathon. The goal was to create a system that predicts whether the closing parameter of a stock will increase or decrease, utilizing various indicators and machine learning techniques.

## **Methodology**

### **Problem Statement**
The hackathon problem statement revolved around real-time trading strategies.

### **Model Development**
- **Prediction Model:** We developed a model that predicts the direction of the Close parameter (increase or decrease) based on the current day's data, employing a binary classification approach.

- **Indicators Used:**
  - **RSI (Relative Strength Index):** Identifies overbought or oversold conditions.
  - **MACD (Moving Average Convergence Divergence):** Shows the relationship between two moving averages.
  - **Stochastic Oscillator:** Measures overbought or oversold conditions.
  - **Momentum:** Indicates the rate of change of closing price.
  - **Moving Average (MA):** Smoothes out fluctuations to identify trends.
  - **ATR (Average True Range):** Measures market volatility.
  - **Lagged ATR:** Previous day's ATR values.

### **Model Training**
We utilized an **XGBoost Classifier** for training, excluding provided features like open, close, high, low, and volume, achieving an approximate accuracy of **83%**.

### **Backtesting Results**
- Evaluated model performance through various metrics.
- Conducted manual calculations of metrics such as largest losing trade, gross profit, net profit, etc.
- Backtested to assess the model's performance in a simulated trading environment.

### **Trading Strategy**
- Implemented a binary classification model predicting stock price movement.
- Entered trades based on model predictions with specific risk management rules.
- Ongoing monitoring is advised due to the complexity of stock price prediction.

### **Visualization**
- Used **LIME plots** for local interpretable model-agnostic explanations.
- Utilized **SHAP (SHapley Additive exPlanations)** values for feature importance.

## **Metrics and Results**
Documented various metrics, including largest losing trade, gross profit, net profit, close trades, open trades, max drawdown, etc. Key ratios like **Sharpe Ratio** and **Sortino Ratio** were highlighted for risk-adjusted returns.

## **Trading Scenarios**
Outlined different trading scenarios based on model predictions and approaches for managing ongoing trades during changing market conditions.

## **Conclusion**
The developed model showcased promising results in backtesting. We emphasized the complexity of stock price prediction and the need for caution in real-world financial applications.

---

## **Additional Trading Scenarios**

### **Scenario 1: Reinforcing an Uptrend**
- **Condition:** Before closing an ongoing increasing trade, if the model predicts a price increase in the next hour.
- **Action:** Retain a portion of holdings to continue in the market.

### **Scenario 2: Switching Positions during an Uptrend to Downtrend**
- **Condition:** Holding two shares during an uptrend, and the model signals a downtrend.
- **Action:** Close the entire long position and enter a short position by purchasing some shares at a rate of 0.05%.

### **Scenario 3: Adjusting Short Position during a Downtrend**
- **Condition:** During a downtrend, if the model forecasts a continued downtrend.
- **Action:** Close a portion of the short position to capture profits and strengthen the short position by selling additional shares.

### **Scenario 4: Transitioning from Downtrend to Uptrend**
- **Condition:** In a downtrend where the model predicts an uptrend in the next hour.
- **Action:** Fully close the short position and enter a long position using a portion of our capital, aligning with the model's forecast of an upcoming uptrend.

---

## **Backtesting Results and Required Metrics**

### **Backtesting Results**
We manually calculated various metrics to evaluate the performance of our trading model during the backtesting period.

- **Largest Losing Trade (loss_mag_max):** 88.64%
- **Gross Profit:** \$50,380.07
- **Net Profit:** \$50,304.50
- **Close Trades:** 8,897
- **Open Trades:** 0
- **Max Drawdown:** -6.44%
- **Maximum Loss:** 88.64%
- **Average Losing Trade:** 3.35%
- **Average Winning Trade:** 7.38%
- **Buy and Hold Return:** 102.85%
- **Largest Winning Trade:** 89.13%
- **Average Holding Duration per Trade:** 1 day
- **Sharpe Ratio:** 0.60
- **Sortino Ratio:** 2.10
- **Max Dip:** 99.95%
- **Average Dip:** -3.94%

These metrics provide insights into the performance, risk, and profitability of our trading model.
