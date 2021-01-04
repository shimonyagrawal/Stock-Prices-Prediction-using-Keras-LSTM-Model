# Stock Prices Prediction using Kers LSTM Model

In this project, I extracted the TESLA stock prices data from Yahoo Finance for the time period of 5 years (January 2015 - December 2020). The main objective for the project is to predict the prices of Tesla Inc.stock 180 days in the future based off of the current Close price. I used Long Short-Term Memory (LSTM). LSTMs are widely used for sequence prediction problems and have proven to be extremely effective. The reason they work so well is that LSTM can store past important information and forget the information that is not.

### Data Preparation 

I created a new data frame containing only the target variable - Closing stock price and converted it into an array to train the model. For this project, traning dataset had 75% of values. With time series data, the sequence of values is important. The LSTM network expects the input data to be provided in 3D array structure: [samples, time steps, features]. Currently, the data is in the form: [samples, features] I transformed the train and test input data into the expected structure using numpy.reshape().
The first dimension is the number of records or rows in the dataset which is 1134 in our case. The second dimension is the number of time steps which is 180 while the last dimension is the number of indicators. Since I used only one feature, i.e Close, the number of indicators will be one.

### Building the model and making Predictions 

 A Long Short-Term Model was built using Keras which had 50 units, 4 hidden layers and a dense layer (output) to predict the normalized closing stock price. The model was compile using the mean squared error as loss function and to reduce the loss or to optimize the algorithm, I used the Adam optimizer. Lastly, the model was fit and passed to the training features and a test data set was created to get predictions.
