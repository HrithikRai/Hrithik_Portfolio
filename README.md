# Hrithik_Portfolio
Hey there...Glad you landed here...These are some of my Data Science Projects.

# Project 1 - Regression Analysis - Bike Sharing Demand Estimation
## Kaggle competition - [Bike Sharing Demand](https://www.kaggle.com/c/bike-sharing-demand)

* This Bike sharing system will function as a sensor network, which can be used for studying mobility in a city. Here we combine historical usage patterns with weather data in order to forecast bike rental demand in the Capital Bikeshare program in Washington, D.C.
* Used a multilinear regression model. You can find the project [here](https://github.com/HrithikRai/Bike-Sharing-Demand-Prediction)
* Bike sharing demand prediction using hourly dataset (17379 rows, 17 features)
* Took care of Multiple Linear Regression Assumptions :
  1. Autocorrelation
  2. Multicollinearity
  3. Endogeneity
  4. Residual Normality
* Libraries used - Pandas,Numpy,Matplotlib,Math,sklearn
* RMSLE score of the predictor = 0.3560. **This falls under the top 1 percentile(<0.367) of the Kaggle Bike Prediction Comp.**

## Visualizations and Inferences:
![](https://github.com/HrithikRai/Hrithik_Portfolio/blob/main/Images/Figure%202021-04-22%20155256.png)
Relation between **Continuous variables and Demand.**
* Higher the windspeed, lower the demand
* Temperature and Demand seems to be directly correlated
* Plots of temp and atemp are almost identical pointing out to some correlation, therefore a multicollinearity check is reqd.
* Humidity and Windspeed affects demand but need more statistical analysis like correlation coefficient check

![](https://github.com/HrithikRai/Hrithik_Portfolio/blob/main/Images/Figure%202021-04-22%20155327.png)
Relation between **Categorical variables and Demand.**
* Park bikes near public transport in morning and office premises in the afternoon
* Weekday doesn't affect the demand therefore can be dropped
* Year doesnt affect since only 2 years given

### Correlation Matrix
![](https://github.com/HrithikRai/Hrithik_Portfolio/blob/main/Images/matrix.png)
* Drop a temp since showing high multicollinearity with temp
* Also humidity has a high correlation with wind speed. And windspeed has low Correlation with demand. 
* Therefore windspeed could be dropped.

### Autocorrelation
![](https://github.com/HrithikRai/Hrithik_Portfolio/blob/main/Images/Figure%202021-04-22%20155420.png)
* High auto-correlation upto 5 previous values(Top 3 > 0.8).
* Since autocorrelation is the dependent variable, we can't get rid of it.

### Log Normalizing the Dependent Variable - Demand
![](https://github.com/HrithikRai/Hrithik_Portfolio/blob/main/Images/demand.png)

## Therefore after fitting the processed data into our regressor:
* RMSE Score - 0.380
* RMSLE Score - 0.356

