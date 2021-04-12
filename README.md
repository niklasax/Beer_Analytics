# Final Project

[Link to Google Slides Presentation](https://docs.google.com/presentation/d/1plzO1RmnGwcuphdBBIg4B_E85VguzFJXwS64HdTugO4/edit#slide=id.gca229a901d_0_57)

[Link to Tableau Story](https://public.tableau.com/profile/nik6051#!/vizhome/Beer_Analytics/Beer_Analytics?publish=yes)


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

## Outline of Project

Our project wishes to answer one simple question- Can you determine a type of beer based on it's bitterness and alcohol content? This execution of this analysis can be summarized in the three steps below.

### 1.) Data Exploration and Database Integration

The first part of our Analyis involved cleaning and merging the datasets using Python’s Pandas library to get rid of Null values, group attributes into a new columns and filter only for data that will be used in the final analysis. We connected AWS RDS to a local PostgresSQL server using SQLAlchemy, joined the data with a Postgres query and connected Postgres to our Machine Learning Model. 

### 2.) Machine Learning Model

We chose to use Random Forest as a Classifier because it uses labeled data to “learn” how to classify unlabeled data. Some of the benefits of using Random Forest algorithm is very stable, it works well when you have both categorical and numerical data, and it works well if your data hasn’t been scaled well. One of the disadvantages is that it is more complex which requires more computational resources.

How did we split our data? First, the loaded dataset must be split into input and output components. Next, we can split the dataset so that 75 percent is used to train the model and 25 percent is used to evaluate it. This split was chosen arbitrarily. We can then define and fit the model on the training dataset.

### 3.) Result Interpretation and Data Visualization

Overall Score: Our overall weighted precision was 50%. This means that there were 165 true positive results out of the 332 total positive tests of the model. 
What Influenced the score: The amount of observations and the ibu/abv cluster location

Example 1: The ‘American Double’ group received among one of the best scores because it’s cluster contained many test observations in a space that was distant from the other clusters having the highest abv/ibu.

Example 2: The ‘Other’ category was clustered closely to the other beers but performed decently due to the large number of observations 

Example 3: The model predicted none of the ‘Fruit/Vegetable’ beers due to having among the lowest number of observations and it’s cluster being undifferentiated (similar ibu/abv) from the other beers.


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

Cleaned and transformed data is loaded into the respective schema of the database with SQLalchemy. 
Inversely, data can be read into python environments for analyzing by querying the loaded data from the database.
