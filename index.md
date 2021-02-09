## Introduction

Completed as the Capstone Project for IBM Professional Certificate in Data Science.

### Business Question

For a real estate company, **how can we more efficiently sell houses** (or rent apartments)? A major factor in home buyers' decision is the neighborhood surrounding the home. i.e., What businesses and services are nearby? This tool will allow buyers to select their top venue types and will generate a score for each neighborhood based on the buyers' desired features. This will allow real estate agents to focus on neighborhoods that are more suited to the buyers' needs, reducing time wasted on unproductive leads. 

### Data Collection

Inputs: neighborhood or postal code location; buyer's prefered venues

Outputs: neighborhood score from 0 (worst) to 100 (best) 

Data Needs: 
- What types of businesses and services are located within a given radius from a given location. (Foursquare API)

### Data Manipulation

- The number of venue types in Foursquare is very large and will need to be reduced to make a list from which buyers can select. 
- The reduced venue types will receive one-hot encoding, and the sum of each venue type will be entered into the scoring function. 
- The users' preferences will provide a weight for each venue type within the scoring function. The number of venues and weights of each type will provide a score that needs to be scaled to 100 as a maximum. 
    - Option for multiple users' preferences, e.g. for spouses with different preferences


### Data Visualization

A map of the city will be generated with neighborhoods color-coded based on their neighborhood score (high score = green ; low score = red). 


#### For Development and Testing Purposes

- two users with pre-defined preferences
- the city is pre-defined as New Orleans, LA
    - with latitude and longitude available in a Wikipedia table
- The number of venues is limited to 10 per neighborhood


[Jupyter notebook](https://https://github.com/MarielleSP/Rate-Neighborhoods/blob/main/Rate-Neighborhoods.ipynb)


## Discussion

### Room for Improvement

- The categories from Foursquare are a little wonky, sometimes too detailed (e.g., 'Sausage Shop'), sometimes not detailed enough (e.g. 'Church' but no ability to select denomination). A better category scheme is needed. 
- The score could be modified to provide a walking score and a driving score.
- Other types of data are also important:
    - safety of the neighborhood
    - quality of schools and other venues
- There does not seem to be a single source for neighborhood data online. 
- A realistic number of venues will require a paid account.



