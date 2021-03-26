# Final Project
<<<<<<< HEAD
=======
=======

>>>>>>> 14a5af326d31fb36c7976cd4dc6fc2a7455a23c5
<p align = "center">
<img src = "https://rlv.zcache.com/periodic_table_of_beer_styles_poster-ra7fb9b6684f8466f9abfdd9262630cf4_6rq_8byvr_704.jpg">
</p>
<br>
<<<<<<< HEAD
=======

>>>>>>> 14a5af326d31fb36c7976cd4dc6fc2a7455a23c5
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
<<<<<<< HEAD
=======
Using sqlalchemy, we established a database connection to our cleaned data by using the create_engine(database) function to communicate with our sql file.
We were then able to take in the provisional data and use the train_test_split function in the Sklearn model to split our arrays into our training and test data. From there we could use y_train to output our lablels.

=======

Using sqlalchemy, we established a database connection to our cleaned data by using the create_engine(database) function to communicate with our sql file.
We were then able to take in the provisional data and use the train_test_split function in the Sklearn model to split our arrays into our training and test data. From there we could use y_train to output our lablels.

<<<<<<< HEAD

>>>>>>> 14a5af326d31fb36c7976cd4dc6fc2a7455a23c5
=======
>>>>>>> 0b06138cbacb12d41230b34b36d90431b9c14ca1
## Database Integration
An AWS Postgres Database instance has been set up to store the cleaned and transformed data. 
With the data accessible it is then read in directly to the python environment by incorporating the database connection in the machine learning notebook.  
