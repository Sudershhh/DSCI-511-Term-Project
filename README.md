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

#### CREATING CRIME DATASET
The core requisite for this dataset depends on the Open Data Philly API. The response gives us data starting from 1st January, 2022 till today's date. 
The API was run at the end of each day to get the latest data. 
The major problem with the response was that it was dirty and raw and was not readable to the user and several columns were unnecessary.
After iterating through the response as a list and cleaning the rows and dropping several columns, a cleaned dataset was obtained and converted to a CSV File.

#### RAW DATASET
![Raw data](https://user-images.githubusercontent.com/59435391/204218311-69204ab5-501e-4850-8dbb-4fdbd6702667.jpeg)


### Sample Cleaned Crime Dataset

![WhatsApp Image 2022-11-27 at 21 38 53](https://user-images.githubusercontent.com/59435391/204214117-b9aa6a8e-cf64-4e53-8017-5f02ab86766a.jpeg)


#### CREATING WEATHER DATASET
The next part of this project is to collect data from the weather api. This API is a 14 day trial edition and gives us access to historical data. Since our dataset consists of over 280,000 rows; we cannot call the api for each date. So we just collect the unique dates the crime occured and store the 24h hourly weather details in a dictionary. After storing the details in a list, we can iterate over the crime dataset and obtain the weather data for that corresponding day and append it to weather dataFrame. After getting the weather dataframe and converting to a CSV file, we can merge the 2 datasets; crime and weather into one large dataset.


#### CREATING STOCK MARKET DATASET
Twelve Data provides us stock market data and the api is flexible. We can provide the start, end dates, currency and exchanges. For our project, we are collecting data from 1st January, 2022. The information we are collecting are the daily Low, High, Open, Close, Volume stock prices.

![Stock Photo](https://user-images.githubusercontent.com/59435391/204216359-dad6c174-8818-4fd0-a8f5-4206eb739439.PNG)




#### CREATING HOLIDAY DATASET
Holiday API provides us the list of holidays throughout the year globally. For our project, we just need the holidays specific to the United States. The response we are getting are Date, Holiday, Public Holiday or not.

![Holiday](https://user-images.githubusercontent.com/59435391/204216867-822c05ab-2908-428c-b99e-2c8d6e54a665.PNG)

#### FINAL MERGING AND MANIPULATION
Once we obtain all the 4 dataframes, namely, Crime, Weather, Stock and Holiday, using pandas library, we can merge all the 4 dataframes using the append method into one big dataset and rename the columns into a readable format.

#### FINAL SAMPLE DATASET
![Final - 1](https://user-images.githubusercontent.com/59435391/204217489-7a50c35e-d8e9-47e4-93da-d3709a58630d.jpeg)



![Final - 1 5](https://user-images.githubusercontent.com/59435391/204219191-1eb095ae-5e1e-48b1-be9a-db94238975e8.PNG)



![Final - 2](https://user-images.githubusercontent.com/59435391/204217503-db6b9f3c-d1c0-4828-a04d-662cd597a1a9.jpeg)

#### Challenges Faced by the Team & API Limitations

- Initially, The dataset we created was quite large with over 2 Million rows of data. It took some time to figure out the necessary columns and delete the unrecognized data. 
- The Weather API we have is a  Pro Plus plan with 14 day trial version that allows us to request 5 Million calls per month. Subscription to the API is quite expensive and we have to signup twice over the course of our project implementation to get it up and running,
- The Stock API provided by Twelve data is free for use however the system is based on API Credits. 1 API call costs 8 API Credits and we are allowed a maximum of 800 credits per day. Also, We can only call the API once in a minute.
- For the Holidays API, we only get the 2021 holiday data and we can make 10000 requests per month. We had to programmatically get the response and change all the years to 2022 to fit in our dataset.


