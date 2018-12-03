# Exploration in 2018 FIFA Player Library
### Team: I love coding
### Members: Yahan Hu, Chenchen He, Lili Yan, Shipei Feng
 
## Introduction:
The growing interests in soccer and FIFA drive the creation of our project. Our project provides a well-rounded library presenting summarized statistics and analysis by extracting player personal attributes, player performance attributes, and ratings at all positions. User interaction and data visualization enable users to customize their questions and find answers out of our project. In general, our project is further separated into 4 parts that bring different insights about FIFA to users.

## Installation:
!pip install prettytable

!pip install msgpack

!pip install wordcloud
 
### Part I: (User Interaction): 
#### < Find the best squad for each formation in terms of players, clubs, countries >
This section is to find out the best squad given selected information by users. Users choices include formation type, nationality, and club. 
 
### Part II: (User Interaction):
#### < Compare the performance between two players, two clubs or two countries >
This part is aimed to compare different players, clubs, and countries in several aspects, like age, value, potential, and skills. The part also extends to provide all simple predictions of game results based on two clubs’ (or countries’) five formations. The comparison results are mainly presented in two graphs and one table. 

### Part III: (User Interaction):
#### < Measure a player’s value aligned with multiple factors >
This portion is designed to give users some insights about a player’s value(€) with associated impacting factors and a player’s value(€) position within the whole FIFA. We use a line chart to plot a relationship between age and score for a individual player. We also create linear regression models to predict the correlation between value(€) and three different factors(Age, Overall rating, Potential rating) among the whole FIFA, which is further used to spot a individual player’s position the user chose.   

### Part IV: (User Interaction)
#### < Find required ability for every position >
This part offers our users some understanding about what important abilities each group of positions require based on the current FIFA registered players. To clearly and visually present our result, we use principal components analysis that reduces the dimensions and sum up these data to 3 abilities that a soccer player should have.
 
## Data Description:
#### The data is downloaded from the website listed below:
https://www.kaggle.com/thec03u5/fifa-18-demo-player-dataset#CompleteDataset.csv

#### The FIFA 18 complete Dataset includes:
●	Player personal attributes (Age, Value, Nationality, club, etc.); 
●	Player performance attributes (Acceleration, Aggression,Balance etc.)  
●	Player preferred position (CM, FB, RAM, RCM etc.)  and both overall ratings and potential ratings at all positions.
These attributes provide us with huge varieties of indicators to analyze these four topics listed above.
 
 
## Run Instruction:
### Part I (User Interaction): 
#### < Find the best squad for each formation in terms of players, clubs, countries >
The goal of this section is to find the best Squad (including player’s name, preferred position, overall rate, nationality, and club), given the selected information. The performance is measured by the overall rating.
 
●	Find the best Squad given the selected formation among all players.
The program takes one parameter:
Ø  Formation (eg. 433, 424, 442, 343, 451)
The best Squad for the formation user chose is predicted by the program showing below:
![Best_Squad_formation](https://github.com/YahanCU/Project-for-tools/blob/master/images/Part1-1.png)
 
This table shows the best Squad you can get under the formation you chose based on a player’s overall performance. This information could give you some insights about top individual player’s overall skills. 

●	Find the best Squad for different formation given the selected country.
This program takes one parameter:
Ø  Country/Nationality (eg. Brazil, Spain, Germany etc.)
The best Squads for different formations are listed below given the selected country.
![Country_Squad_formation1](https://github.com/YahanCU/Project-for-tools/blob/master/images/Part1-2.png)
![Country_Squad_formation2](https://github.com/YahanCU/Project-for-tools/blob/master/images/Part1-3.png)
![Country_Squad_formation3](https://github.com/YahanCU/Project-for-tools/blob/master/images/Part1-4.png)
 
This table shows the best Squad you can get under different formations within one country. This information is able to offer you some guidance about players’ selection under specific formation or compare overall performances between formations. 

●	Find the best Squad for different formation given the selected club.
      This program takes one parameter:
Ø  Club (eg. Manchester United, Manchester City, Juventus etc.)
       The best Squads for different formations are listed below given the selected country.
 ![Club_Squad_formation1](https://github.com/YahanCU/Project-for-tools/blob/master/images/Part1-6.png)
 ![Club_Squad_formation2](https://github.com/YahanCU/Project-for-tools/blob/master/images/Part1-7.png)
  
 
This library provides a list of players under different formations within one club. The information can be used to provide you with some insights about players’ selections within a club and comparisons between different formations.  
 
 
 
### Part II (User Interaction):
#### < Compare the performance between two players, two clubs or two countries >
This part is used to compare different players, clubs, and countries in several aspects.

●	First, we can compare any two players by function player_compare().

This function will require input at first. Following the hint("Enter two players' names you want to compare(separated by ',')), the function will automatically extract parameters:

Ø  Two player names (eg. Cristiano Ronaldo, Neymar)

Then the result includes two graphs, bar chart and radar graph as following:

![compareplayer](https://github.com/YahanCU/Project-for-tools/blob/master/images/part2-1.png)

First from the bar chart, we can easily compare players’current performance and future performance according to overall rate and potential separately. Also based on age, we could learn which one player has a longer career. Those differences may finally determine which player has a higher value, which has been presented in labels next to names.

Then, from the radar graph, we could have a clear view of differences in two players’ capability. For example, Ronaldo is significantly better than Neymar in two aspects, Shot power and strength, while Neymar is little better than Rnaldo about Dribbing and Acceleration. In the different formation, the differences of those players’skills may lead to the game to be won or lost.

●	Second, we can compare any two clubs by function club_compare().

This function will require input at first. Following the hint("Enter two clubs' names you want to compare(separated by ',')), the function will automatically extract parameters:

Ø Two club’s name (eg. Paris Saint-Germain, FC Barcelona)

Then the result includes one prediction table and two graphs, bar chart and radar graph as following:

![compareclub](https://github.com/YahanCU/Project-for-tools/blob/master/images/part2-2.png) 

First from prediction table, we could obtain simple predicted results for two clubs when they choose five kinds of formation. For each club, we find the best squad for each formation. So the column,Overall rate, means the sum of 11 players’overall rate in the best squad given a certain formation. According this table, we can find that the formation is actually important. Sometimes, a club can win the game even it has lower comprehensive capacity, if it chooses a proper formation.

Then from the bar chart, we can easily compare clubs’current performance and future performance according to the average of their players’overall rate and potential separately. Also based on average age, we could learn which one club is more energetic. Those differences may finally determine which club’s player has a higher average value, which has been presented in labels next to names.

Finally from the radar graph, we could have a clear view of differences in two clubs’ capability. For example, Paris is little better than FC about Finishing and Ball control. Thus, if Paris chooses a formation more focusing on Forward and Midfielder, it would be more likely to win the game with FC. This analysis can be revealed by the prediction table above.
 
●	Finally, we can compare any two countries by function country_compare().

This function will require input at first. Following the hint("Enter two countries’' names you want to compare(separated by ',')), the function will automatically extract parameters:

ØTwo countries (eg. Germany, France)

Then the result includes one prediction table and two graphs, bar chart and radar graph as following:

![comparecountry](https://github.com/YahanCU/Project-for-tools/blob/master/images/part2-3.png) 

First from prediction table, we could obtain simple predicted results for two countries when they choose five kinds of formation. For each club, we find the best squad for each formation. So the column, Overall rate, means the sum of 11 players’overall rate in the best squad given a certain formation. According this table, we can find that the formation is actually important. Sometimes, a country can win the game even it has lower comprehensive capacity, if it chooses a proper formation.

Then from the bar chart, we can easily compare countries’current performance and future performance according to the average of their players’overall rate and potential separately. Also based on average age, we could learn which one country is more energetic. Those differences may finally determine which country’s player has a higher average value, which has been presented in labels next to names.

Finally from the radar graph, we could have a clear view of differences in two countries’ capability. For example, Germany has similar capability with France. Thus, the chance that Germany win the games with France is almost 50%, which can be figured out in prediction table.
 
### Part III (User Interaction):
#### < Measure a player’s value aligned with multiple factors >
The aim of this part is to measure players’ value aligned with multiple factors, and spot certain player’s position in the whole FIFA from different angles.

●	 Find the relationship between age and rating (overall score and potential score) by function Age_Score()
This program takes one parameter
Ø  Player name (eg. A. Aseri)
  
 ![Age_Score](https://github.com/YahanCU/Project-for-tools/blob/master/images/part3-1.png)    
The curve shows the trend of scores changes along with age. It can be clearly seen that potential score decreases slowly with age, while overall score increases with age, and the two scores stay equal after  30 years old, indicating the player almost reaching out to his career peak. After 35 years old, the whole score of the player decreases significantly, which fits the athlete's life cycle.
The star-shaped points represent the overall and potential score of the player user wants to know. Take A. Aseri as an example, his potential and overall score are both higher than the mean, and the difference is large, showing he has better performance than his peer’s and has great potential for growth.

●	 Linear Regression
This function regression() has no input, the result is shown in the image and table.
  
 ![regression](https://github.com/YahanCU/Project-for-tools/blob/master/images/part3-2.png)  
Using the multiple linear regression, we have an equation describes the relationship between value and two factors: value = 0.6463 potential + 0.2336 age - 0.0015.
As shown in the 3-dimensional plot, after removing the high value of star players, the regression fits the real scatters. In the scale of [-4,3], the minimum mean square of 0.7828 is small enough to assert this regression is accurate.

●	The decision of a certain player
Help your decision on whether buying a player or not using the function Value().
This program takes one parameter
Ø  Player name (eg. Pepe)
  
 ![Value](https://github.com/YahanCU/Project-for-tools/blob/master/images/part3-3-1.png)  
 ![Value](https://github.com/YahanCU/Project-for-tools/blob/master/images/part3-3-2.png)
 ![Value](https://github.com/YahanCU/Project-for-tools/blob/master/images/part3-3-3.png)
The output includes three pictures and two tables.
The upper picture shows the polyfitting curve of age and value, blue scatters are the median value of each age group. Input “Pepe”, the yellow dotted line means at Pepe’s age (34), the polyffting median value is about €600,000. The following two figures are the same, and the only difference is the x-axis changes to overall score and potential score.
The first table contains basic information of “Pepe”, especially showing the difference of his real value and the median value. 
The second table shows the decision we make, after calculating we find he is worth buying.


●	10 worth-buying players
This function worthbuy()  has no input.
  
 ![worthbuy](https://github.com/YahanCU/Project-for-tools/blob/master/images/part3-4.png)  
The output is a single table, containing information of 10 most worth-buying players. Among all worth-buying players, their overall scores are the highest. The table is descending sorted by potential scores.

### Part IV:(User Interaction)
#### < Find required ability for every position >
This part illustrates the most important abilities each group of positions require based on the current FIFA registered players. The final result is presented through the following process:

●	Step1: 
This step we calculate the mean of dataset group by the position. 
For this step just run the cell.

●	Step2:
Draw the graph of Cumulative Variance to decide how many new variables should we choose. From the result, we can see that 3 is the best number. 
![graph](https://github.com/YahanCU/Project-for-tools/blob/master/images/pca_00.jpg)
 
●	Step3:
Use the PCA model to reduce the dimension of the dataset. 
The picture below is the relationship between the new variables(Special, Attack-Defense,Dribble-Accuracy) and the original variables(Age,Special,Accelaration etc.). Basically,we summarize the original attributes into three new attributes. 
![graph](https://github.com/YahanCU/Project-for-tools/blob/master/images/pca_1.jpg)

The result_position shows how the new three variables explain the origin dataset for the ability on every position('CF''CDM','ST','LW','CM','RWB')
![graph](https://github.com/YahanCU/Project-for-tools/blob/master/images/pca_0.jpg)

  
●	Step4:
Results are shown below: 
First: [Volleys, FInishing, Longshots, Penalties…] All of these performance attributes are associated with Attack. 
Second: [Sliding tackle, Standing tackle, Interception…] All these performance attributes are associated with Defend.
Based on these two graphs, we summarize them as the Attack_Defence. The left picture is the original variables which have positive effects for this, the right one is the variables that have a negative effect on this. 
![graph](https://github.com/YahanCU/Project-for-tools/blob/master/images/pca_2.jpg)


●	Step5:
This step takes one parameter:
Ø  Position (eg:'RB','LM','RM','CF','CDM','ST','LW','CM','RWB')
Output shows what abilities a good player should have in that position. 
For the result below, we can see a high positive degree of Attack_Defence(towards Attack), meaning Attack is the key to a good CF. Also negative dribble-accuracy(towards Accuracy) meaning accuracy is the key to a good CF. 
![graph](https://github.com/YahanCU/Project-for-tools/blob/master/images/pca_3.jpg)

 
## Bibliography:
### Libraries:
Ø  numpy
Ø  pandas
Ø  plotly
Ø  seaborn
Ø  json
Ø  matplotlib
Ø  itertools
Ø  sklearn
Ø  IPython
Ø  string
Ø  re
 
### Websites:
http://www.soccer-training-guide.com/soccer-formations.html#.XAHCHpNKjEp
https://blog.csdn.net/LULEI1217/article/details/49386295 
https://scikit-learn.org/stable/auto_examples/linear_model/plot_ols.html 
https://docs.scipy.org/doc/numpy/reference/generated/numpy.polyfit.html
