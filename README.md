## Intersections between Topic Models and GIS

In this project, I fit a regular linear model to Twitter data that I have processed using both topic modelling and GIS methods to see if the frequency of tweets in an area can be predicted using the topics found in tweets. 

To do this, I used tweets from New York City collected during one day. I then got the counts of tweets in the census tracts of New York City using GIS. Additionally, I had to find the optimal amount of topics for my dataset, followed by the actual modelling of topics using Latent Dirichlet-Allocation. I then used a linear model to fit the data, trying to predict the frequency associated with a tweet using the most likely topic for each tweet. To assess the quality of the prediction, I used the square-root of the mean-squared error.

### The Data

The data used here was generated during one day of scraping tweets in the state of New York, using a geographic boundary box and a Python scraper running on a Heroku cloud instance, saving tweets to MongoDB. 

The data was then converted to CSV-format, saving relevant parameters, and processed for analysis using QGIS and R packages for GIS. All tweets outside of New York City were dropped and tweets were compared to spatial data on the census tracts in New York City, to get the amount of tweets per tract. Using the "intersect" function in QGIS, I then got the counts for the tract that each tweet was located in, associating every tweet with the amount of tweets in the tract. This data was then exported as a shapefile of points, with every point representing a tweet, and imported with R to get topics and fit my linear model.

I have used this same Twitter data in a [QMSS GIS class](https://github.com/maybemkl/GIS_tweets) to see if tweet counts normalized by area size can act as predictors for gentrification. The raw data was the same, but the preprocessing steps were different. 

A knitted version of the project can be found [here](https://rpubs.com/maybemkl/topicGIS).