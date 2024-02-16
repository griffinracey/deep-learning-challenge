# deep-learning-challenge
Challenge Assignment 21 - Deep Learning

# Overview
We are analyzing data for a nonprofit to determine if an applicant for funding is going to have a good chance of a success or not with their ventures. 

For the pre-processing, I used `pandas` docs to assist with the data cleaning. I also used activites from Module 20 to help with converting the categorical data to numeric (dummies).

# Preprocessing

Our target variable was the `IS_SUCCESFUL` variable since that determines if the funding was successful.

Our feature variables include:

* APPLICATION_TYPE—Alphabet Soup application type
* AFFILIATION—Affiliated sector of industry
* CLASSIFICATION—Government organization classification
* USE_CASE—Use case for funding
* ORGANIZATION—Organization type
* STATUS—Active status
* INCOME_AMT—Income classification
* SPECIAL_CONSIDERATIONS—Special considerations for application
* ASK_AMT—Funding amount requested
* IS_SUCCESSFUL—Was the money used effectively

* EIN and NAME—Identification columns are removed as they are not needed for either target nor feature columns. 

# Evaulating and Training Model

Our intial model had an accuracy of ~`72.8%`. 

Modification 1: I added a third hidden layer to the model and it only brought the accuracy up to about `73.0%`.

Modification 2: I changed the output activation to `sigmoid` and dropped `ORGANIZATION`. This lowered my accuray to `72.6%`.

# Summary

Final modifications for optimization: I added back `ORGANIZATION` but kept `sigmoid`. The first hidden layer's activation was changed to `relu` and nodes chaneged to `100`. The cutoffs for `APPLICATION_TYPE` was dropped to `50` and `CLASSIFICATION` to `25`. These changes resulted in a `73.0` accuracy again. 

I would maybe try used a `Decision tree` classification model instead - I would try this due to the amount of categorical variables. This would allow us to set "paths" based on each categorical variable. 