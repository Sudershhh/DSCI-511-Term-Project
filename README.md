# DSCI 511-Term Project
# Crime, Environmental Factors and demographics

## Team Members
- Sri Sudersan Thopey Ganesh
- Rishabh Sharma
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
- Twitter API

## Instructions to run the program

### CREATING CRIME DATASET
The core requisite for this dataset depends on the Open Data Philly API. The response gives us data starting from 1st January, 2022 till today's date. 
The API was run at the end of each day to get the latest data. 
The major problem with the response was that it was dirty and raw and was not readable to the user and several columns were unnecessary.
After iterating through the response as a list and cleaning the rows and dropping several columns, a cleaned dataset was obtained and converted to a CSV File.

### RAW DATASET
![Raw data](https://user-images.githubusercontent.com/59435391/204218311-69204ab5-501e-4850-8dbb-4fdbd6702667.jpeg)


## Sample Cleaned Crime Dataset

![WhatsApp Image 2022-11-27 at 21 38 53](https://user-images.githubusercontent.com/59435391/204214117-b9aa6a8e-cf64-4e53-8017-5f02ab86766a.jpeg)


### CREATING WEATHER DATASET
The next part of this project is to collect data from the weather api. This API is a 14 day trial edition and gives us access to historical data. Since our dataset consists of over 280,000 rows; we cannot call the api for each date. So we just collect the unique dates the crime occured and store the 24h hourly weather details in a dictionary. After storing the details in a list, we can iterate over the crime dataset and obtain the weather data for that corresponding day and append it to weather dataFrame. After getting the weather dataframe and converting to a CSV file, we can merge the 2 datasets; crime and weather into one large dataset.


### CREATING STOCK MARKET DATASET
Twelve Data provides us stock market data and the api is flexible. We can provide the start, end dates, currency and exchanges. For our project, we are collecting data from 1st January, 2022. The information we are collecting are the daily Low, High, Open, Close, Volume stock prices.

![Stock Photo](https://user-images.githubusercontent.com/59435391/204216359-dad6c174-8818-4fd0-a8f5-4206eb739439.PNG)




### CREATING HOLIDAY DATASET
Holiday API provides us the list of holidays throughout the year globally. For our project, we just need the holidays specific to the United States. The response we are getting are Date, Holiday, Public Holiday or not.

![Holiday](https://user-images.githubusercontent.com/59435391/204216867-822c05ab-2908-428c-b99e-2c8d6e54a665.PNG)

### Twitter API Data Collection and True Crime Daily Website - Scraping
1. Twitter API: using the twitter API elevated access, we generated tokens and used them to extract data from the twitter handle of Philadelphia Police, Which gives live reporting of criminal activities in the philadelphia region. The dataset has 5 attributes namely - tweets, created_at, the user who posted it, likes, retweets and the link to the tweet. This can be used in various ways by the philadelphia police, philadelphia public safety, drexel and Upenn Police departments and others as well. The twitter text data can be used to understand the nature of crimes in the philadelphia region.


![Twitter API](https://user-images.githubusercontent.com/59435391/204380560-dc09f9dd-c796-4716-ad34-ccc3749aad24.jpeg)

2. True Crime daily scraping: Using beautifulSoup and requests we web scrapped the data from the true crime daily website, this is essentialy a news blog for the USA, On the website we scarpped data for the crimes which have happened in the philadelphia region. From the initial page, we were able to extract all the links to the blog post about individual crimes and their detailed text. This dataset has 5 columns - links, titles, text, date and time. This can be used in a similar way as the twitter API.


![True Crime](https://user-images.githubusercontent.com/59435391/204380575-80a3492b-10ce-43f1-8420-f2010bc06b01.jpeg)


These datasets can not be merged with the crime and weather dataset as the crimes reported in the crime and weather dataset can vary from the twitter and true crime daily dataset.





## FINAL MERGING AND MANIPULATION
Once we obtain all the 4 dataframes, namely, Crime, Weather, Stock and Holiday, using pandas library, we can merge all the 4 dataframes using the append method into one big dataset and rename the columns into a readable format.

## FINAL SAMPLE DATASET
![Final - 1](https://user-images.githubusercontent.com/59435391/204217489-7a50c35e-d8e9-47e4-93da-d3709a58630d.jpeg)



![Final - 1 5](https://user-images.githubusercontent.com/59435391/204219191-1eb095ae-5e1e-48b1-be9a-db94238975e8.PNG)



![Final - 2](https://user-images.githubusercontent.com/59435391/204217503-db6b9f3c-d1c0-4828-a04d-662cd597a1a9.jpeg)

### Challenges Faced by the Team & API Limitations

- Initially, The dataset we created was quite large with over 2 Million rows of data. It took some time to figure out the necessary columns and delete the unrecognized data. 
- The Weather API we have is a Pro Plus plan with 14 day trial version that allows us to request 5 Million calls per month. Subscription to the API is quite expensive and we have to signup twice over the course of our project implementation to get it up and running,
- The Stock API provided by Twelve data is free for use however the system is based on API Credits. 1 API call costs 8 API Credits and we are allowed a maximum of 800 credits per day. Also, We can only call the API once in a minute.
- For the Holidays API, we only get the 2021 holiday data and we can make 10000 requests per month. We had to programmatically get the response and change all the years to 2022 to fit in our dataset.


### Individual Contributions
- Sri Sudersan extracted information pertaining to weather from weather API. The responses obtained were substantial and huge. Out of all the parameters obtained, Temperature, Avg Temperature, Max Temperature, Avg Humidity, Precipitation, Condition, Sunrise, Sunset, Moonrise, Moonset, Moonphase were extracted.
- Jeromey collected data for the crime incidents everyday for 2 weeks and converted all to CSV files and merged it together and dropped the redundant entries and cleaning the dataset by discarding certain columns like hour, cartid, objectid, point_x, point_y
- Ridhan collected data from the Twelve data api for stock market and Holiday information from the holiday API. Ridhan created 2 dataframes for stock market and holiday to store the unique information. 
- Rishabh scraped data from True Crime Daily website and Twitter API. Using the twitter and true crime daily we collected data with varied text data along with the date and time of the crime. This dataset can be used individually for the future use. 


### Expansion of this project
- The way we would like to expand this project is by gathering data from other crime-ridden cities.
- We could use this dataset available to other data analysts who are interested in Crime and how it is affected by the environment.
- By doing this, we will be able to get insights from the dataset and also ways in which we could improve the project.
