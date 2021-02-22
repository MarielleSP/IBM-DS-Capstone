## Project Summary

Completed as the Capstone Project for IBM Professional Certificate in Data Science.

For a real estate company, a major consideration is **how can we more efficiently sell houses?** One factor in home buyers' decision is the neighborhood surrounding the home, in particular the types of businesses and services that are nearby. This tool will allow buyers to select their top venue types and will generate a personalized score for each neighborhood based on the buyers' desired features. This will allow real estate agents to focus on neighborhoods that are more suited to the buyers' needs, reducing time wasted on unproductive leads. 

Let's consider a couple wanting to buy a home in New Orleans, LA. The couple have the following preferences:  
    

|     User 1 :                  |          User 2 :           |
|-------------------------------|-----------------------------|
|  Restaurant - any type        |   Football Stadium          |
|  Parks                        |   Music Venues              |
|  Church                       |   Nightlife Spot - any type |
|  Library                      |   Music Festivals           |
|  Elementary School            |   Mexican Restaurants       |
 
  
The following map is generated with dots for each neighborhood color coded with dark green being the best neighborhoods and dark red being the worst neighborhoods for the preferences of this couple.  
![Static png image for display](ratings01.png)




The top 5 highest-scoring neighborhoods for this couple are :
 - Mid-City
 - Freret
 - Uptown
 - Lower Garden District
 - East Carrollton
 
Based on my knowledge of the city, this prediction is good. These neighborhoods all have a high concentration of restuarants and nightlife spots, which are preferred by this couple. (The French Quarter is ranked number 23, which is surprisingly low; this might be due to the lack of parks and churches, which are a preference for User 1.) 


In addition to the neighborhood amenities, other factors such as neighborhood safety and school quality are often important to buyers. This information is not available from Foursquare and so will require integration of new data sources and API's into the current program. This project could be combined with current filtering options on real estate websites to help potential buyers more rapidly narrow down their housing option, resulting in saved time for the realtor and increased customer satisfaction for the buyer.  


For more details, check out the [Full Report and Jupyter notebook](https://github.com/MarielleSP/Rate-Neighborhoods/blob/main/Rate-Neighborhoods.ipynb).





