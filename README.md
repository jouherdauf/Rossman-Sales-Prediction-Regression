# Retail Sales Prediction

Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied. This project includes various plots, graphs, visualizations, feature engineering, ensemble techniques, different machine learning algorithms with their respective parameter tuning, analysis, and trends. Predictions are made for 6 weeks of daily sales for 1,115 stores located across Germany.

## Data Files:

- **train.csv**: Contains information about each store.
- **store.csv**: Holds the sales info per day for each store.

The repository contains `main.py` that runs the main script from start to finish.

## 1. Business Problem

Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.

## 2. Solution Strategy

My strategy to solve this challenge was:

1. **Data Description**: Use statistical metrics to identify data distributions.
2. **Feature Engineering**: Derive new attributes based on the original variables to better describe the phenomenon that will be modeled.
3. **Exploratory Data Analysis (EDA)**: Explore the data to find insights and better understand the impact of variables on model learning.
4. **Feature Selection**: Selection of the most significant attributes for training the model.
5. **Machine Learning Modeling**: Train machine learning models.
6. **Hyperparameter Fine-Tuning**: Choose the best values for each of the parameters of the model selected from the previous step.
7. **Result and Conclusion from Modeling and EDA**

## 3. Machine Learning Model Implementation and Performance

| Regression Model         | Train MSE | Train RMSE | Train R2 | Train Adjusted R2 | Test MSE    | Test RMSE   | Test R2   | Test Adjusted R2 |
|--------------------------|-----------|------------|----------|-------------------|-------------|-------------|-----------|------------------|
| Linear Regression        | 1.214859e+06 | 1102.206527 | 0.844978 | 0.844975          | 1.217627e+06 | 1103.461202 | 0.844943 | 0.844929         |
| Lasso Regression         | 1.214485e+06 | 1102.036953 | 0.845026 | 0.845012          | 1.217348e+06 | 1103.334986 | 0.844979 | 0.844965         |
| Ridge Regression         | 1.214486e+06 | 1102.037084 | 0.845026 | 0.845022          | 1.217348e+06 | 1103.335147 | 0.844979 | 0.844965         |
| Elastic Net Regression  | 1.214485e+06 | 1102.036949 | 0.845026 | 0.845022          | 1.217348e+06 | 1103.334982 | 0.844979 | 0.844965         |
| Decision Tree Regression| 1.362364e+06 | 1167.203328 | 0.826156 | 0.826152          | 1.367349e+06 | 1169.337164 | 0.825877 | 0.825861         |
| Random Forest Regression| 5.596015e+04 | 236.558981  | 0.992859 | 0.992859          | 3.200686e+05 | 565.746016  | 0.959241 | 0.959238         |

## 4. Conclusion

### Conclusions from EDA:
1. Mondays have the most sales since most of the Sundays are closed.
2. Promotions seem to have a significant effect on sales but not on the number of customers.
3. Despite school holidays comprising only 19% of the total data points, the average sales during school holidays surpass those during no holidays.
4. Promo1 does not have a significant role in sales.
5. It is advisable to spend more on promos to get higher returns.
6. Store type 'b' has higher sales and customers per store than other store types. More Store type 'b' must be opened.
7. Assortment 'b' is available only at store type 'b' and it has more sales and customers than any other assortment. More assortment 'b' must be stocked to meet the demands of customers.
8. Weekly sales and customers peak in mid-December. It may be guessed that people buy drugs in advance just before the shops close for the holiday season.
9. In cases where there is less competition distance, sales values tend to be higher. This might be attributed to the possibility that in areas with higher demand, multiple stores are situated.
10. Sales are highest during December, this is because of Christmas, and in this month, the harshest winter starts in Europe so more people become sick.

### Conclusions from Modeling:
1. The linear regression model is the least accurate as it has very high coefficients of Assortment categories and Store type categories and it neglected features like customers, promotions which have a positive correlation with sales, so hyperparameter tuning is used to impose penalties on coefficients.
2. Decision Tree Model density distribution plot of sales varies highly with real data of sales.
3. Random Forest Regression has 99% accuracy for train data but 96% for test data, so this type of model can't be trusted, as the difference between train-test is very high.
4. The most accurate models are Ridge, Lasso, and Elastic-Net Regression, their train-test performances are almost similar, and coefficients are also similar.
5. The week of year line plot shows that Predicted Sales follows Actual Sales, with a variation of mostly $700, except for the last 2 weeks of the year.
