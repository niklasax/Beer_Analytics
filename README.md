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
* **Description of the source data:** This Dataset contains two CSVs pertaining to beer types and breweries from Kaggle.com:
  * [Beers CSV file](https://www.kaggle.com/nickhould/craft-cans?select=beers.csv): Contains data specific to each craft beer (alcohol content, name, type etc..)
  * [Breweries CSV file](https://www.kaggle.com/nickhould/craft-cans?select=breweries.csv): Contains data specific to each Brewery (brewery name, state located in, city located in). Can be merged with beers.csv on 'brewery_id'.
* **Questions we hope to answer with data:** Can we use machine learning to predict the type of alcohol based on features of the beer?

## Outline of Project

Our project wishes to answer one simple question- Can you determine a type of beer based on it's bitterness and alcohol content? This execution of this analysis can be summarized in the three steps below.

### 1.) Data Exploration and Database Integration

The first part of our Analyis involved cleaning and merging the datasets using Python’s Pandas library to get rid of Null values, group attributes into a new column and filter only for data that will be used in the final analysis. We connected AWS RDS to a local PostgresSQL server using SQLAlchemy, joined the data with a Postgres query and connected Postgres to our Machine Learning Model. 

### 2.) Machine Learning Model

Preliminary data processing was done by cleaning the merged dataset using Python’s Pandas library to get rid of Null values, group attributes into a new column and filter only for data that will be used in the final analysis.

## How the data was split:
First, the loaded dataset was split into input and output components. Next, we split the dataset so that 75 percent is used to train the model and 25 percent is used to evaluate it. This split was chosen arbitrarily. We can then define and fit the model on the training dataset.

We separated our dataset into our features and target:

* **Feature (1) ABV: Alcohol by volume (abbreviated as ABV, abv, or alc/vol) is a standard measure of how much alcohol (ethanol) is contained in a given volume of an alcoholic beverage. (In our case... beer!).
* **Feature (2) IBU: The International Bittering Units scale, or simply IBU scale, is used to approximately quantify the bitterness of beer.
* **Target is Style_group, a term used to differentiate and categorize beers by factors such as color, flavor, strength, ingredients, production method, recipe, history, or origin.

## Explanation of Model Choice
We chose Random Forest Classifier because it uses labeled data to “learn” how to classify unlabeled data. Some of the benefits of using Random Forest algorithm is very stable, it works well when you have both categorical and numerical data, and it works well if your data hasn’t been scaled well. One of the disadvantages is that it is more complex which requires more computational resources.

## Training
We then created 100 trees of random samples of the data to train each tree on different samples. Predictions were then made by averaging the predictions of each decision tree. 

## Results Explination

## Conclusion

* **American IPA and American Amber/ Red Ale combines too many IBUs and ABVs.
* **The IBU and ABV range of American Blonde Ale and American Pale Wheat Ale are almost identical.
* **Fruit / Vegetable Beer is the most soft flavours and then Hefeweizen.
* **American Double / Imperial ALE is most bitterness and alcoholic beer.
* **American Brown Ale and American Porter seems to be are almost identical with relatively low IBU and wide range in acohol.
* **American Pale Ale tends to be a soft beer.

Therefore, there is no clear correlation between ABV & IBU and a style. So, the simple scale is not available to clearly distinguish beer styles.

### 3.) Result Interpretation and Data Visualization

We successfully ran our model and with 50% accuracy. From there, we visualized our results and dataset using Tableau story to illustrate features of our dataset and the results.
![ml_accuracy.png](https://github.com/niklasax/Final_Project/blob/main/Project_Pics/ml_accuracy.png)

## Database Integration
An AWS Postgres Database instance has been set up to store the cleaned and transformed data. 
With the data accessible it is then read in directly to the python environment by incorporating the database connection in the machine learning notebook.  

<b>Database Entity Relationship Diagram</b><br>
![database_schema](https://github.com/niklasax/Final_Project/blob/main/beer_database/beer_db%20ERD.png)

