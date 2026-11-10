# S&P 500 European Options Pricing Model
## Project Overview
This is an options pricing tool made in Python for theoretical European call and put S&P 500 options that uses the dividend adjusted Black-Scholes Model.

The user can input the option type (call or put), the strike price (k) and the time in years to maturity (T). In this program, T can range from 1 month to 30 years. The program calculates the theoretical European option price in S&P 500 index points.


## Estimated / Approximated Parameters
S, the underlying price, is taken to be the most recent closing price from whenever the model is run from S&P 500 index data obtained from Yahoo Finance.

q, the continuous dividend yield, is approximated to be 0.011 (https://www.dividenddata.co.uk/sp500-dividend-yields.py), which at the time of writing (10/11/26) is the most recent value for this for the S&P 500.

sigma, the annualised volatility, is estimated from the logarithmic returns of 2 years of historic closing prices from the S&P 500.

r, the risk free interest rate has been approximated by interpolating daily US treasury yields since they are considered to be approximately risk free. To make this tool more accurate, the data read by the program automatically updates to the newest available treasury yield date whenever it is run.
## Methodology
Using this information, the theoretical option price for the option specified by the user is calculated using the Black-Scholes model with a continuous dividend yield. Both the call and put option prices under the specified conditions are calculated, but the program only outputs the price of the option type that the user entered.

To check for consistency, the calculated call price and put price under the specified conditions are substituted into the dividend adjusted Put-Call Parity Equation, and the output tells you whether the equation has been satisfied or not.
## Assumptions & Limitations
The prices calculated are theoretical estimates; this tool estimates future volatility from historical volatility, however in real life, past volatility may not indicate what future volatility will be like as this depends on many factors, so this assumption has been made for simplicity. The continuous dividend yield has been assumed to be constant, which is not the case in real life. The risk-free interest rate has been approximated using US treasury yield data, which is not continuously compounding and is not completely risk-free, however it is widely considered to be incredibly low risk, so it has been used as an approximation. 
## Running the Project
1. Clone or download this repository.
2. Install the required Python libraries: numpy, pandas, yfinance, scipy, fractions and datetime.
3. Open the Jupyter Notebook in a compatible environment.
4. Run all the notebook cells in order and enter values when prompted.