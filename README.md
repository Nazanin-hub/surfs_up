# surfs_up
SQLite, SQLAlchemy, and Flask

## Project Overview

W.Avy who is a famous investor advised me on investing in the surf and ice cream shop business. He asked me to prepare some information about temperature trends specifically, temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

## Resources

Data Sources: hawaii.sqlite

Software: Python 3.8.3, Anaconda Navigator 1.9.6, Jupyter Notebook 6.0.3

## Results

The below tables show summary statistics for June and December. The following results can be derived from both tables:

 - The average temperature in June is higher than in December. 
 - The standard deviation in December is higher than June. it means that the temperatures in December are more spread out from the mean.
 - 50% of temperatures in December are higher than 71 degrees, while they are higher than 75 degrees in June.
 - Temperatures are between 64 and 85 degrees in June, while the minimum and maximum temperatures in December are 56 and 83 degrees.

![](https://github.com/Nazanin-hub/surfs_up/blob/main/June_Temp.png)

![](https://github.com/Nazanin-hub/surfs_up/blob/main/Dec_Temp.png)

## Summary

Based on the above results, the temperature in December is slightly lower than in June. So, the surf and ice cream shop business in Oahu could be sustainable year-round. More queries can help us to gather more weather data for June and December to get the most accurate results.

The below queries show the amount of precipitation for June and December:

     results_June = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==6).all()
     df = pd.DataFrame(precipitation_June, columns=['date','June Prcp'])
     df.describe()
     
     results_December = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==12).all()
     df = pd.DataFrame(precipitation_December, columns=['date','December Prcp'])
     df.describe()
     
The below tables give us a summary of different statistics for the amount of precipitation in June and December.

![](https://github.com/Nazanin-hub/surfs_up/blob/main/June_Prcp.png)

![](https://github.com/Nazanin-hub/surfs_up/blob/main/Dec_Prcp.png)
