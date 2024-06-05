# Stateful Long-Short with Exits
This trading strategy demonstrates the use of Quantiacs libraries to implement a stateful long-short strategy with conditional exits, evaluated on a day-by-day basis using the multipass backtester. This strategy is designed for the Quantiacs platform. 

## How to Run the Strategy
### In an Online Environment

The strategy can be executed in an online environment using Jupiter or JupiterLab on
the [Quantiacs personal dashboard](https://quantiacs.com/personalpage/homepage). To do this, clone the template in your
personal account.

### In a Local Environment

To run the strategy locally, you need to install the [Quantiacs Toolbox](https://github.com/quantiacs/toolbox).

## Strategy Overview

This strategy uses a stateful approach to manage long and short positions with specific exit conditions. It operates on NASDAQ-100 stocks and employs various indicators to make trading decisions.

### Key Features:
- **Universe:** NASDAQ-100 stocks
- **Trading Logic:** Positions are adjusted based on calculated signals, with conditional exits for taking profit, stopping loss, and day counting for short positions.
- **Indicators Used:** Simple Moving Average (SMA), Rate of Change (RoC), Average True Range (ATR), etc.
- **State Management:** Utilizes the Quantiacs state management system to maintain and update strategy state across different days.

### Strategy Components:
1. **Data Loading and Preparation:**
    - Load stock data using qndata.stocks.load_ndx_data.
2. **Strategy Function:**
    - Define the strategy function which computes the weights (positions) based on signals and applies exit conditions.
    - The strategy adjusts weights according to the trading logic and exits conditions.
    - Conditional exits are applied to manage risks and capture profits.
3. **State Management:**
    - Use state to manage positions and exits dynamically.
    - Due to the state requirement, this strategy and the exits only work with the multipass backtester
4. **Backtesting:**
    - Use the multipass backtester to evaluate the strategy performance over historical data.
    - Analyze the results and visualize performance metrics.

### Recommendations for Competitive Submissions:
- Limit the amount of exit functions to reduce computational demand.
- Keep in mind that exits that happen too often will also often trigger slippage penalties.
- Compare notebook statistics with the submission statistics to make sure there are no unintended interactions such as forward-looking.
