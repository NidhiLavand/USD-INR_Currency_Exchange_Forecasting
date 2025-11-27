# USD-INR_Currency_Exchange_Forecasting
Exchange Forecast study using Time series analysis

# Project Overview
This project develops a classical time series forecasting pipeline to predict the USD/INR  exchange rate using historical data. The goal is to implement a robust forecasting model and set the foundation for deploying the trained model, potentially using frameworks like FastAPI or Streamlit.

# Methodology 
The project is structured into three distinct phases, each documented in a separate Jupyter Notebook:

1) Data_Collection.ipynb (Data Sourcing)

* Objective: To fetch and inspect the raw historical daily exchange rate data.

* Source: The data is typically sourced using the yfinance library for financial market data.

* Data Period: Daily USD/INR closing prices were collected for the period from 2015-10-27 to 2025-10-24.

2) EDA.ipynb (Exploratory Data Analysis)

* Objective: To understand the statistical properties, trends, and seasonality of the time series data.

* Key Findings:

a) The time series plot reveals a strong, consistent appreciation of the USD against the INR, with a visible acceleration in recent years.

b) Initial checks indicate the series is non-stationary, which is common in financial data, requiring transformation before modeling.

c) Techniques used include time series plots, rolling statistics, and seasonal decomposition.

3) Time_Series_Analysis.ipynb (Modeling and Forecasting)

* Objective: To preprocess the data, achieve stationarity, build a suitable time series model, and generate forecasts.

# Data Preprocessing:

a) The time series index was standardized to Business Day ('B') frequency.

b) Missing values (introduced by re-indexing for business days) were filled using time-based linear interpolation (method="time").

c) To achieve stationarity, the data was transformed using log differencing. Stationarity was verified using the Augmented Dickey-Fuller (ADF) and KPSS tests.

# Modeling:

a) Classical time series models, specifically Autoregressive Integrated Moving Average (ARIMA) models, were explored.

b) Model orders (p, d, q) were determined by analyzing the Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) plots of the differenced series.

c) The data was split into training and testing sets to evaluate model performance.

# Dependencies
The following Python libraries are required to run the notebooks:

Library	Purpose
pandas	Data manipulation and time series indexing
numpy	Numerical operations (e.g., log transformation)
matplotlib & seaborn	Data visualization (plots, ACF, PACF)
statsmodels	Time series analysis, stationarity tests (ADF, KPSS), and ARIMA modeling
yfinance	Data collection from financial markets (exchange rate)
datetime & timedelta	Handling date and time operations
You can install these dependencies using pip:


# Execute Notebooks: 
Run the Jupyter Notebooks in the following order:

1) Data_Collection.ipynb (To fetch the usd_inr_daily_raw.csv file)
2) EDA.ipynb
3)Time_Series_Analysis.ipynb

Note: (Data File) The pipeline relies on a data file named usd_inr_daily_raw.csv which is generated during the Data Collection phase.

# Future Work
The project sets the stage for several future enhancements:

1) Model Selection: Systematically compare the performance of various time series models (e.g., SARIMA, Prophet, LSTM) against the fitted ARIMA model.

2) Deployment: Implement the trained model using a web framework like FastAPI or Streamlit to create an interactive forecasting tool.

3) Volatility Modeling: Explore GARCH-family models to account for the time-varying volatility observed in the financial data's residuals.
