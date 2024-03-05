# Store Item Demand Forecasting

## Questions
You are given 5 years historical sales data from 50 different items at 10 different stores. Explore the dataset and answer the following questions:
1. How is the sales trend and growth rate over the 5 years?
2. How is the sales trend by different stores?
3. How is the sales trend by different items?
4. Do you have any recommendations for the growth of the stores?
5. Bonus: predict 3 months of sales for these 50 different items at 10 stores.

## Dataset
The `train.csv` contains 4 columns:
- `date`: Date of the sale data. There are no holiday effects or store closures.
- `store`: Store ID
- `item`: Item ID
- `sales`: Number of items sold at a particular store on a particular date.

The `test.csv` contains the test data that we need to predict.

## Main Finding

**Sales Trend over Month**

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/f6bab092-a889-4ef0-84a2-ca3532a1a320)

- From the plot, we can see the sales trend is always growing over the 5 years and grows fastest during 2013 to 2014

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/ae1ea08f-7506-4c72-8f21-d1db64cf0a07)

- From the plot, we can see the sales is always highest of the year at July, which may caused by summer vacation. In addition, during November, there is a small peak caused by Thanks' Giving Day.
- The time-series has seasonality pattern, such as sales are always low at the beginning of the year and high at the middle(festive season maybe) of the year and again low at the end of the year. 

**Growth Rate**

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/9b243608-464a-4907-bdb8-83e8929ba0ce)

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/edc55ac9-b46d-4af5-9944-697534f0ff34)


**Sales Trend by Store**

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/57ad0fd1-7e44-413c-91bf-7a3bfd68bf75)

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/b0c98941-ebe3-4a8a-bc52-72316a714a19)


## Model

**1. Determining Stationarity**

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/74035e52-6396-4921-bd69-ec74fc18958f)

- The plot clearly shows that the sales is unstable, along with its obvious seasonality.

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/0d940b27-d73b-4bfe-b2b0-f08dd2b43a6d)

**2. Model**

2.1 Linear Regression

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/e897724b-1968-4c8b-854e-5814d36b422d)

2.2 LSTM

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/ba21c156-3c73-469c-a707-8b9fd506e178)

2.3 ARIMA Model

- We are going to apply one of the most commonly used method for time-series forecasting, known as ARIMA, which stands for Autoregressive Integrated Moving Average.
- ARIMA models are denoted with the notation ARIMA(p, d, q). These three parameters account for seasonality, trend, and noise in data.
- AR: Auto-Regressive (p): AR terms are just lags of dependent variable. For example lets say p is 3, we will use x(t-1), x(t-2) and x(t-3) to predict x(t)
- I: Integrated (d): These are the number of nonseasonal differences.
- MA: Moving Averages (q): MA terms are lagged forecast errors in prediction equation.

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/17a78f13-16d7-4e01-8ce5-f0a8d5237468)

**3. Model Compare**

![image](https://github.com/Sol2023/store-demand-forecast/assets/92194263/2f4b82a5-66f2-43fc-92c0-b2110ab93000)
