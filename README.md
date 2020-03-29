# Project 2 - Ames Housing Data and Kaggle Challenge


## Problem Statement
To predict as accurately as possible the sale price of a house based on the Ames Housing Dataset using regression techniques enhanced by feature engineering and regularization.
Additionally, the model should also help to perform inferential learning to provide homeowners with recommendation on the features that would fetch good sale price and those that would hurt the sale price. 

## Executive Summary

#### Background

This project examines housing data from Ames, IA with the goal of building a model to predict housing prices. The dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses.

The objective is to : 
1) Construct a regression model that accurately predict the sale prices of houses within test dataset.
2) Using Kaggle to practice the modeling process.
3) Provide business insights through reporting and presentation. 

#### Modeling Process and Evaluation

For modeling and performance measurement, the data are separated into a training and a test set.

1) Data cleaning was performed on both training and test set. Major cleaning performned that affected the data are as follows:<br>
    a) Dropped off columns with huge number of null values i.e. more than 250 cell with null values after checking their   correlation to sale price. Columns falling into this category are : Lot Frontage, Alley, FireplaceQu, Pool Qc, Misc Features, Fence<br>
    b) Replaced cell values with less that 250 cells with null values : 0 for numeric and NA for categorical columns<br>
    c) Related/ dependent columns were dropped off : Basement finished sqft1, Basement finished sqft2 and Basement unfinished sqft are redundant as these are summed up and stored in column : Total Basement Sqft.<br>
          
2) EDA involved the following studies:<br> 
    a) Correlation of features to sale price<br> 
    b) Correlation of fatures among themselves - looking out of multicolinearity<br>
    c) Distribution of numeric variables<br> 
    d) Spotting outliers and removing them to avoid noise learning by models<br>
    e) Normalized sale price to follow a normal distribution for the regressors to work better<br>
    
3) Preprocessing and Feature Engineering involved :<br> 
    a) Replacing oridnal columns with integer ranking.<br>
    b) Creating dummy variables for remaining categorical variables.<br>
    c) Train-test-split with 90% training set.<br>
    d) Standardizing training sets.<br>
    
4) Modeling, Evaluation and Final Prediction<br>
    a) Created 4 models - Linear Regression (LR), LR with regularization methods - Ridge, Lasso and Elastic Net.<br>
    b) The models were measures with R-squared (relative measure of model fit) and RMSE (absolute measure of model fit).<br> 
    c) The higher the R-squared and lower the RMSE, the more accurate the model is. The best model turned out to be Lasso. (not surprising)<br>
    c) The best model was selected to predict sale price in test dataset.<br> 
    d) The predicted saleprice was uploaded to Kaggle and scored RMSE Kaggle score of 21247.42348 which is the lowest thus far.<br> 
    e) The coefficients' information obtained from Lasso modeling can also be used for inferential learning resulting as recommendations to home owners on the features affecting the sale price of their property postively and negatively. 


## Conclusions and Recommendations

1) The importance of data cleaning and removing outliers cannot be stressed enough. It helped improve the R2 score by over 10%. Even though it is time consuming and rather dirty, the performance enhancement it brings to the accuracy/ scoring of the model is worth every bit of cleaning.<br>

2) The model shows strong R Squared score and is certainly a strong prediction model. Linear regression may be a basic prediction model, but prediction is not the only output of it. It helps much with inferential learning showing what factors influence the selling price of a house. This may well be more valuable than the predictions themselves.<br>

3) Addressed problem statement by developing a relatively accurate model to predict housing prices based on various features<br>
    - Top 3 features that can fetch higher sale price : Bigger houses, Well renovated (or good quality) houses and Newer houses<br>
    - Features that ma hurt the sale price : Unfinished basement, Houses located in commercial zone and Townhouses<br>

4) A lot more can be done to analyse the relationship between features like age of the property, year sold, style of the house etc. that may lead to next level of feature engineering.