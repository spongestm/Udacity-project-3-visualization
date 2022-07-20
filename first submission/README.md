# (FEBRUARY 2019 FORDGOBIKE DATA EXPLORATION)
## by (EKPOT GODSWILL TOM)


## 201902-fordgobike-tripdatacopy.xlsx

 Provide basic information about your dataset in this section. If you selected your own dataset, make sure you note the source of your data and summarize any data wrangling steps that you performed before you started your exploration.
### This data set includes information about individual rides made in a bike-sharing system covering the greater San Francisco
### Bay area
### This project explores this dataset containing 183412 rows and 16 columns. The columns include bike id,start station longitude, start station latitude, start station name start station id,user type, member gender, duration in seconds,start time, end time, end station id, end station name, end station longitude, end station latitude, member birth year, and bike share status.
## Wrangling
I downloaded the dataset from the udacity dataset options sheet. After downloading, i read it into my ipynb file using the pd.read_csv option and used the df.info() and .head()  to check for tidiness or quality issues in the dataset

# Quality issues
1. Presence of null values
2. The start_time and end_time are both object datatypes and are supposed to be datetime variables

# Tidiness issues
1. The start_time and end_time are both object datatypes and are supposed to be datetime variables
2. There are columns for longitude and latitude. These values on their own are not variables as they cant be measured against each other or a standard and cannot be calculated on their own. Therefore i plan to extract the longitude and latitude columns of the start and end points to another dataset to calculate the distance between the pointsfrom them 
3. Start and end time columns contain too many variable including year,month, date, hour etc. therefore we will seperate options in this column and analyze seperately Also, we will use member birth year and year from the time stamp to calculate age of the rider.
4. Duration in seconds will be changed to minutes and probably hours


## cleaning
To perform the cleaning,
1. i dropped all the null rows from the dataframe
2. I dropped the columns with irrelevant values or values that cant be measured or calculated including start and end longitude and latitude
3. I changed the start and end columns into datetime data type.
4 I extracted the time from the start time column and extracted the year 
5. i subtracted the member birth year from present year to extract the member age
6. I attempted getting distance by using the start and end latitude and longitude and the haversine function, however, my device doesnt hhave enough memory to accomodate such calculation.
7. i divided the duration_secs column by 60 to get the ride duration in minutes.
8. I extracted the hour start hour of all the rides from the start time column.


## Summary of Findings

 Summarize all of your findings from your exploration here, whether you plan on bringing them into your explanatory presentation or not.
 
1. I observed from my exploratory analysis that people within the ages of 20 and 40 ride bikes the most.

2. From the data, we also found out that  there are more male riders than female riders.

3. We were also able to establish that most of the rides last 30 mins to 1 hour

4. I also noticed that there is a low bike share rate

5. I was also able to deduce that the high traffic periods for bikes are from 7am to 10 am and 4pm to 7pm

6.  There is a significantly higher amount of subscribers than customers.

7.  We also noticed that 11th station at Natoma street and 11th street at bryant street are the most used stations.

8.  We observed most people below 60 riide bikes between 7am and 8pm. Also that this is the time with the highest riding periods.

9.  We were able to observe that despite the fact that we have more male riders, the females ride for longer periods than men.

10. It was also obseved that customers ride longer than actual subscribers.

11. we observed some outliers in the age column towards the end of the bivariate data exploration.

12. The "other" gender has the least amount of  values some have been observed to have extreme durations so could be outliers

13. We also observed that subscribers use the the bike share more than customers.




## Key Insights for Presentation

From our dataset, it is interesting to note that customers do not share their bikes for trips and this is one of the reason why the sharing rate is so low. We need to find out why this is so.
I also think its important to observe that women ride for longer periods than men.