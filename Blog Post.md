# Some Data-Driven Tips to Increase Income as an Airbnb Host
<img src="seattle.jpg"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />
## Introduction

Airbnb has revolutionized the travel industry by allowing people to rent out their homes or apartments to travelers. As a host, setting the right price for your Airbnb is key to attracting guests and maximizing your earnings. In this post, we'll use a Lasso regression model to predict Airbnb prices and identify the most important features that contribute to those prices.

Thus, our main objective is to answer the following questions:
1. Which appartment's features will give the host the opportinity to -easily- to charge more?
2. What are the most desired areas of Seattle, for Airbnb guests?
3. What are some key recommendations for the host?

## Data

We'll be using a dataset from [Kaggle](https://www.kaggle.com/datasets/airbnb/seattle) that contains information about Airbnb listings in Seattle The dataset includes features such as the neighborhood, property type, number of bedrooms, and availability.

## Coding process explanation

- We first import the necessary libraries: `pandas` for working with data frames, `Lasso` from the `sklearn.linear_model` module for the Lasso model, `train_test_split` from the `sklearn.model_selection` module to split the data into training and testing sets, and `mean_squared_error` from the `sklearn.metrics` module to calculate the mean squared error.
- We then unzip the data.
- After exploring the features and their values, we decide that we'll continue the analysis with only the apartments that have been available at least one day in the studied year.
- We begin leaving a subset of columns that at first gaze seem relevant to predict the price.
- Knowing that Lasso models can't handle categorical data, we begin to turn these type of variables to numeric, trying to preserve their fundamental logic.
- We create dummy variables for categorical features using the `get_dummies()` function, for the rest of categoricals.
- We split the data into training and testing sets using the `train_test_split()` function.
- We standardize the data.
- We use a search grid that iterates over Lasso models with alpha parameter between 0.1-10, and keeps the best model, which turns out to be the one with Alpha= 0.7.
- We make predictions on the testing data using the `predict()` method.
- We calculate the mean squared error between the predicted values and the actual values using the `mean_squared_error()` function.
- We print the mean squared error and the coefficients of the Lasso model, which give us an idea of the importance of each feature in predicting Airbnb prices.
- Finally we look for the variables that appear to have coefficients = 0, i.e have no impact in the price prediction, as well as for the coefficients bigger than 0.
- We build a bar plot and then get the list of features, shown here:

## Top 15 most important features:

| **Variable Name**                         | **Coefficient** |
|-------------------------------------------|-----------------|
| bedrooms                                  | 26.431984       |
| room_type_Entire home/apt                 | 16.250019       |
| bathrooms                                 | 12.690958       |
| accommodates                              | 9.698379        |
| neighbourhood_group_cleansed_Downtown     | 9.521042        |
| host_response_time_num                    | -7.369377       |
| property_type_Boat                        | 7.241013        |
| neighbourhood_group_cleansed_Queen Anne   | 6.964313        |
| cleaning_fee                              | 6.708912        |
| guests_included                           | 6.405995        |

## Conclusions

There are 4 identifiable groups among the top 15 features:

**Group 1: Property Features (Variable)**
 - bedrooms, bathrooms, accomodates, guests included, cleaning fee, room type, property type.

**Group 2: Neighbourhood**
 - Downtown, Queen Anne.

**Group 3: Host Features**
 - Host's responde time.

With this in mind, we can answer to our business questions:

**1. Which appartment's features will give the host the opportinity to -easily- to charge more?**

Group 1 helps us answer:
- The amount of bedrooms significantly rises de price, so if the aparment has extra space, turning it into a bedroom might be a good idea.
- This is in line with the amount of people it can accomodate and if it includes guests.

**2. What are the most desired areas of Seattle, for Airbnb guests?**

Group 2 helps us answer:
- Downtown and Queen Anne are both great locations!

**3. What are some key recommendations for the host?**

Group 3 helps us answer:
- The amount of time the host takes to answer is inversely related to the price, so if a host wants to charge more, he should be fast replying to het guests.
