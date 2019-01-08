# predicting_fantasy_football_scores
Linear Regression Model to Predict Fantasy Football Scores for Quarterbacks:

This was my first real data science project. Below is a short description of the purpose of each file.

## Scrape Game Data One Team

This file does exactly what it sounds like. The 16 inputs are scraped from fantasydata.com using BeautifulSoup and Selenium for just one of the 32 different teams. The password entered in the code posted here is incorrect so the code will not run properly due to the fact that the logging in process will be unsuccessful. This can be easily changed.

## Scrape Game Data All Teams

This file creates functions using the code from Scrape Game Data One Team, and runs the functions in a loop in order to acquire the data for all 32 NFL teams, and places them all into one dataframe. Data is then collected from a different part of the website for three more features and puts these points into a separate dataframe. Both dataframes are then pickled to use in a different file. Similar to Scrape Game Data One Team, the password entered is incorrect so the code will not run properly because the logging in process will be unsuccessful.

## Clean Data

This file brings in the pickled dataframes from Scrape Game Data All Teams. Then, the quarterbacks who have played less than four games are filtered out the of the dataframe. After this, each row is changed so that the row reads the average for each feature prior to the game (except for the fantasy points scored that game, which is what is trying to be predicted). The same is done for the second dataframe with the three remaining features, and the dataframes are merged into one large dataframe. Lastly, the first three games for each quarterback are removed as the averages are more erratic prior to these games. The final dataframe is then pickled and ready for modeling.

## Modeling
Different modeling techniques are applied to the data in order to achieve a model that can accurately predict fantasy scores. The final model is a second degree ridge regression model which uses three features.
