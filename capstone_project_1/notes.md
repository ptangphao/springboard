=Notes
1/17/18

For calculating distance based on latitude and longitude, consider using geopy.distance

https://stackoverflow.com/questions/19412462/getting-distance-between-two-points-based-on-latitude-longitude


Potential data
https://github.com/saltzberg/sf_real_estate_data

Very limited amount of data

2 versions of the model
1. with just the zillow data set
2. add in additional insights from the yelp dataset (geographical insights) 

some machine learning algorithms will give you feature importance as a byproduct. 


Additional
- categorize as zones
- calculate average of the zone

Data granularity

Zipcodes or cities based on domain specific knowledge 

Feature engineering - "engineered features" from yelp

Start with ~ 10

Stick to 2017 data.

Split dataset into 3 parts
1. train 
2. validation
3. test

When doing engineered features - do literature survey. What other properties and business can positively/negatively impact real estate price. Put citations.

Start with zillow raw dataset, based on actual facts, then do a data merge from yelp and engineer. 

Fact Data + Engineered data based on human expertise in the real estate industry

After collect all the features, do an incremental model comparison. 

Finally, do a final feature selection. 


1. Start raw zillow dataset, build a model
2. Add engineered data based on real estate knowledge
3. Incremental model comparison
4. Final feature selection 

Action steps:
If you're comfortable with the zillow dataset,

Try to consolidate and combine the dataset.

Put them into a dataframe.

1. combine data into a single frame
2. engineer features

Homework:
1. figure out engineered features (citations)
2. add to dataframe based on engineered features.


1/20/18
Engineered Features
1. Proximity to medical care
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Methodology: 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Make a single API call to gather all medical centers within the areas specified by the dataset. 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Divide medical centers into two lists, large medical centers(hospitals) and others (clinics, etc)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Define a function to take in a set of latitude and longitude coordinates (property), return an id or name of the closest large center. 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. Repeat using the list for the 'other' medical centers
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; v. Populate the data frame using the functions
2. Nearby grocery store
3. Nearby police station
4. Proximity to a fire station
5. Airport proximity
6. School proximity

```
Source: http://www.foxbusiness.com/features/2013/10/22/why-location-matters-in-real-estate.html
```
7. Starbucks
8. Whole Foods
9. Religious Buildings
10. Art museum, etc (Culture)
```
Source: https://www.moneytalksnews.com/20-clues-youre-buying-home-the-right-neighborhood/
```
10. Proximity to park/recreation center
11. Proximity to university 

```
Source: https://list.juwai.com/news/2015/10/9-things-chinese-look-at-when-property-hunting
```

2016 entries: 2,985,217 entries with 58 columns
2017 entries: 2,985,217 entries 

Consideration: only 25k API calls per day
Import using python_http_client
do I store the JSON?

1/25
Take the latest data
If later on, we want to improve the machine learning algorithm, we'll start looking back

Distinct zip code
Consider school district

if data size is small, save as a variable, and write it to a flat file

Todo: engineer features


