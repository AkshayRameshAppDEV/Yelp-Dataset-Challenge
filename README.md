# Yelp-Dataset-Challenge

## Goal:-
To analyze how restaurant ratings are affected by review sentimental scores, review length, and number of useful, funny, and cool votes recieved by review.

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

install.packages("gbm") # Boosting Package

install.packages("randomForest") # Random Forest Package

```

## Loading the installed libraries/packages:-

```
library(SparkR)
library("aws.s3")
library(corrplot)
library(tree) # library for decison tree
library(gbm)
library(randomForest)
```

## Getting access to my AWS S3 bucket and storing the bucket object into the variable:-
```
Sys.setenv("AWS_ACCESS_KEY_ID" = "Your Access Key ID",
           "AWS_SECRET_ACCESS_KEY" = "Your Secret Access Key",
           "AWS_DEFAULT_REGION" = "Your Bucket Default Region")
bucketlist() #For seeing what files are there in bucket
get_bucket('yelpdatasetchallengebigdataproject') #getting the bucket containg the Yelp Dataset

#Storing the S3 bucket in object
obj <- get_object("s3://yelpdatasetchallengebigdataproject/yelp_review.csv")
yelpData <- read.csv(text = rawToChar(obj)) #storing csv data from Amazon s3 to a yelp data variable
```

## Data Exploration:-
```
display(yelpData)
```
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/1.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/2.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/3.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/4.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/5.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/6.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/7.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/8.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/9.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/10.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/11.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/12.PNG)

## Linear Regression Analysis:-
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/13.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/14.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/15.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/16.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/17.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/18.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/19.PNG)

## Decision Tree Analysis:-
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/20.PNG)

## Boosting Analysis:-
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/21.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/22.PNG)
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/23.PNG)

## Random Forest Analysis:-
![alt text](https://github.com/AkshayRameshAppDEV/Yelp-Dataset-Challenge/blob/master/Big%20Data%20Pics/24.PNG)

## Conclusion:-
When comparing all the above correlation accuracies of 4 different algorithms, the ranking based on correlation accuracy (from highest accuracy to lowest accuracy) are as follows:-

Boosting > Random Forest > Decision Tree > Linear Regression

Boosting algorithm performed much better than the other three models with an accuracy of
70.15%. Boosting performed better because it is designed to create lot of trees consecutively,
which resulted in improved performance. Moreover, each tree has a better fit on a modified
version of the previous tree when Boosting is used.
