# Yelp-Dataset-Challenge

## Goal:-
To analyzed how restaurant ratings are affected by review sentimental scores, review length, and number of useful, funny, and cool votes recieved by review.

## Language used:-
We used Spark R in databricks.

## Installing Required Package:-

```
install.packages("aws.s3")

#Installing sentimentr package
if (!require("pacman")) install.packages("pacman")
pacman::p_load_current_gh("trinker/lexicon", "trinker/sentimentr")

install.packages("corrplot") #installing corrplot package

install.packages("tree") # Decision Tree Package

install.packages("gbm") # Boosting PAckage

install.packages("randomForest") # Random Forest Package

```
