# Time-Series-Forecasting

## Contents
1. Introduction
2. Approach
3. Results

Introduction

A time-series data is a series of data points or observations recorded at different or regular time intervals. Time-Series Forecasting is the process of using a statistical model to predict future values of a time-series based on past results. A time series analysis encompasses statistical methods for analyzing time series data. These methods enable us to extract meaningful statistics, patterns and other characteristics of the data.
Time series forecasting can be applied in various fields such as in sales and demand forecasting, weather forecasting, econometrics, signal processing, pattern recognition and earthquake prediction.
My interest, however, lies in its application in weather forecasts. The dataset used in this forecast and analysis contains meteorological information over Accra, the capital of Ghana from
1950 to 2013. 

Approach

The dataset had four fields i.e is Date, Rainfall, Tmin and Tmax. Dataset contained 23,276 rows with missing values observed in some fields. To determine the Average temperature observed over 
this period, the data was first cleaned and missing values were imputed using the mean of each field. After cleaning and filling missing data, a new column; AvgTemp is created. This column
holds the average temperature of Accra. This is done by adding both the Min Temp and Max Temp and dividing it by 2. The data points are then plotted to observe outliers. Outliers are removed using the
inter-quartile range. Next, the dataset is tested for a stationarity using the augmented dickey fuller test. P-value obtained is less than 0.05 which means data is stationary. 
The AutoregRessive Integrated Moving Average (ARIMA) is used in this forecast. 
There are three distinct integers (p, d, q) that are used to parametrize ARIMA models. Because of that, ARIMA models are denoted with the notation ARIMA(p, d, q). Together these three parameters account for seasonality, trend, and noise in datasets:

p is the auto-regressive part of the model. It allows us to incorporate the effect of past values into our model. Intuitively, this would be similar to stating that it is likely to be warm tomorrow if it has been warm the past 3 days.

d is the integrated part of the model. This includes terms in the model that incorporate the amount of differencing (i.e. the number of past time points to subtract from the current value) to apply to the time series. Intuitively, this would be similar to stating that it is likely to be same temperature tomorrow if the difference in temperature in the last three days has been very small.

q is the moving average part of the model. This allows us to set the error of our model as a linear combination of the error values observed at previous time points in the past.

 A “grid search” is used to iteratively explore different combinations of parameters. The Akaike information criterion (AIC) with the lowest score is used to fit the best performance model.
 In this case, the lowest AIC score is ARIMA(1, 0, 1)x(1, 0, 1, 12) with a score of 635.3346958078906.
 
 
 Results 
 
 The one-step ahead forecast produced a mean squared error of 0.12 whereas the mean squared error for the dynamic forecast is 0.18. I further run the model 300 steps ahead, 
 which showed a general upward trend in average temperature, which corresponds with rising global temperatures worldwide. Further research could look at using time series forecast 
 as a risk management tool to be used to hedge against weather related risks. For e.g Weather derivates. 
