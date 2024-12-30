# Stock and Gold Market Trading Model

## Feature Explanation

1. **Close/Last**: Normalized closing price of the stock for a specific day. This reflects the market's final trading price.  
2. **Volume**: Normalized total volume of stocks traded during the day. Higher volume can indicate strong activity.  
3. **Open**: Normalized opening price of the stock for the day.  
4. **High**: Normalized highest price the stock reached during the day.  
5. **Low**: Normalized lowest price the stock reached during the day.  
6. **Day, Month, Year**: Temporal attributes that can help detect seasonality or trends over time.  

## Action Space

Actions include:  
- **Buy**: Purchase gold at the current price.  
- **Sell**: Sell gold at the current price.  
- **Hold**: Take no action.  

## State Space

States are represented by the following features of the dataset:  
- Close/Last  
- Volume  
- Open  
- High  
- Low  
- Day  
- Month  
- Year  

## Reward Function

Rewards are assigned to encourage profitable actions:  
- **Positive reward**: When the agent buys at a low price and sells at a higher price.  
- **Negative reward**: When the agent buys high and sells low.  
- **Neutral reward**: For holding without taking action.  

## Deep Q-Learning (DQL)

- A neural network is used to approximate Q-values for each action.  
- Q-values are updated using the Bellman equation based on rewards received from the environment.  

## Decision Column

- After training the model, a new column is created in the dataset to indicate whether to **Buy**, **Sell**, or **Hold** based on the model's output.  

## Evaluation

The model is evaluated by simulating trades using a test set and measuring:  
- **Total profit**  
- **Accuracy of "Buy" and "Sell" predictions**  

## Evaluation Metrics

1. **Profit Calculation**  
   - Simulate a trading strategy based on the model's decisions.  
   - Track the net profit (or loss) over the test period.  
   - **Initial balance**: Assume starting with a fixed balance (e.g., $10,000).  

2. **Action Accuracy**  
   - Evaluate how often "Buy" decisions are followed by a price increase and "Sell" decisions by a price decrease.  

3. **Sharpe Ratio**  
   - Measures the risk-adjusted return.  
   - Formula:  

4. **Win Rate**  
   - Proportion of profitable trades to total trades.  

## Key Metrics

- **Total Profit**:  
  - Measures the absolute profit or loss achieved by the strategy. A positive value indicates profitability.  

- **Win Rate**:  
  - Shows the percentage of successful trades. Higher values indicate better decision-making.  

- **Sharpe Ratio**:  
  - Indicates the return per unit of risk. Higher values suggest better risk-adjusted performance.  

- **Final Balance**:  
  - The total funds at the end of the trading period, including unsold gold.
