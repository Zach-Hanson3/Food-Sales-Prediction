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
This heatmap shows that there is a high correlation between Item Outlet Sales and the items MRP.

### Explanatory Data Analysis
![alt text]()
Another large factor in an items outlet sales is the outlet type of the given store. We can see here that Supermarket Type 3 has just under double the total sales compared to Type 1 and Type 2, which in turnu also have about four times the amount of sales as a grocery store.

## Model

Our final model uses a random forest regression model to predict an items outlet sales.

This model has a RMSE of 1,047 units sold, and an R^2 of 0.6030.

This means our model can predicty an items outlet sales with an error of around 1,050 units, and the features of this model can account for about 60% of the variance in the target value.

## Recommendations:

In general, the most ideal outlet would be a medium size, supermarket type 3, located in a tier 2 or tier 3 location. Of these features, the size and location tend to have a significantly smaller impact on an items sales compared to the type of outlet.


## Limitations & Next Steps

One main limitation was current limited knowledge of applying feature importance in a random forest model to refine our R^2 and RMSE values even more. Further steps would include finding outside resources to help understand how this is applied and continue refining this model. 


### For further information


For any additional questions, please contact **zhansonpdx@gmail.com**