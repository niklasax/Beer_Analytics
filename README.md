# Final Project

## Resources

Python Pandas, SQLAlchemy, PostgreSQL 12.2, Amazon AWS RDS

## Topic and Data selected
* **Selected Topic:** Craft Beer
* **Reason for Selected topic:** This topic was one that all the members of the group had familiarity and interest in
* **Description of the source data:** This Dataset contains two CSVs pertaining to beer types and breweries:
  * Beers CSV file: Contains data specific to each craft beer (alcohol content, name, type etc..)
  * Breweries CSV file: Contains data specific to each Brewery (brewery name, state located in, city located in). Can be merged with beers.csv on 'brewery_id'.
* **Questions we hope to answer with data:** Can we use machine learning to predict the type of alcohol based on features of the beer.




## Communication Protocols

Our team communicated across various platforms to plan, discuss and execute the project objectives. The three primary communication tools were Slack, Text and Zoom:
* **Slack:** We created a Slack group as a repository for links, git commands, project instructions and other helpful items.
* **Text:** We used text as a means to discuss ideas, organize meeting times and make decisions.
* **Zoom:** We used Zoom during class times to work on issues (virtually) face to face, together in real time.

## Machine Learning Model

Team members will be expected to present a provisional machine learning model that stands in for the final machine learning model and accomplishes the following:

Takes in data from the provisional database
Outputs label for input data

## Database Integration
A AWS Postgres Database instance has been set up to store the cleaned and transformed data. 
With the data accessible it is then read in directly to the python environment by incorporating the database connection in the machine learning notebook. 
