# Neural-Network-with-Financial-Time-Series-Data

# Introduction:
Time series is an important part of financial analysis. Today, you have more data, more data sources, and higher frequency of data. New sources include new exchanges, social media and news sources. Today, delivery frequency has been increased from dozens of messages every day to hundreds of thousands of messages per second. Therefore, the results will bring more and more analytical techniques. Most modern analytical techniques are not different, and they all have a statistical basis, but their applicability follows the available computational capabilities. The increase in available computing power is faster than the increase in the number of time series data, so it is now possible to analyze large-scale time series in an unprecedented way. This neural network predicts the future movement of the index and achieves a reasonably well result.

# Content:
It downloads the stock/ index data from an online information provider, then forms a pandas DataFrame that contains open, high, low, close and is compatible with the TensorFlow library and Keras. Finally, a LSTM recurrent neural network will be implemented to train and predict. It also creates a visualized result for the ease of presentation. Optimized Hyperparameters arre also provided at the end.

# Error
1. Please notice that I created this model with pandas 0.19.2 and I will update it to support pandas 0.20
2. Recently, pandas datareader is not available for downloading stock data, I am currently working on downloading data from Quandl.

# How it works:
The efficient market hypothesis (EMH) states that price cannot be predicted based on previous price and this model clearly violates the EMH. It attempts to understand the market sentiment behind price trends rather than analyzing a security's fundamental attributes. In order to strengthen the market sentiment analysis, a sentiment analysis model or event driven prediction model will be added. Hopefully, the result would be slightly better than a random guess. The model is currently overfitting and more updates will be provided.

# Versions
After receiving feedbacks that stock price is very close to the previous price and thus regression is inappropriate. From now on, there will be 2 methods to predict the stock price.

1. Prediction with 22 previous days (Original) (Regression)

Filename: LSTM_Stock_prediction_20170507.ipynb

2. Prediction with 22 previous days (Modified) (Classification)

Filename: TBA


# Future improvement:
1. Moving average will be added
2. Uses more fundamental data to predict the price of stock.
3. Sentiment analysis
4. Train the model with 3000 US stocks.
5. Deep Q learning for portfolio optimization and risk
6. Regularization will be added to avoid overfitting.
7. Quantopian Zipline will be used for backtesting
8. LSTM convolutions network 


# Result:
Lastest LSTM model result for 7 years of testing data that has not been trained:

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/result2.png)

Train Score: 0.00006 MSE (0.01 RMSE)

Test Score: 0.00029 MSE (0.02 RMSE)

# Hyperparameter
# The following result will be deleted and modified soon because it was based on testing data, not crossvalidation data.
After serveral tests,

For dropout, the result is shown as below. Dropout of 0.2, 0.3 would be fantastic

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/dropout.png)

For epochs, the result is shown as below. Epochs less than 100 would be sufficient.

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/epochs2.png)

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/epochs.png)

For number of neurons, [256, 256, 32, 1] and [512, 512, 32, 1] would be ideal for this model.

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/neurons.png)

For weight decay, after serveral tests, 0.4 and 0.5 would be good.

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/decay2.png)

For the days of stock price included (window), after serveral tests, 10 days would be ideal.

![Alt text](https://github.com/BenjiKCF/Neural-Network-with-Financial-Time-Series-Data/blob/master/window.png)

# Update:
26/03/2017 First update
1. Recurrent neural network with LSTM is added to the code. 
2. Keras with tensorflow is also implemented. 
3. Tensorboard for neural network visualization is also added to the code.

14/04/2017 Second update
1. Normalized adjusted close price. 
2. A new data downloader has been implemented for simplicity
3. Added more variable to predict the adjusted close price
4. More accurate result, significantly less mean square error
5. Extra visualization for close price
6. Denormalization will be fixed soon
7. Twitter sentiment analysis is currently on testing stage

16/04/2017 Third update
1. Updated denormalization 
2. More test results available

18/04/2017 Fourth update
1. Updated fundamental data from Kaggle for NYSE 

19/04/2017 Fifth update
1. Supporting Python 3.5 on Windows 10
2. Significant improvement in accuracy

29/04/2017 Sixth update
1. ^GSPC Data since 1970 has been added, more training data, higher accuracy
2. 7 years of test data 
3. Object oriented programming
4. Hyperparameters for dropout has been tested

08/05/2017 Seventh update
1. All Hyperparameters have been tested and results have been uploaded.
2. Fixed comment for the data loader
3. More technical analysis like volume, moving average and other indexes will be added

# References:
Bernal, A., Fok, S., & Pidaparthi, R. (2012). Financial Market Time Series Prediction with Recurrent Neural Networks.

Box, G. E., Jenkins, G. M., Reinsel, G. C., & Ljung, G. M. (2015). Time series analysis: forecasting and control. John Wiley & Sons.

Jaeger, H. (2001). The “echo state” approach to analysing and training recurrent neural networks-with an erratum note. Bonn, Germany: German National Research Center for Information Technology GMD Technical Report, 148(34), 13.

Jaeger, H. (2002). Tutorial on training recurrent neural networks, covering BPPT, RTRL, EKF and the" echo state network" approach (Vol. 5). GMD-Forschungszentrum Informationstechnik.

Maass, W., Natschläger, T., & Markram, H. (2002). Real-time computing without stable states: A new framework for neural computation based on perturbations. Neural computation, 14(11), 2531-2560.
