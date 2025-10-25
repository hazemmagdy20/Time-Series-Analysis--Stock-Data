# Time-Series-Analysis--Stock-Data

This repository contains a comprehensive analysis of historical stock market data to explore key time series concepts and forecasting techniques.

**DataSet Columns:**

Open → starting price

High → highest price reached

Low → lowest price reached

Close → ending price

Volume → how actively it traded

Date → when the trading happened

Name → which company's stock it is


**Stock Time Series Analysis – Workflow Summary**

**🔹 Steps Performed**

1- Imported all necessary Python libraries and modules:

(Pandas, NumPy, Seaborn ,Matplotlib, Statsmodels)

2- Loaded the stock dataset:

Converted the Date column into a proper DatetimeIndex for accurate time series handling

3- Cleaned the data:

Dropped columns where all values are NaN

4- Exploratory Visualization:

Plotted the High price over time using the datetime index on the x-axis to observe overall price movement

5- Applied Resampling (Downsampling):

Converted daily data to monthly averages to simplify the view of trends and smooth short-term fluctuations

6- Autocorrelation Analysis (ACF Plot):

Checked for dependencies across time lags

Looked for repetitive peaks indicating potential seasonality


**🔹Stationarity Check – Before Differencing**

ADF (Augmented Dickey-Fuller Test)

P-value	= 0.99

Significance Level (α) = 0.05

Decision: ❌ Fail to reject H₀

**✅ Conclusion:**

The series is non-stationary → further transformation like Differencing required.


**🔄 Data Transformation**

7- Applied Differencing:

Calculated first difference to remove trend and stabilize variance

8- Smoothing using Moving Average:

Computed a rolling average to reduce noise and better highlight overall patterns (window = 120  => quarter)

9- Combined original and differenced High columns:

Visual comparison of effect of differencing

10- Removed rows containing NaN introduced by transformations



**🔹Stationarity Check – After Differencing**

P-value	 = 0.00

Significance Level (α)	= 0.05

Decision: ✅ Reject H₀

**✅ Conclusion:**

The transformed series IS stationary, and can now be modeled using techniques like ARIMA or SARIMA or others.
