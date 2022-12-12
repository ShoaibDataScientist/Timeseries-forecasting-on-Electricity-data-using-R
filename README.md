# Timeseries-forecasting-on-Electricity-data-using-R
This repository is aiming to Time Series Forecast over a given dataset. The goal of the exercise is to find the most appropriate model and make some predictions. 
## Time-Series Modelling
Data split-ted into training and test set. 80% for training and 20% for testing
![image](https://user-images.githubusercontent.com/61366086/207009163-ccd3cccf-f3c3-4f9c-8b22-0664c631ba98.png)

# Exponential Smoothing
## Simple Exponential Smoothing (SES)
![image](https://user-images.githubusercontent.com/61366086/207009342-7afb1be6-6121-4b4f-8df2-18bf48910e02.png)
These models do not fit well.

Lets try to consider the seasonal and linear trends.
# Additive Seasonal Holt-Winters Model
![image](https://user-images.githubusercontent.com/61366086/207009511-a0c772f9-20b1-4065-891f-5834ce7b73b1.png)
These models are still not good.

Now We can try to stabilize the variance using a Box-Cox transformation with the additive Holt-Winters model.
![image](https://user-images.githubusercontent.com/61366086/207009583-37cfc56c-7808-4b39-80ae-425689fe6869.png)
This shows an improvement compared with the previous models.

Now we compute the root mean square error (RMSE) of each model to assess model fit.
The model with the lowest error so far is dampened multiplicative Holt-Winters. However, this is not necessarily the best model because the prediction pattern does not correlate with the pattern of the test set. Instead, the mean error is low because the prediction is compressed in the center part of the chart.
# ARIMA
Now we fit an autoregressive integrated moving average model (ARIMA):
![image](https://user-images.githubusercontent.com/61366086/207009864-107239db-a471-471e-b813-ad9c6648d2ae.png)
This model is an improvement on previous attempts, but is still not ideal

# Neural Network Auto-Regression
Neural Network Auto-Regression models take a machine learning approach and provide more flexibility compared with parametric statistical models
![image](https://user-images.githubusercontent.com/61366086/207010030-4298dd81-5320-4e2f-9c81-894bb82e075a.png)
# Time Series Linear Regression
Estimate the effect of temperature on electricity consumption using a time series linear regression model (TSLR):
![image](https://user-images.githubusercontent.com/61366086/207010218-c9e10a46-abee-4602-9656-2deb4aa11289.png)
![image](https://user-images.githubusercontent.com/61366086/207010245-739e8858-133a-4d55-a753-121989ae91e2.png)

# Conclusion
Of all models fitted, the neural network model with temperature as an additional predictor gives the best fit to the data.

The main advantage of NNAR is the added flexibility to model non-linear trends such as that seen with our data.
Special credit to:
https://github.com/IsmaelMekene
