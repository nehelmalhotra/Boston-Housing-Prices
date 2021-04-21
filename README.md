# Boston House Price Prediction <!-- omit in toc -->

Real-estate seems to be really hot currently, with a lot of people looking to make the most of the low interest rates to buy their dream house or invest for the future. 

#### -- Project Status: [Completed]

# Table of Contents <!-- omit in toc -->

- [Synopsis](#synopsis)
- [Dataset](#dataset)
  - [Summary of the Dataset](#summary-of-the-dataset)
  - [Exploratory Analysis](#eda)
- [Data Cleaning and Feature Engineering](#cleaning)
- [Model fitting and ensembling](#ensembling)
- [Conclusion](#conclusion)

# Synopsis <a name="synopsis"></a>

The hosuing market has been really hot the past few years due to the really low interest rates. In the project we will train a supervised model to predict the house prices in Boston based on parameters such as number of rooms, area, year built, etc. 

We will use Tableau for the Exploratory analysis and ensembling techniques to predict the final prices!

# Dataset <a name="dataset"></a>

The datasets used for this part of the project can be found on Kaggle: 

https://www.kaggle.com/c/house-prices-advanced-regression-techniques

## Summary of the Dataset <a name="summary-of-the-dataset"></a>

 - The dataset contains over 1460 records and 80 features. These features include things such as number of rooms, lot area and year the house was built.
 - The contains a number of missing and mis-labelled values. Any feature that has more than 80% values missing is removed. 

## Exploratory Analysis <a name="eda"></a>

 - Tableau is a widely used software for data analysis, visualization and preparing dashboards. Data exploration for this project was conducted throught Tableau.
 
 - It is typically percieved that houses built in the earlier years had more rooms and were more spacious. This myth is busted as shown by the box-plots below.

  ![Area](images/Year_built_vs_area.PNG)
  
  ![Rooms](images/Year_built_vs_rooms.PNG)
  
- Sale price and building foundation do not seem to be too correlated, increasing lot size does increase the sale price as depicted by bigger circles. 

  ![Foundation](images/foundation_price_area.PNG)

- Did a particular type of roof become old fashioned? Or did a certain style of house come in fashion? As seen from the plot below, Split Foyer and Split Level became more popular around the 1960's. Gable roof type is the most common across different years and house styles.

  ![Roof Style](images/Year_built_vs_house_roof.PNG)

- We are all aware the historically, house prices have been going up. Lets instead try and compare the difference in prices of old and new houses and the condition they are sold in. It is interesting to note that there was a slight dip in the prices for houses built and sold during the economic crisis in 2008.

  ![Roof Style](images/Price_vs_year_condition.PNG)
  
# Data Cleaning and Feature Engineering <a name="cleaning"></a>

Sentiment analysis can be conducted by training a supervised machine learning model on a portion of the review data which can be used to predict a rating that the user might assign just by the analyzing the review text.

## Conclusion <a name="conclusion"></a>

NLP in combination with Neural Networks has made is possible to analyze textual data and train very accurate models to predict sentiments. 

- Predicted Reviews

![Predicted](images/Distribution_of_ratings_predicted.PNG)
