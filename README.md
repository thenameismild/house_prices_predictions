# Overview

In this project I am looking to predict housing prices from the data set provided. Through looking at the data and evaluating different possibility of uses for this information I have decided that I will be fousing on helping business optimized house pricing predictions for their clients.

My audience for this projects are real estate companies that are helping their client estimate their estate value. The problem I will be tackling is what are the features that are most helpful for the client to tell the real estate companies to allow them to help the client estimate their real estate price more accurately.

# The Data

I was giving a data test which contains all the information on the features and categories that the house has with their sale price, and another real estate data set with similar features and categories without the sale price to be use for the prediction model.

# The Model

In the project I decided to test the data using 4 models, linear regression, lasso model, ridge model and elasticnet. For each model I decided which model was the most suitable for the different features I selected to predict by using the model that return the lowest root mean squared error. 

Through the model tuning I created 8 separates model with different features input into the model to see what feature best fit the estimators. I started of my modeling using all the numeric data available which return great results however the estimations were still not accurate.

From then I decided to add the real estate categorical data like which neighnorhood they are located in or the finishes of the different part of the house. When I combine the categorical with the numerical data in the prediction model, it return better predicted results as show on kaggle. However, I still noticed some inconsistency with the prediction.

With that in mind I decided to take a closer look at the data and removed some outliers in the saleprice by evaluating the sale price Z-Score to help identify if there are any outliers. From the evaluation I found 33 outliers and removed then. Thus this process gave me the best estimation prices.

I then fitted the model with the selected data and returned a lasso regression that used 31 of the top categories from the data which were:

|Feature|Description|Coefficient|
|---|---|---|
|GrLivArea|Above grade (ground) living area square feet|18971.003120|
|OverallQual|Rates the overall material and finish of the house|1575.489225|
|BsmtFinSF1|Basement finished in square feet|6782.781007|
|YearBuilt|Original construction date|6745.577710|
|TotalBsmtSF|Total square feet of basement area|5670.125978|
|GarageArea|Size of garage in square feet|4999.199851|
|BsmtQual|Evaluates the height of the basement|4770.719978|
|KitchenQual|Kitchen quality|4760.743378|
|YearRemod/Add|Remodel date (same as construction date if no remodeling or additions)|3510.895258|
|Fireplaces|Number of fireplaces|3086.769381|
|LotArea|Lot size in square feet|2717.396769|
|BsmtExposure|Refers to walkout or garden level walls|2445.979788|
|Neighborhood_NoRidge|Physical locations within Ames city limits|2326.237397|
|Neighborhood_NridgHt|Physical locations within Ames city limits|2075.178767|
|Neighborhood_Crawfor|Physical locations within Ames city limits|720.392614|

# Evaluation
Through comparing this model coefficients to other model that I did shows that the top 5 categories are consistent with all the model while in the top 10 coefficients there are some similarities but some model have other columns like garrage cars in the categories of their model as well.

From looking at the final model, I believe that there could have been columns that could be removed, or when create dummes variable, there might be other options like One Hot Encoding or mapping categories to reduce errors point.

# Recommendations
From the information and modeling, I believe that the features that would add the most value to predict home prices are:
- Above Ground Living Area
- Overall Quality of the house
- Basement Area
- Garage Area
- Year Built
- Neighborhood

These categories can be use by business to help clients predict their house prices. However if the business wants to increase accuratecy they can ask their clients to provide more details for each category asked, for example:
- Evaluation of the quality and condition of the house basement
- If the house has been remodeled
- Evaluating the type of garage, the capacity or the finishes
- Location of the houses, ising zoning to indicate the type of residence
