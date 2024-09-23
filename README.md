# BoomBikes - Regression model for bike rental service
Build a model which takes in the historical data, a set of variables from which predictions can be made.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

## General Information
### Brief
Model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.

### Some Background
A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

### Problem Statement
They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

Which variables are significant in predicting the demand for shared bikes.
How well those variables describe the bike demands

### What this project is trying to solve
Build a model to help BookBikes understand the market such that the historical data can be used to predict the business in the coming future.

### Dataset
Categorical¶

    instant - row instance
    dteday - date the transaction happened
    season - season of the year
    yr - year (0 for 2018 and 1 for 2019)
    mnth - month of the year
    holiday - boolean, holiday or not
    weekday - day of the week
    workingday - boolean, workingday or not
    weathersit - weather conditions

Numreical

    temp - temperature
    atemp - assumed temperature - how the users felt
    hum - humidity
    windspeed - windspeed
    casual - business from 'on the spot' type of rental
    registered - business from 'existing user' type of rental
    cnt - the business parameter. To be predicted

## Conclusions
- The relationship between `temp` and `cnt` seems to positively correlate. So, a part of the variance in `cnt` is explained by `temp`
- More rentals happening on holidays
- More rentals on fall and summer with slightly lesser rentals on winter and spring
- More rentals were taken in the year 2019 compared to 2018
- More rentals were taken from month April to Oct with peaks in Sep and Oct
- More `casual` rentals happen on the weekends
- More rentals happening on Clear day, followed by Cloudy and Light Snow days and none on days of Heavy Rain
- More rentals were taken from month April to Oct with peaks in Sep and Oct
- There is a positive correlation between the y-variable cnt and temp, atemp, season, dteday, yr and mnth
    cnt negatively correlated to windspeed and hum
- Variables apart from correlating with cnt, they also correlate with themselves, like
        yr, mnth, season and dteday
        temp, atemp, hum
        hum and weathersit
        season and temp
- The $Adjusted R^2$ of test and the predicted datasets are 83% and 80.8% respecrively. The difference (2.2%) is minimal and hence the estimated model is satisfactorily close to the actual.
### Final Equation
    cnt = 0.2762 
    + 0.2265 * yr 
    - 0.0897 * holiday 
    + 0.5666 * temp 
    - 0.2864 * hum 
    - 0.2014 * windspeed 
    - 0.1917 * weather_light_rain 
    + 0.0494 * mnth_Aug 
    + 0.1187 * mnth_Sep 
    + 0.1002 * season_summer 
    + 0.1521 * season_winter

## Technologies Used
Package                           Version
--------------------------------- ---------------------
- pandas                            2.2.2
- numpy                             1.26.4
- matplotlib                        3.8.4
- matplotlib-inline                 0.1.6
- scikit-learn                      1.5.1
- scipy                             1.13.1
- seaborn                           0.13.2
- statsmodels                       0.14.2
- jupyter                           1.1.1
- jupyter-console                   6.6.3
- jupyter_core                      5.7.2
- jupyterlab                        4.2.5


## Acknowledgements
- BoomBike dataset and problem statements provided by Upgrad


## Contact
Created by [@prscsy] - feel free to contact me!