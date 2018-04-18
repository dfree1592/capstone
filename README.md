### This Project Analyze What Factors Make a Probowl Punter

Intro:

In this project, the goal was predict whether or not a punter in the NFL will make the Pro Bowl for that season. The focus on punters was  because they have the most influence on how the rest of the game is going to play out. A Punter can dramatically change the game plan for the opposing team. If he punts the ball within 20 yards from the end zone (Red Zone) it will limit the types of plays that the offense will run, giving the defense an advantage. There are other multiple statistics that could determine what makes a Pro Bowl punter. The data suggests that best way to predict this would be through Decision Trees because they are a very powerful machine learning model. Bagged Decision Trees and Random Forests were also used to offset the overfitting. During the this project the part that took the most time was the data cleaning.


Data Acquisition:

The data acquisition was straight forward. Originally The idea was to  web scrape using beautifulsoup or use an API that they might have. After more research neither of the two websites that stored this data made an API that could be used. There is a method in the Pandas library, which would let me extract a table from a page on webpage. The method turned of to pd.read_html(‘url’). 

Data Cleaning:

When the data was loaded in to the notebook, it was loaded as a list. The entire dataframe was on string of a list. The Data frame was the first element of that list. Once that was a workable pandas dataframe, the columns were renamed to what was titled from the original data. Additions had to be had because when looking through the data there was some missing players that need to be added. Multiple times the shape of the data frame was was not the right length of rows. At the same time there were extra punters that were listed because some teams had multiple punters, even though those additional punters only had a minimal amount of punts for the season. This involved cross referencing the different pages of the origin site to find the correct statistics for the missing players. Another way the data was clean was, all of the drafted objects were changed to either 1 or 0 depending if the punter was drafted or not. 
After the data cleaning was done, it was time do the same process for another dataset from a different data source regarding if the punter made the Pro Bowl. Once that dataframe included the missing players, each year’s non-Pro Bowl and Pro Bowl dataframes were merged. 

Operationalized Outcome Variable:

The target variable was if the punter made a Pro Bowl or not. The target variable Pro Bowls because this is the goal of the project to classify/ predict whether or not a punter will make the Pro Bowl. 
Features that were omitted were the objects (Player Name, Team Name), the target variable (Pro Bowl), and a couple features that were not particularly relevant using subjective domain knowledge (Punts Returned,  Punt Return Yards). 

Model,  Hyperparameters, and Metrics:

The Models that were used were Decision Trees, Bagged Trees, Random Forests. Decision trees were used because they are nimble and powerful models which cancel many of the potential errors out. As well, even if its assumptions are somewhat violated by the true model from which the data were generated.
When there was no adjustment of the hyperparameters the models were severely overfit. Altering the sample size and impurity of the leafs helped the model reach an acceptable bias/variance trade off. The precision score was 82% and the recall was 91%. Another way to evaluate the model was by using cross-validation. When the model was not overfit the cross-validation score for the decision trees and random forests was between 84% - 90%. 

Future Deployments:


A few tweaks that would be interesting to add would be adding the feature of the punters hang time. THis would be an interesting feature because the amount of hang time may correlate with the number of fair catches. It would be interesting to see if that as an added feature would make a difference to whether or not a punter would make the Pro Bowl.


Data Sources:

Pro-football-reference.com
footballdb.com
