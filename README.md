# Stock Predictor RNN
In this project I build an LSTM neural network in Keras used for predicting stock prices. In order to apply our LSTM we treat the time series prediction problem as a regression problem, and so need to use a sliding window to construct a set of associated input/output pairs to regress on.  This process is animated in the gif below.

<img src="images/timeseries_windowing_training.gif" width=600 height=600/>

For example - using a window of size T = 5 (as illustrated in the gif above) we produce a set of input/output pairs like the one shown in the table below. Each input is a sequence (or vector) of length 4 (and in general has length equal to the window size T) while each corresponding output is a scalar value.  Notice also how given a time series of length P and window size T = 5 as shown above, we created P - 5  input/output pairs.  More generally, for a window size T we create P - T such pairs.

This means that each prediction of the LSTM is one day ahead of the input data. The LSTM is successfull in making these predictions, but the applications are limited.

The model has also been applied to predict mutiple days into the future by making predictions based on prior predictions. The results of this experiment create an asytotic prediction.

The results can be found in the Jupyter Notebook
