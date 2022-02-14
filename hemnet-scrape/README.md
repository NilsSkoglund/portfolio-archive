# Sold-apartments-Stockholm-2013-2020

# DIY
1) Run code in sthlm/"1. Sthlm - Get id_sold_sthlm.ipynb" (runtime ~10 minutes)
2) Run code in sthlm/"2. Sthlm - Get sthlm_raw.ipynb" (runtime ~ 30-60 minutes)

You should now have raw data from 50k+ apartments sold in Stockholm with less than 1% NaN-values. 

# Summary
In this project I'm scraping information from 50k+ sold apartments in Stockholm from jan-2013 to sep-2020. After scraping I´ve performed a decent amount of data cleaning before the data-set was ready for analysis. My analysis was exploratory and I was mainly focused on looking at the price development for apartments in Stockholm kommun. The year over year return was ~4.5% and the annualized standard deviation was ~2% for aparments sold in Stockholm between jan-2013 and sep-2020.

# Description
## Scraping
Hemnet (www.Hemnet.se) is Sweden´s most widely used marketplace for finding houses/apartments to buy or sell. 
In addition to this Hemnet stores information about sold objects and this information is available on their site. 
My goal was to scrape basic information about as many apartments as possible that has been sold in Stockholm and then perform an exploraty analysis on the data. 

Hemnet had a total of 117k+ sold apartments in Stockholm. 
I was able to scrape information from 58k+ sold apartments. 
Hemnet only shows information about the 2500 most recent sold objects for a category. 
Therefore It's not possible to scrape the desired information directly from the "Stockholm" category. 

My approach was to scrape information from individual streets in Stockholm. I managed to find a range of numerical identifiers for streets in Stockholm which was the only variable in the URL, thus allowing me to loop thorugh the range and efficiently extract the desired information. No street had more than 2500 sold objects so it's very likely that you can find more numerical identifiers to be able to extract info from more apartments in Stockholm than the 58k+ sold apartments my range covered. However my data-set is quite big and has a good coverage of the total amount (58/117 ~ 49.6%).

My date-range was from jan-2013 to sep-2020. In this data-set, 2013 is the year with the least amount of sold apartments (4k+ in total and no month with less than 100). I did find objects sold in 2011 and 2012 but not enough to be of interest in an analysis of price development. 

I'm extracting 13 pieces of information from each sold object and I had good coverage with less than 1% NaNs. 


## Data-cleaning
Some values are mistyped by Hemnet and if they are not numerical outliers they are very difficult to identify. However I believe the most important part of the data-cleaning in this data-set is to identify the numerical outliers so this was my main focus. If you don´t pick up on the mistyped information the data can get heavily skewed. I.e. there was a price increase of over 1 billion percent which obviously has a huge effect on an analysis of the average price increase. 

## Columns/Values of special interest
The values from each sold apartment I was mainly interested in was the  "sqm", "final price" and "date sold". This information allows for a really solid estimate of the average price development for apartments in Stockholm. 

In addition to the three above mentioned values I was also extra interested in the values "no. of rooms", "street name" and "area name". This information in conjunction with "sqm", "final price" and "date sold" allows for an analysis of the average price development in Stockholm for different groups. 

## Omx30 
I´m comparing the price development of apartments in Stockholm with the price development of omx30 for the years 2013-2020. 

# Project status
Closed to finished project. Need to tidy up code and add comments in a few places. 

Possible to ongoingly extract information and create your own data-base of sold objects in Stockholm (or other areas of interest with minor adjustments to the code) 

# Possible future updates
- Automate the data-cleaning were possible. I.e. a method such as removing absolute Z-values > 3 
- Find a good method to automate analysis of average price changes in different areas
- Find a good method to automate analysis of average price changes on different streets
- Explore the possibility of creating a more efficient index for average price change for apartments in Stockholm. I.e. a basket of streets with high turnover. 

# Map & file structure
`Maps`
- graphs: Visualizations & analysis 
- omx30: Creating usable csv from data exported from Nasdaq
- sthlm: (THIS MAP CONTAINS THE MAJORITY OF THE PROJECT). Scraping information from Hemnet, data-cleaning and adding columns. Finished product is a clean csv with information about 50k+ apartments sold in Stockholm between 2013-2020. 

`Files`
- "Testing environment for scraping Hemnet": For efficient testing of diffrent ways of scraping the desired information from Hemnet. 

# Contributors
Nils Skoglund
