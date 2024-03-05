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

