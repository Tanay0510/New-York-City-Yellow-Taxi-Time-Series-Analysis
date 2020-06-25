# New-York-City-Yellow-Taxi-Time-Series-Analysis

In this project, I looked at NYC Taxi data to come up with a prediction for the year 2016. I started with doing some exploratory data analysis of the data to come up with some hidden insights in gigabytes of data. I plotted time series graph of daily taxi data from 2009-2015 and then also compared the pick-up and drop off location in New York City.


Then, I did time series forecasting by using appropriate model for the dataset. The only limitation of this was that the resources available to me was not enough to go into detailed analysis of the data. Given an opportunity, I would like to divulge deeper into this dataset to come up with even more finding such as which location/ area will have how many pick-ups on a given day


The New York City Taxi & Limousine Commission has taxi record available from 2009 to 2019. The taxi data is further divided into Yellow Taxi, Green Taxi and For Hire Vehicle. For this project, I decided to use the data of Yellow Taxi from 2009 to 2015. The entire dataset, comprising of just Yellow Taxi Data, from 2009 to 2015 have 1.1 billion rows. The dataset for further divided into months. I downloaded the monthly data from 2009 to 2015. The total size of the dataset from 2009-2015 was 173GB.

Each of the data file has the following columns

*Vendor-ID*

*Trip Pickup Date-Time*

*Trip Dropoff Date-Time*

*Passenger Count*

*Trip Distance*

*Start Longitude*

*Start Latitude*

*End Longitude*

*End Latitude*

*Payment Type*

*Total Amount (Fare Amount + Extra + MTA Tax + Toll Amount + Tip Amount)*

Since our end goal was to do time series analysis of data and predict how many yellow taxi trips would occur in the year 2016, I decided to subset the data by Trip Pickup Date-Time. I got a count of trip completed based on Trip Pickup Date-Time for each day from 2009 to 2015 and saved it in a .csv file. This helped me in converting 173GB of data to just 41KB, as I just used the columns that I needed.

For plotting the graph of Trip Pick Up and Trip Drop Off location, I converted all the .csv file with its original columns (84 files/173gb) to. hdf5 file format and then merged all these. hdf5 files into one. This helped me plot the Yellow Taxi Drop Off and Pick up location on map.

Then, I wanted to cluster the areas with most yellow taxi trip pickup. To do this, I used H3 library, which is Uber’s Hexagonal Hierarchical Spatial Index. By using it, I could easily cluster geospatial observations, and display them on a map. I did the clustering using just one month of data as doing it on the whole dataset was computationally impossible taking into consideration the fact that Pandas library is not useful when dealing with big data.


## Time Series Techniques ##

*Auto Regressive Integrated Moving Average (ARIMA)*

*Trigonometric seasonality, Box-Cox transformation, ARMA errors, Trend and Seasonal components (TBATS)*

## Forecast ##

*Came up with Forecast for next year based on previous 7 years of daily data*
