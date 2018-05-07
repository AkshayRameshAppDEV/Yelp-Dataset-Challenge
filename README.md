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
