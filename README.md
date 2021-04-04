# Final Project

[Link to Google Slides Presentation](https://docs.google.com/presentation/d/1plzO1RmnGwcuphdBBIg4B_E85VguzFJXwS64HdTugO4/edit#slide=id.gca229a901d_0_57)

[Link to Tableau Story](https://public.tableau.com/profile/nik6051#!/vizhome/Beer_Analytics/Beer_Analytics?publish=yes)

[Link to Tableau Dashboard](https://public.tableau.com/views/CraftBeersProject/Dashboard1?:language=en&:display_count=y&publish=yes&:origin=viz_share_link)

## Resources

* **Data Analysis:** Python Pandas, SQLAlchemy
* **Database:** PostgreSQL 12.2, Amazon AWS RDS
* **Presentation:** Google Slides, Tableau

## Topic and Data selected
* **Selected Topic:** Craft Beer
* **Reason for Selected topic:** This topic was one that all the members of the group had familiarity and interest in
* **Description of the source data:** This Dataset contains two CSVs pertaining to beer types and breweries s from Kaggle.com:
  * [Beers CSV file](https://www.kaggle.com/nickhould/craft-cans?select=beers.csv): Contains data specific to each craft beer (alcohol content, name, type etc..)
  * [Breweries CSV file](https://www.kaggle.com/nickhould/craft-cans?select=breweries.csv): Contains data specific to each Brewery (brewery name, state located in, city located in). Can be merged with beers.csv on 'brewery_id'.
* **Questions we hope to answer with data:** Can we use machine learning to predict the type of alcohol based on features of the beer?


## Communication Protocols

Our team communicated across various platforms to plan, discuss and execute the project objectives. The three primary communication tools were Slack, Text and Zoom:
* **Slack:** We created a Slack group as a repository for links, git commands, project instructions and other helpful items.
* **Text:** We used text as a means to discuss ideas, organize meeting times and make decisions.
* **Zoom:** We used Zoom during class times to work on issues (virtually) face to face, together in real time.

## Machine Learning Model

Using sqlalchemy, we established a database connection to our cleaned data by using the create_engine(database) function to communicate with our sql file.
We were then able to take in the provisional data and use the train_test_split function in the Sklearn model to split our arrays into our training and test data. From there we could use y_train to output our lablels.



Using sqlalchemy, we established a database connection to our cleaned data by using the create_engine(database) function to communicate with our sql file.
We were then able to take in the provisional data and use the train_test_split function in the Sklearn model to split our arrays into our training and test data. From there we could use y_train to output our lablels.


## Database Integration
An AWS Postgres Database instance has been set up to store the cleaned and transformed data. 
With the data accessible it is then read in directly to the python environment by incorporating the database connection in the machine learning notebook.  


## Database 
An AWS Postgres Database instance has been set up to allow for remote connections. 

Cleaned and transformed data is loaded into the respective schema of the database through connecting using the SQLaclemy Library. 
Inversly data can be read into python envorinmets for analyzing by querying the loaded data from the dtabase. 

 


