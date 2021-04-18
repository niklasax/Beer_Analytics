# Final Project

[Link to Google Slides Presentation](https://docs.google.com/presentation/d/1plzO1RmnGwcuphdBBIg4B_E85VguzFJXwS64HdTugO4/edit#slide=id.gca229a901d_0_57)

[Link to Tableau Story](https://public.tableau.com/profile/nik6051#!/vizhome/Beer_Analytics/Beer_Analytics?publish=yes)


## Resources
* **Data Analysis:** Python Pandas, SQLAlchemy
* **Database:** PostgreSQL 12.2, Amazon AWS RDS
* **Presentation:** Google Slides, Tableau


## Outline of Project
* **Selected Topic:** Craft Beer
* **Reason for Selected topic:** This topic was one that all the members of the group had familiarity and interest in
* **Description of the source data:** This Dataset contains two CSVs pertaining to beer types and breweries from Kaggle.com:
  * [Beers CSV file](https://www.kaggle.com/nickhould/craft-cans?select=beers.csv): Contains data specific to each craft beer (alcohol content, name, type etc..)
  * [Breweries CSV file](https://www.kaggle.com/nickhould/craft-cans?select=breweries.csv): Contains data specific to each Brewery (brewery name, state located in, city located in). Can be merged with beers.csv on 'brewery_id'.
* **Questions we hope to answer with data:** Can we use a machine learning algorithm to predict the type of alcohol based on features of the beer?

**What should the final product look like?:**

* README and Presentation that describes high level outline of analysis
* Database to house and pull the data from
* Machine learning model that predicts beer type based on factors of the beer
* Interactive Tableau Visualization that summarizes the data and outcome of the analysis



## Project Overview


*See Google slides for more detail


### 1.) Data Exploration, Manipulation and Integration

The first part of our Analyis involved looking at the raw data to make sure it was usable for our analysis, we wanted to assure there were enough data points and enough diverse data points to use in a machine learning model. We cleaned and merged the datasets using Python’s Pandas library to get rid of Null values, group attributes into a new columns and filter only for data that will be used in the final analysis. After cleaning the data, we were left with 1326 unique data points to use which we determined was sufficient to use in our model. 

![database_schema](https://github.com/niklasax/Final_Project/blob/main/beer_database/beer_db%20ERD.png)

**How did we integrate our database?:** After cleaning the data, we connected AWS RDS to a local PostgresSQL server using SQLAlchemy, joined the data with a Postgres query and connected Postgres to our Machine Learning Model. 

![](https://github.com/niklasax/Final_Project/blob/main/Project_Pics/data_flow_chart.png)

### 2.) Machine Learning Model

**Explanation of Model Choice:** We chose Random Forest Classifier because it uses labeled data to “learn” how to classify unlabeled data. Some of the benefits of using Random Forest algorithm is very stable, it works well when you have both categorical and numerical data, and it works well if your data hasn’t been scaled well. One of the disadvantages is that it is more complex which requires more computational resources.

**How the Data was Split:** We seperated our dataset into 2 features (inputs) and 1 target (output):
* Feature (1) ABV: Alcohol by volume (abbreviated as ABV, abv, or alc/vol) is a standard measure of how much alcohol (ethanol) is contained in a given volume of an alcoholic beverage. (In our case... beer!).
* Feature (2) IBU: The International Bittering Units scale, or simply IBU scale, is used to approximately quantify the bitterness of beer.
* Target is Style_group, a term used to differentiate and categorize beers by factors such as color, flavor, strength, ingredients, production method, recipe, history, or origin.

We used a train/split of 75/25, so 75% of the data was used to train the model and 25% of the data was used to test the model.


### 3.) Result Interpretation and Data Visualization

**Overall Score:** Our overall weighted precision was 50%. This means that there were 165 true positive results out of the 332 total positive tests of the model. 

**What Influenced the Score?:** The amount of observations and the ibu/abv cluster location relative to other clusters. The model was successful for Beer Styles that had more observations and a higher ibu/abv combination due to the more unique clusters it formed. Put another way, the model could recognize the more unique ibu/abv combinations better than the 

Preliminary data processing was done by cleaning the merged dataset using Python’s Pandas library to get rid of Null values, group attributes into a new column and filter only for data that will be used in the final analysis.

## How the data was split:
First, the loaded dataset was split into input and output components. Next, we split the dataset so that 75 percent is used to train the model and 25 percent is used to evaluate it. This split was chosen arbitrarily. We can then define and fit the model on the training dataset.

We separated our dataset into our features and target:

* Feature (1) ABV: Alcohol by volume (abbreviated as ABV, abv, or alc/vol) is a standard measure of how much alcohol (ethanol) is contained in a given volume of an alcoholic beverage. (In our case... beer!).
* Feature (2) IBU: The International Bittering Units scale, or simply IBU scale, is used to approximately quantify the bitterness of beer.
* Target is Style_group, a term used to differentiate and categorize beers by factors such as color, flavor, strength, ingredients, production method, recipe, history, or origin.

## Explanation of Model Choice
We chose Random Forest Classifier because it uses labeled data to “learn” how to classify unlabeled data. Some of the benefits of using Random Forest algorithm is very stable, it works well when you have both categorical and numerical data, and it works well if your data hasn’t been scaled well. One of the disadvantages is that it is more complex which requires more computational resources.


### 3.) Result Interpretation and Data Visualization

We successfully ran our model and with 50% accuracy. From there, we visualized our results and dataset using Tableau story to illustrate features of our dataset and the results.

* Example 1: The ‘American Double’ group received among one of the best scores because it’s cluster contained many test observations in a space that was distant from the other clusters having the highest abv/ibu.
* Example 2: The ‘Other’ category was clustered closely to the other beers but performed decently due to the large number of observations 
* Example 3: The model predicted none of the ‘Fruit/Vegetable’ beers due to having among the lowest number of observations and it’s cluster being undifferentiated (similar ibu/abv) from the other beers.

![](https://github.com/niklasax/Final_Project/blob/main/Project_Pics/ml_accuracy.png)

**Data Visualization/Dashboard:** We visualized our data and our results using Tableau. We chose Tableau due to it's intuitive and easy to use design, as well as it's interactive functionality that allow us to manipulate our visualizations in real time. The link to our Tableau story is at the top of the readme.

**In Conclusion:** Our model was successful for Beer Styles that had more observations and a higher ibu/abv combination due to the more unique clusters it formed.

Considerations for future tweaks of the model to improve accuracy:
* Use more train data: We only used 25% train this time, in the future we could potentially go up to 30%
* Add more variables: We could’ve used more X variables in our analysis such as location (State, City) to see if the accuracy results would improve
* Revisit Style groupings: We took the simple approach of grouping any beer with less than or equal to 26 occurrences into a single ‘other’ category. In a further analysis we could have split this into multiple groupings that considered ibu/abv combinations instead of grouping by occurrences.




