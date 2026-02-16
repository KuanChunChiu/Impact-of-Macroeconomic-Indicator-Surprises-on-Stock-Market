# Impact of Macroeconomic Indicator Surprises on S&P 500 Return
## Project Description
Macroeconomic indicators play a central role in shaping financial markets by providing timely information on the health and direction of an economy. In the United States, indicators such as inflation releases, non-farm payrolls (NFP), and retail sales are closely monitored by economists, policymakers, investment banks, and portfolio managers. Prior to each release, professional forecasters submit their expectations to Bloomberg, which publishes a consensus forecasts representing the aggregated views of major financial institutions and research groups. Market participants often treat these published expectations as “baseline” values, and asset prices frequently respond not to the actual level of the indicator itself, but to the surprise or the difference between the realized value and the forecast. Unexpectedly strong job growth or
decline, an unanticipated acceleration in inflation, or sudden weakness in consumer spending can move U.S. equity indexes, Treasury yields, and other financial assets within seconds of release. Despite this widespread market belief that macroeconomic surprises “move markets,” the actual magnitude, and statistical strength of this relationship (particularly for daily S&P 500 returns) remains a more of an open question. Our project aims to quantify this impact using the ARIMAX and Bayesian linear regression model

## Study Results
ARIMA model - Effect size per 1 standard deviation
- NFP surprise: 0.00184
- PCE surprise: 0.00058
- Retail sales surprise: 0.00007

ARIMAX model - Reaction curve analysis

![ARRIMAX result](https://github.com/user-attachments/assets/def27c8f-42ec-4842-9585-1ad0d305aca2)

Bayesian linear regression model - Effect size per 1 standard deviation
- NFP surprise: 0.00045
- PCE surprise: 0.00006
- Retail sales surprise: 0.00005

Bayesian linear regression model - 95% credible interval
- NFP surprise: (0.0001, 0.0008)
- PCE surprise: (-0.00036, 0.00048)
- Retail sales surprise: (-0.0003, 0.0004)

Bayesian linear regression model - Probability of positive coefficients:
- NFP surprise: 0.9944
- PCE surprise: 0.6086
- Retail sales surprise: 0.6078

Bayesian linear regression model - Posterior predictive distribution under a positive shock for each macro-indicator

![Bayesian result 1](https://github.com/user-attachments/assets/e2c782bd-20cc-45eb-abc1-bbdc98e3e7bc)

Bayesian linear regression model - Posterior predictive distribution under a negative shock for each macro-indicator

![Bayesian result 2](https://github.com/user-attachments/assets/d2ca8b85-11b5-415f-a1fc-2a0de6d0cfd9)

## How to Install and Run the Program
### Dependencies:
  - scikit-learn >= 1.7.2
  - matplotlib >= 3.10.6
  - datetime >= 3.12.10
  - scipy >= 1.16.2
  - seaborn >= 0.13.2
  - pandas >= 2.3.2
  - numpy >= 2.3.2
  - forecast >= 8.23.0
  - ggplot2 >= 4.0.1
  - patchwork >= 1.3.2

### Instructions:
  1. Make sure all libraries in the above dependency list are installed to your current working environment, and the versions are all up to date
  2. Download the ipynb and R files from home and two csv files from the Data folder. The csv files contains the datasets while the ipynb and R files contain the python and R code that built this program
  3. Run the bayesian.ipynb file to generate the impact of macro-indicators on S&P 500 return using the Bayesian linear regression model.
  4. Run the arimax.R file to generate the impact of macro-indicators on S&P 500 return using the ARIMAX model. The impact from both models are quantified into numerical values and mapped to plots.

### Troubleshooting:
  - If there's error reading the csv files, make sure they're in the Data folder in your current working directory, and their names aren't modified after downloaded
  - If there's error with the libraries used, make sure they're all properly installed to your current environment, and the version are the same or newer than the versions in the dependency list
  - If there's error with running the files, make sure you specify the correct csv dataset names, imported the correct libraries without typos, and didn't make any modification on the files after downloaded them.     If necessary, download the ipynb and R files again or restart your computer before running again.

## How to Use the Program
### Running the ARIMAX model:
Run the arimax.R file, which will train and test the arimax model on the macro-indicator dataset and the S&P 500 dataset. The first output you see includes the the reaction curve of expected daily S&P 500 return under each indicator surprise. Another output is each indicator's effect size per 1 standard deviation on the S&P 500 return, showing the direction and magnitude the S&P 500 return is moved by each indicator surprise.

### Running the Bayesian linear regression model:
Run the bayesian.ipynb file, which trains and tests the Bayesian linear regression model on the macro-indicator and S&P 500 dataset. Same as the arimax model result, the first output includes each indicator's effect size per 1 standard deviation on the S&P 500 return. The second output is the 95% credible interval, showing the 95% range of indicator surprise coefficients. The third output is the probability that each indicator surprise's coefficient is positive, ranging from 0 to 1. Lastly, two plots are generated, showing the posterior predictive distribution of the S&P 500 return under a positive and negative shock of 2 SD from each indicator surprise.

### How to Interpret the Result:
The ARIMAX model results show that while macroeconomic surprises do influence daily S&P 500 returns, their effects are small relative to the dominant noise in equity markets. A +1 SD surprise in NFP increases expected returns by roughly 18 bps, core PCE surprises move returns by about 6 bps, and retail sales surprises have near-zero impact. Even though NFP exhibits a statistically meaningful coefficient, the model-implied volatility of 1.07% per day means these shocks translate into only modest shifts in the overall predictive return distribution. Scenario analysis further confirms that even extreme ±2 SD surprises generate
changes in expected returns that remain small relative to typical market fluctuations, reinforcing the conclusion that macro surprises don’t have much explanatory power for short-horizon equity movements.

For the Bayesian model, the key findings are that NFP surprise has the largest effect size per 1 SD, while the effect size of surprise in PCE and retail sales are minimal, suggesting NFP surprise is the most impactful indicator shock to the S&P return. In addition, the 95% credible interval of NFP surprise doesn’t include 0 and has a positive lower and upper bound, meaning we’re 95% certain that NFP surprise will have a positive impact on the S&P return. For the PCE and retail sales surprise, both of their credible intervals contain zero and have a negative lower bound and positive upper bound. This means for PCE and retail sales surprise, their impact on the S&P return can be positive or negative depending on where the coefficient lands in the interval, or even have no impact on the S&P return at all as the coefficients can potentially be zero. Next, the probability that the coefficient of NFP surprise is positive is 0.994, so it’s almost guaranteed that NFP surprise will have a positive impact on the S&P return. The probability for the coefficient of PCE and retail sales surprise to be positive is only 0.608 and 0.607, which is much lower and means these two indicator surprises can sometimes have positive impact while the other 40% of the time have negative impacts on the S&P return. 

## Analysis You Can Do With the Results
- Which of the three macro-indicators (NFP, retail sales, PCE) moves the S&P 500 return the most with their surprises?
- Do all 3 indicator surprises have positive impact on the market return?
- Which indicator has the least impact on the market return?
- Is there another indicator whose surprise also impacts the S&P 500 return a lot?
- In the ARIMAX model result, what's the relationship between the reaction curves and effect size per 1 SD for the 3 indicators?

## Contributors
1. Kuan-Chun Chiu (Myself) - beagledirk1@gmail.com
2. Paul Champagne - champagne.p@northeastern.edu
