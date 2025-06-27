# Quantitative Forex Strategy: Mean Reversion Backtest

## Objective
This project builds and evaluates a mean-reversion trading strategy applied to the Forex market. The goal was to test if the AUD/NZD currency pair exhibits stationary (mean-reverting) behavior and if a strategy based on Z-scores could be profitable from January 2015 to June 2025.

This project demonstrates a complete workflow for testing a statistical arbitrage-style strategy on non-equity assets.

## Key Features
* **Data Acquisition:** Downloads historical daily Forex data for the `AUDNZD=X` pair using the `yfinance` API.
* **Statistical Validation:** Performs an Augmented Dickey-Fuller (ADF) test using the `statsmodels` library to statistically verify the stationarity of the price series.
* **Signal Generation:** Calculates a rolling Z-score to identify when the currency pair has significantly deviated from its historical mean.
* **Backtesting Engine:** Simulates trades based on Z-score thresholds (entering on +/- 2.0, exiting on a return to the mean) and calculates the portfolio's equity curve over time.
* **Performance Analysis:** Computes key metrics, including the annualized Sharpe Ratio and Total Return, to objectively evaluate the strategy's performance.

## Results & Conclusion
The statistical analysis and backtest yielded a clear outcome.

* **ADF Test P-value:** 0.0001 (Strongly suggesting the series is stationary)
* **Annualized Sharpe Ratio:** 0.01
* **Total Return:** -0.11%

**Conclusion:** Despite the strong statistical evidence of mean-reversion in the AUD/NZD pair, this specific strategy with a 60-day lookback window and +/- 2.0 Z-score thresholds was **not profitable**. The strategy produced no risk-adjusted returns and resulted in a slight net loss. This highlights that a statistical property alone does not guarantee a profitable strategy without further optimization of parameters and risk management rules.

## How to Run This Project
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd YOUR_REPOSITORY_NAME
    ```
3.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Run the Jupyter Notebook.**

## Libraries Used
* pandas
* numpy
* yfinance
* matplotlib
* statsmodels