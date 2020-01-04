# CoY2.TaxiFareRF
Year of Code - Day 2 | Taxi Fare Predictions Using randomForest()

For today's coding challenge, I used the project resources that DataCamp offers to get introduced to analyzing datasets using the random forests.

In this project, the tidyverse package was used to manipulate the data. The main function and uses were:
  
  - Mutate() : Addinf new colums to the dataset to use in our analysis                  
  - Rename() : Clean the dataset variables that would make working with predictive modeling easier
  - Filter() : Eliminating any values that would indicate an invalid taxi ride
  
After cleaning the dataset and prepping it for analysis, the first heat map was generated to visualize where most taxi riders are starting their rides. This is useful to guide our final analysis at the end of the project. By seeing where most riders start, we can see a trend occur - most riders started in midtown compared to downtown or uptown.

Using this trend to drive our prediction models, we start to use the tree() function located in the tree package. This allows for a tree diagram to visualize the relationship between total fare amount [log(fare_amount + tip_amount)] and the prediction variables - longitude and latitude.

This proves to be a frugal visualization, as it states any latitude > 40.7237 constituted a fare that was comparably greater in value. The longitude variable was dropped from this visual, as the model declared it did not offer any usefulness in predicting total fares.

Adding time may be a great predictor variable. By using the lubridate package, we begin to define new variables [hour,wday,month]. To no avail, the tree did not change with the addition of these new variables.

The tree() functionality proves to be inadequate in deriving a strong relationship between total fare and latitude. By introducing the randomForest() function to the process, we can now fit multiple trees to subsets of the dataset to capture smaller variable trends and relationships.

We used the newly fitted forest model to visualize 2 ggmap() items that illustrate the: (1) Fare Predictions in Manhattan; (2) Mean Fare Predictions in Manhattan.

These can be useful to get a full picture of how the model predicts fare totals using the randmoForest() methodology. We can see that, with trip volume (heat map1), lower ride density in Manhattan correlates to more expensive fare totals.

.
.
.

If you have any questions regarding my write-up or have any corrections regarding my communicated analysis, please feel free to contact me!

