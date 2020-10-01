# Ford GoBike System Data Exploration for Udacity Data Analyst Nanodegree Program
## by Elaine Lau


## Dataset

The Ford GoBike dataset contains 2,506,983 entries of bike trips in the San Francisco Bay area for 2019. It has 13 different columns of variables including trip duration, start time and date, end time and date, start station information, end station information, bike ID, and user type, whether Subscriber (Member) or Customer (Casual).  I combined monthly data from this website to get a full year for 2019: https://s3.amazonaws.com/baywheels-data/index.html

I created new columns for time of day (hour), day of the week (weekday), and month of year (month) from the start time and date data for easier analysis. I removed one outlier that had an unusually long duration. I also converted the duration from seconds to minutes and added the data as a new column, duration_mins, to the dataframe for easier interpretation.

## Summary of Findings

The distribution of bike trips taken each hour of the day appears roughly bimodal, with the number of trips peaking around 8am and around 5pm (17hr), which coincides with the start and end of a workday.  The highest number of bike trips occurs during the work week with significantly less on the weekend. Tuesdays and Thursdays show slightly higher numbers than the other work days.The largest number of trips occured in March, April, July, and October of 2019.  The number of bike trips by subscribers, in other words people who have become members, greatly outnumber those of customers, who are just casual users. 

The plot of number of trips by duration shows a right skewed distribution with greater number bike trips on the lower end. 
The distribution shows the higher concentration of trips were less than 30 minutes but with a long tail into the higher numbers.  I needed to perform a log transformation to see the values at the higher end better.  The average duration is 13 minutes.  

The plot of number of trips by hour shows the same pattern of peaking at 8am and 5pm for both subscribers and customers. The plot by day of the week shows that subscribers use the bikes more during the work week and less on the weekend. The customers' usage is fairly consistently the same across the days. The plot by month shows the subscriber's usage peaks in March, April, July, and October. The customer's usage shows a slow increase from July to peaking in December with a slight dip in November.

The average duration seems slightly higher for customers than for subscribers. When looking by time of day, customers have higher average duration than subscribers. peaking around the middle of the day from 10am to 4pm. When looking by day of the week, customers have a slightly higher average duration subscribers, peaking on the weekend.    The average duration for subscribers does not vary by day of the week.  When looking by month, the customers still have a higher average duration than subscribers, being highest in the months between March and July. The average duration for subscribers does not seem to vary by month.

The number of trips for subscribers was the most during the work week and at the beginning of the work day at 8am and the end of the work day at 5pm, indicating they used the bikes to get to work and back. The average duration of usage for casual customers was greater in every time frame than for subscribers. 

Surprisingly, the most trips for casual customers occurred in month of December, perhaps they used them for Christmas shopping and visiting friends more. Also interestingly, the most trips for subscribers occurred in month of March.

## Key Insights for Presentation

For the presentation, I used histogram and bar charts to display the number of trips taken in hourly, by weekday, by month, and by user type in 2019.  I displayed the distribution of duration using a log transform on duration because the values spread over a wide range.  

I used bar charts and violin plots to display if the user type affected the number of trips taken or the average duration.

Lastly, I used box plots and violin plots to see if average duration was affected by user type in different time frames.
After getting feedback, I changed the plots to consistently display customers in blue and subscribers in orange.  It was also recommended that I add additional padding between subplots in the graph, Count of Trips by Hour, Weekday, and Month Grouped by User Type.

## Files
>Exploration of the dataset can be seen in exploration.ipynb or exploration.html.
Explanation of findings can be seen in explanatory.ipynb or explanatory.ipynb.
The presentation is in explanatory.slides.html.

## Resources

I used the material from Udacity Data Analysis Nanodegree program and the following websites to aid in some of the coding:

https://stackoverflow.com/questions/40973687/create-new-dataframe-in-pandas-with-dynamic-names-also-add-new-column
https://stackoverflow.com/questions/3294889/iterating-over-dictionaries-using-for-loops
https://stackoverflow.com/questions/53926323/appending-multiple-dataframes-in-pandas-with-for-loops
https://stackoverflow.com/questions/28009370/get-weekday-day-of-week-for-datetime-column-of-dataframe
https://stackoverflow.com/questions/25129144/pandas-return-hour-from-datetime-column-directly
https://stackoverflow.com/questions/51603690/extract-day-and-month-from-a-datetime-object
https://matplotlib.org/3.1.1/gallery/subplots_axes_and_figures/figure_title.html
https://kite.com/python/answers/how-to-set-the-spacing-between-subplots-in-matplotlib-in-python

