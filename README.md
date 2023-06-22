# Forecast-app

### This web app is developed with streamlit and prophet
here is the application link: https://sunilgiri7-forecast-app-forecastapp-jgzz7s.streamlit.app/

## 1. Configure the model settings
Once loaded the data, the app allow the configuration of multiple parameters:

Horizon: the time in future to forecast. It is expressed in days.
Seasonality: choose beetwen Additive seasonality or Multiplicative seasonality. Useful when we can infer o have knoledge of the variation of volatility of the time series.
Trend components: declare which trends want to discover and propagate. Daily should be selected if loading a dataset with hourly data. Weekly: Prophet will search for thrend during days of the week (monday to sunday). Monthly: Prophet will search for trend during days of the month (1th to 31th). Yearly: will evaluate trend within months of the year( january to december) -Growth model: choose beetwen linear growth or logistic growth, to specify carrying capacity, for example if there is a maximum achievable point. The app allows then to specify cap and floor of the logistic model.
Holidays: add holidays to the model. Available countries at the moment: Italy, Spain, France, United States, Germany, Ukraine.
Hyperparameters: Change the scale of the changepoints or holidays. It impacts the flexibility of the model.

## 2. Fit the model and predict future
Initialize the model with the settings configured above (Fit)
Generate forecast (Predict): will plot forecast with standard Prophet charts
Show components: shows finding about time components selected in point 2.
## 3. Evaluate and validate prediction
Set the k-fold configuration: specify the initial timeframe to keep as training data, the horizon to predict and recurrency of the prediction as period.
Calculate the metrics related to the cross-validatio. A dataframe will be generated and a plot of the selected metric will be created.

## 4. Hyperparameter tuning
Runs the model with all the combinations possible within the matrix of coefficients of scaling. It return the best combination of changepoint ans seasonality prior scale, which can be used to go back above at point 2 and embed in the model and create an optimized forecast.

## 5. Export results
Export forecast(.csv) : will generate a link to download the dataframe with predictions and confidence intervals.
Export model metrics (.csv): will generate a link to downloa d the dataframe or the cross-validation
Export model configuration (.json): will export the configuration of the model for reproducibility of the results.

### Fork In your machine, Here is installation process
step1. conda create -n stan_env python=3.7
step2. conda activate stan_env

you need to install mingw-w64 compiler type:
step3. conda install libpython m2w64-toolchain -c msys2
step4. conda install numpy cython -c conda-forge
step5. pip install pystan OR conda install pystan -c conda-forge

Now you are good to go :)

# Author
Sunil Giri
connect in linkedIn for any queries 
last-updated: 22-06-23
