## Predicting Air Pollution - Multiple Time Series Forecasting

*GitHub Repository Link:* <https://github.com/harshulvarma/air_pollution_prediction>

### Overview

The goal of the project was to forecast multiple time series consisting of air pollutant levels 1 week ahead using 18 years of air pollution data. The following steps are taken in the corresponding notebooks:

- **Data Preprocessing**:
  - Examining the data integrity
  - Selecting air pollutants for prediction
  - Dealing with missing values via appropriate interpolation
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/1_data_preprocessing.ipynb>
  
- **Data Visualisation**:
  - Analysing distribution of each air pollutant levels using histograms
  - Finding correlation via pairplots and visualising time series line plots at various granularity (year, month, week, hour etc.)
  - Final prediction task was also chosen here to be 1 week ahead with data being grouped weekly
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/2_data_visualisation.ipynb>
  
<img src="trend.png?raw=true"/>

- **Decompostion and Stationarity**:
  - Determining Seasonality and Trend of time series via decomposition
  - Looking at autocorrelation for lagged autoregressive feature
  - Identifying if the time series are stationary using Augmented Dickey Fueller test
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/3_decomposition_stationarity.ipynb>
  
- **Baseline Forecasts**:
  - Naiive Forecasts with 1 week lag as the prediction
  - Seasonal Naiive Forecasts with 1 year (52 weeks) lag as the prediction
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/4_baseline_forecasts.ipynb>
  
- **Gradient Boosted Trees Forecasts**:
  - Conducting feature engineering for features such as week of year, month, autoregressive lags, autoregressive lag residuals/errors and moving averages.
  - Prediction done using LightGBM library due to faster model fitting and ability to pass categorical features
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/5_gradientboostedtrees_forecasting.ipynb>
  
- **Long Short Term Memory - Recurrent Neural Network Forecasts**:
  - Forcasting using many-to-many LSTM-RNN architecture
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/6_LSTM-RNN_forecasting.ipynb>
  
- **FB Prophet Forecasts**:
  - Using Facebooks' Prophet model for forecasts
  - <https://nbviewer.jupyter.org/github/harshulvarma/air_pollution_prediction/blob/main/7_FB_Prophet_forecasting.ipynb>
  
### Results

Each model and their mean sMAPE and RMSE across all time series forecasts are as follows:

Model | sMAPE | RMSE
------------ | ------------- | -------------
Naiive  | 24.06 | 7.74
Seasonal Naiive | 29.49 | 9.08
Gradient Boosted Trees | 17.70 | 4.03
LSTM RNN | 24.35 | 5.88
FB Prophet | 27.73 | 3.44

<img src="predictions.png?raw=true"/>

For future iterations, hyperparameter tuning can be conducted. Additionally since there seemed to be some correlation between the time series as well, they can be used as features for predictions in the ML models. Other features such as traffic flow, wind, temperation and humidity can be also utilised.

### Tools Utilised
- pandas
- seaborn
- matplotlib
- statmodels
- LightGBM
- Keras
- Tensorflow
- FBProphet
- scikit-learn




