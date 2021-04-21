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

 - From the plot below, it can be seen that majority of the ratings are 4 or 5. Which contradicts the initial itution that people only go to review something when they find it bad or not up to the mark. This might be a more special case since the data is for musical instruments and usually enthusiasts get something only when they know what they are getting.

  ![Overall Ratings](images/Distribution_of_ratings.png)

- Most reviewed genre was Pop followed by Alternative Rock. 

  ![Genre Ratings](images/Distribution_of_ratings_category.png)

- The following are the most reviewed products and the most active users.

  ![Most Reviewed](images/Top_reviewed.png)
  
  ![Most Active](images/Top_reviewers.png)
  
 - Sentiment distribution of most reviewed products.
 
  ![Most Reviewed Sentiment](images/Top_reviewed_sentiments.png)
 
- Wordcloud for negative sentiment reviews:
  ![Negative Sentiment](images/Negative_wordcloud.png)
  
# Sentiment Analysis and Review Prediction <a name="sentiment"></a>

Sentiment analysis can be conducted by training a supervised machine learning model on a portion of the review data which can be used to predict a rating that the user might assign just by the analyzing the review text.

## Multi-class classifcation <a name="classification"></a>

In order to do this, a Logistic Regression model and a Multi-class Naive Bayes model is trained on the vectorized review data. The data is vectorized using tf-Idf which counts how frequently a word appears in a review and then penalizes it based on its occurance in the entire set of reviews.

- Logistic Regression model gives a train accuracy of 70%.

  ![Regression](images/logistic_regression_matrix.png)
  
- Naive Bayes model gives a train accuracy of 73%.

  ![Bayes](images/naive_bayes.PNG)

## Neural Networks - LSTM <a name="classification"></a>

In order to improve on this accuracy a few step are taken:
1. Glove word embeddings are used to vectorize the data. These embeddings are pretrained on a number of features and help classify different words together.
2. A regression type model is used instead of classification. 
3. Neural networks framework in Keras is used with LSTM. Long Short-Term Memory (LSTM) network is a type of RNN capable of learning order dependence in sequence prediction problems. 
4. In addition to the review text, price and genre are also included as features in the NN. Genre is one-hot-encoded and price is standardized for this.

- Proposed LSTM model
  ![LSTM](images/lstm.PNG)

Hyper-parameter tuning is conduced for the model and then the model is fitted on the train dataset. 

An MSE of 0.42 is obtained for the train set and 0.48 for the test set. 

## Conclusion <a name="conclusion"></a>

NLP in combination with Neural Networks has made is possible to analyze textual data and train very accurate models to predict sentiments. 

- Predicted Reviews

![Predicted](images/Distribution_of_ratings_predicted.PNG)
