# DSCI 511-Term Project

## Team Members
- Sri Sudersan Thopey Ganesh
- Risabh Sharma
- Jeromey Abraham
- Ridhan Srikumar

## Overview

Since crimes are happening frequently on a random basis, we are curious to find out if there is any correlation with crimes and other factors such as Weather, Holiday events, Poverty/Low income neighborhoods, Unemployment or stock prices falling which leads to inflation and prices shooting up which could probably make the perpetrators commit those crimes.

We expect to gather information on the localities were most vulnerable to crimes and what sorts of crimes happens to be common in the given areas. Other predictions and analytics like, The timezones during which the particular area would be hard to access or would be prone to crimes can be drawn from the given data.

With the timestamps in the data set, we can also predict the time of the years, seasons and holidays on the days when maximum crimes take place. Also by including Sensex and other economical data, we can trace the effect of economy on the crime rate (theft, burglary etc). After which, we would like to expand our search to other major cities and compare the differences. We believe this dataset would enable us to connect the dots and form a logical analysis.

## API used
- Open Data Philly
- Weather API 
- Twelve Data API - Stock Market
- Holiday API

## Instructions to run the program

The core requisite for this dataset depends on the Open Data Philly API. The response gives us data starting from 1st January, 2022 till today's date. 
The API was run for several times during the start of each week to get the latest data. 
The major problem with the response was that it was dirty and raw and was not readable to the user and several columns were unnecessary.
After iterating through the response as a list and cleaning the rows and dropping several columns, a cleaned dataset was obtained.





