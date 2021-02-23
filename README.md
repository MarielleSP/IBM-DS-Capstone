# Rate-Neighborhoods


## Introduction
This project will use location data from Foursquare on what types of businesses and services are located within a given radius from a given location (address or latitude plus longitude). Based on their preferences of the user (e.g. proximity to dog park, school district, etc.), a neighborhood rating will be generated. 
Completed as the Capstone Project for IBM Professional Certificate in Data Science. 


## Technologies
python 3.7.3

numpy 1.16.2

pandas 1.1.0

requests 2.18.3

folium 0.5.0

dotenv 

os

re 2.2.1

matplotlib

BeautifulSoup


## Launch
The notebook can be downloaded and run on your local machine.

You will need to make a .env file with your Foursquare access key or hard-code them into your local copy of the notebook. 
The .env file should include your CLIENT_ID, SECRET_KEY, ACCESS_TOKEN, and VERSION

The user preferences need to be hard-coded in the notebook as a list. Any sub-category or main category can be chosen from the Foursquare list. If a main category is desired, use the format "Category - any" in the preferences list. The code is set up to run with exactly 2 users. If a greater or fewer number of users is desired, the code will need to be modified. 

