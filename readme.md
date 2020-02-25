# GoFordBike Data Exploration

## Dataset

The dataset contains 26 separate files downloaded from GoFordBike website, each file contains all rides data in a specific month from July 2017 to January 2020, the rides data contains of ride duration, starting and ending locations and timing and the user type. After combining all the 26 files, the combined data counted more than 5 millions rows. 

The dataset can be found online [here](https://www.lyft.com/bikes/bay-wheels/system-data).


## Summary of Findings

In the exploration, I found that the dataset consist of more than 5 millions rows over 26 months from July 2017 to January 2020, It was challenging how to combine all these data in one dataframe to conduct my analysis.

I found that the duration distribution is normally distributed on log scale with small skew to the right, the duration ranges from 60 seconds to 86k seconds with two unlogical outliers with more than 10 days that I removed for clean analysis.

There was 453 stations in this dataset that were used as pick up and drop off points, a count plot was produced for this huge number of stations.

80.5% of users were Subscribers, while Customers were just 19.5%

Another challenging task was to analyze the distance for each ride using the pick up and drop off coordinates, I used a geopy function to find the distances and then proceeded my analysis.

The distance distribution skewed to the right, but there is large frequency at zero distance, which relates to uncomplete rides, or a ride that started and finished at same point. 

The relation between duration and distance looks postive and strong on the graph except for points of zero distance that have large distance values, and this supports our assumption, that the rides that have zero distance maybe due to the fact that the ride started at a point and moved for long distance and then returned again to the same point, these points affected the corr coefficient r and made it lower than expected.



## Key Insights for Presentation

For the presentation, I show the most interesting insights in my study as follow:

1. Rides durations in the dataset take on a very large range of values, from 60 seconds as minimum which is propably due to standard values for shortest rides in the system, and ranges to about 86k seconds at the highest. Plotted on a logarithmic scale, the distribution of durations is normally distributed with small right skew.

2. There are 453 stations that has bikes by GoFordBike in San Francisco.

3. The average number of rides per month is 187k rides, and the year 2019 is showing great results in against 2018 in terms of number of rides per month. Also, Decemeber is always associated with lower number of rides per month, which can show that rides decrease in holidays, which also can lead to a conclusion that people use these rides during working times.