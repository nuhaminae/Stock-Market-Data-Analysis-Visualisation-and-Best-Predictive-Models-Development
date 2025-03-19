# Stock Market Data Analysis Visualisation and Best Predictive Models Development
The goal of the project was to develop a machine learning model capable of accurately predicting stock closing prices. This was achieved by collecting stock data from Yahoo Finance's API for four selected stocks—Apple (AAPL), Amazon (AMZN), Google (GOOGL), and Microsoft (MSFT)—across short, medium, and long time ranges. The data underwent thorough cleaning, feature engineering, and exploratory data analysis to prepare it for predictive modelling. Three models—ARIMA, LSTM, and Prophet—were evaluated, with LSTM emerging as the optimal model due to its balance of accuracy and computational efficiency. Key findings include strong positive correlations among stocks, inverse relationships between traded volumes and closing prices, and the successful enhancement of prediction accuracy through engineered features like volatility and moving averages. The results showcase the resilience of the stock market and the importance of leveraging historical trends for robust forecasting.

# ****************************************************************************
Check requirements.txt for list of dependencies (libraries used in the project)

# ****************************************************************************

# *There are two ways to run the code sucessfully*
# *1. To get the closing price prediction of the time when the code was written:*
  *-Save and move the .iypnb file to the models folder.*
  *- Comment out 'Stock Selection', 'Data Collection', 'Exploratory Data Analysis (EDA), and 'Feature Engineering' from 'Predicitve Modelling'.* 
  *- Run the following code snippet before running the first cell in model training.* 
  *- The dashboard is the last code in the notebook. After running the whole notebook: Historical Data Plot, Model Plot, Trained Model Plot, and Trained Model Prediction Plot can be explored.*

short_range_stocks= pd.read_csv('https://github.com/nuhaminae/Stock-Market-Data-Analysis-Visualization-and-Best-Predictive-Models-Development/blob/main/datasets/short_range_stocks.csv', header=[0,1])
short_range.drop(index=0, inplace=True)
short_range[('Unnamed: 0_level_0', 'Unnamed: 0_level_1')] = pd.to_datetime(short_range[('Unnamed: 0_level_0','Unnamed: 0_level_1')])
short_range.set_index(('Unnamed: 0_level_0', 'Unnamed: 0_level_1'), inplace=True)
short_range.index.name = 'Datetime'
short_range = short_range.sort_index(level=0, axis=1)
print(short_range.head())

medium_range= pd.read_csv('https://github.com/nuhaminae/Stock-Market-Data-Analysis-Visualization-and-Best-Predictive-Models-Development/blob/main/datasets/medium_range_stocks.csv', header=[0,1])
medium_range.drop(index=0, inplace=True)
medium_range[('Unnamed: 0_level_0', 'Unnamed: 0_level_1')] = pd.to_datetime(medium_range[('Unnamed: 0_level_0','Unnamed: 0_level_1')])
medium_range.set_index(('Unnamed: 0_level_0', 'Unnamed: 0_level_1'), inplace=True)
medium_range.index.name = 'Datetime'
medium_range= medium_range.sort_index(level=0, axis=1)
print(medium_range.head())


long_range= pd.read_csv('https://github.com/nuhaminae/Stock-Market-Data-Analysis-Visualization-and-Best-Predictive-Models-Development/blob/main/datasets/long_range_stocks.csv', header=[0,1])
long_range.drop(index=0, inplace=True)
long_range[('Unnamed: 0_level_0', 'Unnamed: 0_level_1')] = pd.to_datetime(long_range[('Unnamed: 0_level_0','Unnamed: 0_level_1')])
long_range.set_index(('Unnamed: 0_level_0', 'Unnamed: 0_level_1'), inplace=True)
long_range.index.name = 'Datetime'
long_range= long_range.sort_index(level=0, axis=1)
print(long_range.head())


# *2. To get the closing price prediction of the present time:*
  *- Save and move the .iypnb file to the models folder.*
  *- Remove the .keras files and run the code.*
  *- The dashboard is the last code in the notebook. After running the whole notebook: Historical Data Plot, Model Plot, Trained Model Plot, and Trained Model Prediction Plot can be explored.*

  

