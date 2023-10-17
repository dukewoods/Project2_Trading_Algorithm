# Machine Learning Trading Algorithm with BTC/AUD

This README has been created to define our project scope and overview of the Machine Learningproject. Exploring the problem, questions, datasources and goals. 

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Data Collection](#data-collection)
- [Data Analysis](#data-analysis)
- [Projections](#projections)
- [Contributing](#contributing)
- [License](#license)

 ___ 
# Introduction

Our Machine Learning Algorithm Project has been created to assess the performance of various trading algorithms against the historic cumulative returns of Bitcoin against the Australian Dollar. We utilise data from yfinance to create a standard dataframe of historic BTC prices to benchmark each algorithms performance. During this project we identify the model with the greatest returns against historic cumulative returns between January 2018 and October 2023. With this assessment a model with the greatest returns will be determined. The training and evaluation of models will be assessed. 

___
# Installation
This guideline is provided to support installation of new packages and/or files required to utilise the Project 2 models. 
### Installation - TA-Lib (Technical Analaysis Library)
##### Requirements
* Requires Homebrew (MAC)
* Requires Python and Pip (Windows)

#### Install (MAC OS)
 * Open a new terminal window
 * Use Homebrew to install TA-Lib:

```shell 
 brew install ta-lib
```

* Verify installation

```shell
ta-lib-config --libs
```

#### Install (Windows)
* Download TA-Lib's binary (32-bit or 64-bit) for Windows from the official website: https://www.lfd.uci.edu/~gohlke/pythonlibs/#ta-lib
* Choose the version compatible with your Python installation (e.g., cp39 for Python 3.9).
* Download the file with a .whl extension, e.g., TA_Lib‑0.4.0‑cp39‑cp39‑win_amd64.whl.
* Open your terminal or command prompt.

* Navigate to the directory where you downloaded the .whl file.

* Install TA-Lib using pip. Replace the file name with the one you downloaded:

```shell
pip install TA_Lib-0.4.0-cp39-cp39-win_amd64.whl
```
* Verify the installation by running:

```shell
python -c "import talib; print(talib.__version__)"
```

___
# Usage

1. Complete the Installation instructions above for your Operating System.
2. Open notebook/
3. Run the notebook
   
___
## Data Collection
To commence the analysis a csv file was downloaded from yfinance to provide the daily close price of BTC/AUD. This data is then imported into each note book with the Pandas library. For our analysis the time frame downloaded was January 2018 until October 2023. 

___
## Data Analysis
###### Importing Libraries
The notebook begins by importing the required libraries to complete the analysis. Libraries include data manipulation packages such as pandas and visualisation packages such as matplotlib. New packages in this model are TA-Lib which is a library popular for technical analysis in trading and finance. 

##### Importing the BTC-AUD Dataset
Read tje Bitcoin-Australian Dollar dataset from a CSV format into a pandas dataframe, this dataset contains the open, high, low, close, adjusted close prices and trading volumes. 

##### Get Insights of the data
Utilise 'hvplot' to create a line plot of BTC closing prices over time. Print summary statistics of the dataset too such as the count, mean and standard deviation. 

##### Create RSI Indicator
Define a function called 'calculate_rsi' to compute the Relative Strength Index (RSI) for the dataset, given a specific time period. The RSI is calculated based on daily price fluctations and add these RSI values into the DataFrame.

##### Create Daily Returns and Signal for +/- Daily Returns
Compute daily returns for Bitcoin closing prices using the pct_change method. Generate trading signals based on daily returns: 
* 1 for buy (long) signals when returns are positive
* -1 for sell (short) signals when returns are negative.

##### Create Linear Regression Model
Prepare the features (X) and target variable (y) for linear regression modeling and split the data into training and testing sets.
Initializes a linear regression model and fit the model to the training data. Finally, predicts target values on the test data and store the results in a DataFrame.

##### Calculate Performance Metrics
Compute a couple of performance metrics for the linear regression model, including Mean Absolute Error (MAE), Mean Squared Error (MSE), and R-squared (R2) score.

##### Plotting
Create a plot comparing the actual and predicted returns from the linear regression model, save this plot as 'linear_regression_plot.png'.
___

