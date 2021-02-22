# Rate Neighborhoods

## Introduction

Completed as the Capstone Project for IBM Professional Certificate in Data Science.

### Business Question

For a real estate company, **how can we more efficiently sell houses** (or rent apartments)? A major factor in home buyers' decision is the neighborhood surrounding the home. i.e., What businesses and services are nearby? This tool will allow buyers to select their top venue types and will generate a score for each neighborhood based on the buyers' desired features. This will allow real estate agents to focus on neighborhoods that are more suited to the buyers' needs, reducing time wasted on unproductive leads. 


## Methodology


### Data Collection

Inputs: neighborhood or postal code location; buyer's prefered venues

Outputs: neighborhood score from 0 (worst) to 100 (best) 

Data Needs: 
- What types of businesses and services are located within a given radius from a given location. (Foursquare API)


### Data Visualization

A map of the city will be generated with neighborhoods color-coded based on their neighborhood score (high score = green ; low score = purple). 


### Data Manipulation

- A list of neighborhoods and their location is obtained from Wikipedia 
    - using pandas built-in read_html method
- A list of venue categories is scraped from the Foursquare website
    - using BeautifulSoup 
- A list of venues and their categories within each neighborhood is obtained from Foursquare
    - using API requests
- The venue categories are checked against the user preferences. 
- Neighborhoods with a greater number of venues within the user preferences are ranked more highly. 
    - At this time, all venue types within the user preference lists are equally weighted. 
    
    - The users' prefence lists may be of variable length. For example (see below), User 1 is happy with any restuarant type, which means that User 1 will have a greater number of preferred venues in total; this imbalance inevitably skews the results towards User 1's preferences. In order that both users have their preferences more equally weighted, I normalize the number of preferred venues by the number of venue types preferred for each user. 
    
    - Scores for each user are added to get the total score for the neighborhood.
    
    - All scores are divided by the maximum score and multiplied by 100 so that the maximum score is scaled to 100. 



##### For Development and Testing Purposes

- two users with pre-defined preferences
    

|     User 1's preferences :    |    User 2's preferences :   |
|-------------------------------|-----------------------------|
|  Restaurant - any type        |   Football Stadium          |
|  Parks                        |   Music Venues              |
|  Church                       |   Nightlife Spot - any type |
|  Library                      |   Music Festivals           |
|  Elementary School            |   Mexican Restaurants       |
 
  
- the city is pre-defined as New Orleans, LA
    - with latitude and longitude of neighborhoods available in a Wikipedia table

- The number of venues is limited to 50 per neighborhood


## Results

New Orleans's City Planning Commission divides the city into 72 neighborhoods.

The top 5 neighborhoods for this couple are :
 - Mid-City
 - Freret
 - Uptown
 - Lower Garden District
 - East Carrollton
 
Based on my knowledge of the city, this prediction is good. These neighborhoods all have a high concentration of bars and restuarants. The French Quarter is ranked number 23, which is surprisingly low; this might be due to the lack of parks and churches, which are a preference for User 1. 


Static png image for display: 
![Ratings of Neighborhoods](ratings01.png)

## Discussion

The location of a home can be a major selling point if the surrounding neighborhood contains amenities desired by the buyers. This project has taken the preferences of two users and used them to compute a personalized neighborhood score for each neighborhood in New Orleans, LA. Based on my knowledge of the city, the scores are accurate; the neighborhoods with a high concentration of restuarants and bars are scored highly, and those with fewer restuarants and bars have a low score. 

This neighborhood score is similar to a "[walkability score](https://www.walkscore.com/)" because the neighborhood radius is only 1 km (0.6 mi; a 12 minute walk for most adults). However, the neighborhood score presented here is personalized to the preference of the user(s), whereas the standard walkability score is not personalized. One potential addition to this project is a "drivability score" in which venues at a further distance would be taken into account. 

In addition to the neighborhood amenities, other factors such as neighborhood safety and school quality are often important to buyers. This information is not available from Foursquare and so will require integration of new data sources and API's into the current program. There is an opportunity to integrate this type of information with current filtering options on real estate websites so that buyers can better narrow down their options.  


##### Room for Methodological Improvement

- A better category scheme is needed. The categories were taken from Foursquare's website. Sometimes, they seem too detailed, for example, 'Sausage Shop' may not need its own category and could be combined with other 'Grocery' venues. On the other hand,  sometimes the categories are not detailed enough. For example, the 'Church' church category does not contain any information on denomination; if there are 100 Baptist churches but the buyer is Catholic, the neighborhood score will have a false high value. 

- In order to generalized the program, a consistent source for neighborhood location/boundary data is needed. Sometimes this data can be found in geojson files on a city, but sometimes not. Sometimes this data is on Wikipedia, but sometimes not. Also, the url's for the data sources are currently entered manually. An automated way to find neighborhood data is needed. 

- Improvements to the scoring function:
    - An option for ranked-choice of venue types could be added, then the scored function weighted appropriately.
    - The scoring function can give artificially high scores because it is defined to give the best neighborhood a score of 100. Neighborhoods that are overall bad (with a low number of preferred venues) can still look good if the entire city is lacking in the preferred venues. 
    
    
    ## Conclusion

This project was able to successfully determine neighborhoods with the desired venue types for two users. This project could be combined with current filtering options on real estate websites to help potential buyers more rapidly narrow down their housing option, resulting in saved time for the realtor and increased customer satisfaction for the buyer. 
