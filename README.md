# Food Sales Predictions Given Outlet Store Features

**Zach Hanson**: 

### Business problem:

In this program we are creating multiple different models to help a retailer understand the properties of products and outlet stores that play a role in predicting sales.

### Data
#### Source:
Big Mart Sales Prediction https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/
For this data set there is 8,523 rows and 12 columns.

#### Data Dictionary
![alt text](https://github.com/Zach-Hanson3/Food-Sales-Prediction/blob/main/images/datadict.PNG)



## Methods
- Started by removing the unnecessary features that were included with the original data
- Removed the item and outlet identifier, item weight, and outlet establishment year
 - Item identifier was removed because we were missing almost 20% of the data in this column. In addition, this is most likely not crucial in predicting an items outlet sales, as these models will be used to predict new items.
 - Outlet identifier was removed for similar reason to item identifier, as the specific store is likely not a factor in a new items sales. We are looking for a more general list of features that can be used at any location, not just the 10 specific stores listed.
 - Item weight was removed because it likely has no influence on an item's sales
 - Establishment year was dropped because it likely has no influence on an items sales
- After removing unnecessary features, some value errors in the data were corrected and inconsistencies in some columns were fixed
- Set of the data was copied, to prevent data leakage, and used in different visualization models
- Second set of the data was copied, and split into training and testing sets for machine learning
- Created a pipeline to impute the data, then scale or OneHotEncode the data, depending on the type (numerical or categorical)
- Created a linear regression model and investigated the RMSE and R^2 values this model gave us
- Created a Regression tree model and investigated the RMSE and R^2 values this model gave us

## Results
### Exploratory Data Analysis
![alt text](https://github.com/Zach-Hanson3/Food-Sales-Prediction/blob/main/images/Correlation_Heatmap.PNG)

This heatmap shows that there is a high correlation between an items MRP and its total outlet sales.


### Explanatory Data Analysis
![alt text](https://github.com/Zach-Hanson3/Food-Sales-Prediction/blob/main/images/outlet%20type.PNG)

Another large factor in an items outlet sales is the outlet type of the given store. We can see here that Supermarket Type 3 has just under double the total sales compared to Type 1 and Type 2, which in turn also have about four times the amount of sales as a grocery store.


## Model
### Models Used:
- Linear Regression Model
- Tuned Random Forest Regression Model

### Results of Models
- Linear Regression Model (Testing Set)
  - R^2: 0.5661
  - MAE: 805.49
  - MSE: 1,094,068.14
  - RMSE: 1,094.11
- Tuned Random Forest Regression Model (Testing Set)
  - R^2: 60.30
  - MAE: 728.48
  - MSE: 1,095,215.78
  - RMSE: 1,046.53

- The final model chosen was the random forest regression model with a max depth of 5 and n_estimators tuned to 300
- On the testing set of this model, 60.3% of the variance in total outlet sales was explained by our other features
- The Mean Absolute Error was off by around $728.48.
- The Mean Square Error was off by $1,095,215.78.
- The Root Mean Square Error was off by about $1,046.53.

## Recommendations

### Feature Recommendations:
- For an ideal outlet:
  - Medium Size
  - Supermarket Type 3
  - Tier 2 or Tier 3 location
  - If having to decide between features, size and location tend to have a much smaller impact on an items sales compared to outlet type.
  
### Model Recommendation:
- The best model is a tuned Random Forest Regression Model. There is still some bias in the model, but of our options this one performs the best by a few percentage points.


## Limitations & Next Steps

One main limitation was current limited knowledge of applying feature importance in a random forest model to refine our R^2 and RMSE values even more. Further steps would include finding outside resources to help understand how this is applied and continue refining this model. 


### For further information


For any additional questions, please contact **zhansonpdx@gmail.com**
