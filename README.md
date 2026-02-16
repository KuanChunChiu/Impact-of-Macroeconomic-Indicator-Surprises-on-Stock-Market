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


### Running the Bayesian linear regression model:


### How to Interpret the Result:


## Analysis You Can Do With the Results
- 
- 
- 
- 
- 

## Contributors
1. Kuan-Chun Chiu (Myself) - beagledirk1@gmail.com
2. Paul Champagne - champagne.p@northeastern.edu
