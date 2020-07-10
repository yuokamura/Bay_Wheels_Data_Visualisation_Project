# Bay_Wheels_Data_Visualisation_Project

## Dataset

This project explores a dataset obtained from the bike-sharing system Bay Wheels (formally Ford GoBike).  The area covers the greater San Francisco Bay area includes the detail of individual bike rides made during 2019.
The dataset can be found in the following link:
https://s3.amazonaws.com/baywheels-data/index.html

The website provides a month by month summary of the rides made.  These datasets are firstly concatenated to create one dataframe.  The start_time and end_time were stored as an object, thus changed to the DateTime.  Month, day of the week and hour information are extracted and added as new columns.  
There was one ride which recorded duration time of nearly 250 hours, while all the rest of rides had lasted less than 24 hours.  This data point was simply eliminated.  Also, the duration of rides was recorded in seconds, and this was converted to minutes.

## Files
Initial data gathering, cleaning, and exploration is performed in `exploration.ipynb`.  Key insights from the exploration and analysis are gathered in `slide_deck.ipynb`.

## Summary of Findings
Univariate exploration:  
I have discovered that the duration of rides is right-skewed, but the majority of them are less than 30mins.  Most rides are very short and last 5 to 10 minutes.  The number of rides is affected by mainly by the time of the week (whether it is weekday or weekend), and also the time of day (a bimodal distribution with peaks at 8 and 17).  Also, the majority of users are subscribers (80 per cent to be more precise).  

Bivariate exploration:  
Firstly, I have checked how the duration of the ride is affected by time factors.  Again, I saw the difference between weekend and weekday, and thus decided to update the day of week column (Before it gave one of Monday to Sunday, and after it was either weekday or weekend).  The rides during weekday tend to be shorter than the those of the weekend.  The duration was also affected by the user type.  Subscribers have shorter rides while customers have a longer mean and more broad distribution.  The number of rides was also primarily influenced by the customer type.  Weekday rides are mostly made by subscribers, but the figure drops during the weekend.  Although the hourly figure showed, the trend is similar for both types of users.  The interesting pattern shows up when the hourly number of rides are plotted again, but this time separated by whether it is on the weekday or weekend.  The pattern changed completely for both subscribers and customers.  While the weekday pattern was the same as what has been observed, the weekend pattern shows the one broad peak with peak time around early afternoon.

Multivariate exploration:
I have considered how all three variables, duration, time and user type are connected.  It was clear that the customers have a much longer ride on average than the subscribers.  Subscribers also have fewer fluctuations in duration when compared to that of customers.  There was a significant drop in the duration towards December for customers.  If there was assumed to be a periodical pattern, then the jump between December and January would be quite significant.  It will be interesting for further investigation to see the pattern in different years.  The duration of rides during the late-night for customers is quite high, even considering the large interquartile range.  This can be observed for subscribers as well, but the increase is less significant

## Key Insights for Presentation
For the presentation, I focus on how the duration and number of rides vary depending on weekend and weekday, and also by user type.  I will leave out variation throughout the year.

I will start by introducing the duration distribution, both before and after log transformation.  I will then show the proportion of user type.

Next, I will show the bar plots of a number of rides against weekday/weekend and how it differs with subscriber/customers.
Make the point that how the distribution completely differs on a weekday (bimodal) and weekend(normal).  Also, note that the trend is the same for both subscribers and customers.

Finally, show the plot of average duration of rides for subscribers and customers during weekday v weekend.  Point out that the average duration is consistently shorter for subscribers.  The duration change over the course of the day shows that the late-night rides tend to be longer, especially for the customer.  There is also an increase in duration during the afternoon for customers.
