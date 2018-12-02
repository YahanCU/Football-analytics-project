# Exploration in 2018 FIFA Player Library
### Team: I love coding
### Members: Yahan Hu, Chenchen He, Lili Yan, Shipei Feng
 
## Introduction:
The growing interests in soccer and FIFA drive the creation of our project. Our project provides a well-rounded library presenting summarized statistics and analysis by extracting player personal attributes, player performance attributes, and ratings at all positions. User interaction and data visualization enable users to customize their questions and find answers out of our project. In general, our project is further separated into 4 parts that bring different insights about FIFA to users.
 
### Part I: (User Interaction): 
#### < Find the best squad for each formation in terms of players, clubs, countries >
This section is to find out the best squad given selected information by users. Users choices include formation type, nationality, and club. 
 
### Part II: (User Interaction):
#### < Compare the performance between two players, two clubs or two countries >
This part is aimed to compare different players, clubs, and countries in several aspects, like age, value, potential, and skills. The part also extends to provides all simple predictions of game results based on two clubs’ (or countries’) five formations. The comparison results are mainly presented in two graphs and one table. 

### Part III: (User Interaction):
#### < Measure a player’s value aligned with multiple factors >
This portion is designed to give users some insights about a player’s value(€) with associated impacting factors and a player’s value(€) position within the whole FIFA. We use a line chart to plot a relationship between age and score for a individual player. We also create linear regression models to predict the correlation between value(€) and three different factors(Age, Overall rating, Potential rating) among the whole FIFA, which is further used to spot a individual player’s position the user chose.   

### Part IV: (User Interaction)
#### < Find required ability for every position >
This part offers our users some understanding about what important abilities each group of positions require based on the current FIFA registered players. To clearly and visually present our result, we use principal components analysis that reduces the dimensions and sum up these data to 4 abilities that a soccer player should have.
 
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
https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/Part1-1.png
 
This table shows the best Squad you can get under the formation you chose based on a player’s overall performance. This information could give you some insights about top individual player’s overall skills. 

●	Find the best Squad for different formation given the selected country.
This program takes one parameter:
Ø  Country/Nationality (eg. Brazil, Spain, Germany etc.)
The best Squads for different formations are listed below given the selected country.
https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/Part1-2.png
https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/Part1-3.png
https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/Part1-4.png
  
This table shows the best Squad you can get under different formations within one country. This information is able to offer you some guidance about players’ selection under specific formation or compare overall performances between formations. 

●	Find the best Squad for different formation given the selected club.
      This program takes one parameter:
Ø  Club (eg. Manchester United, Manchester City, Juventus etc.)
       The best Squads for different formations are listed below given the selected country.
https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/Part1-6.png
https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/Part1-7.png
  
This library provides a list of players under different formations within one club. The information can be used to provide you with some insights about players’ selections within a club and comparisons between different formations.  
 
 
 
### Part II (User Interaction):
#### < Compare the performance between two players, two clubs or two countries >
This part is used to compare different players, clubs, and countries in several aspects.
●	First, we can compare any two players by function player_compare().
This function will require input at first. Following the hint("Enter two players' names you want to compare(separated by ',')), the function will automatically extract parameters:
Ø  Two player names (eg. Cristiano Ronaldo, Neymar)
Then the result includes two graphs, bar chart and radar graph as following:
 
        	
●	Second, we can compare any two clubs by function club_compare().
This function will require input at first. Following the hint("Enter two clubs' names you want to compare(separated by ',')), the function will automatically extract parameters:
Ø Two club’s name (eg. Paris Saint-Germain, FC Barcelona)
Then the result includes one prediction table and two graphs, bar chart and radar graph as following.
 

 
●	Finally, we can compare any two countries by function country_compare().
This function will require input at first. Following the hint("Enter two countries’' names you want to compare(separated by ',')), the function will automatically extract parameters:
ØTwo countries (eg. Germany, France)
Then the result includes one prediction table and two graphs, bar chart and radar graph as following.
 
 
### Part III (User Interaction):
#### < Measure a player’s value aligned with multiple factors >
The aim of this part is to measure players’ value aligned with multiple factors, and spot certain player’s position in the whole FIFA from different angles.

●	 Find the relationship between age and rating (overall score and potential score) by function Age_Score()
This program takes one parameter
Ø  Player name (eg. A. Aseri)
 ![Age_Score](https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/1.png)
The curve shows the trend of scores changes along with age. It can be clearly seen that potential score decreases slowly with age, while overall score increases with age, and the two scores stay equal after  30 years old, indicating the player almost reaching out to his career peak. After 35 years old, the whole score of the player decreases significantly, which fits the athlete's life cycle.
The star-shaped points represent the overall and potential score of the player user wants to know. Take A. Aseri as an example, his potential and overall score are both higher than the mean, and the difference is large, showing he has better performance than his peer’s and has great potential for growth.

●	 Linear Regression
This function regression() has no input, the result is shown in the image and table.
 ![regression](https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/2.png)
Using the multiple linear regression, we have an equation describes the relationship between value and two factors: value = 0.6463 potential + 0.2336 age - 0.0015.
As shown in the 3-dimensional plot, after removing the high value of star players, the regression fits the real scatters. In the scale of [-4,3], the minimum mean square of 0.7828 is small enough to assert this regression is accurate.

●	The decision of a certain player
Help your decision on whether buying a player or not using the function Value().
This program takes one parameter
Ø  Player name (eg. Pepe)
 ![Value](https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/3.png)
The output includes three pictures and two tables.
The upper picture shows the polyfitting curve of age and value, blue scatters are the median value of each age group. Input “Pepe”, the yellow dotted line means at Pepe’s age (34), the polyffting median value is about €600,000. The following two figures are the same, and the only difference is the x-axis changes to overall score and potential score.
The first table contains basic information of “Pepe”, especially showing the difference of his real value and the median value. 
The second table shows the decision we make, after calculating we find he is worth buying.


●	10 worth-buying players
This function worthbuy()  has no input.
 ![worthbuy](https://github.com/YahanCU/Project-for-tools/blob/master/image_yll/4.png)
The output is a single table, containing information of 10 most worth-buying players. Among all worth-buying players, their overall scores are the highest. The table is descending sorted by potential scores.

### Part IV:
#### < Find required ability for every position >
This part illustrates the most important abilities each group of positions require based on the current FIFA registered players. The final result is presented through the following process:
●	Step1: 
This step we calculate the mean of dataset group by the position. 
For this step just run the cell.
●	Step2:
Draw the graph of Cumulative Variance to decide how many new variables should we choose. From the result, we can see that 4 is the best number. 
 
●	Step3:
Use the PCA model to reduce the dimension of the dataset. The result_position show how the new four variables replace the original variables. 
 
The picture below is the relationship between the new variables and the original variables.
  
●	Step4:
Results are shown below: 
First: [Volleys, FInishing, Longshots, Penalties…] All of these performance attributes are associated with Attack. 
Second: [Sliding tackle, Standing tackle, Interception…] All these performance attributes are associated with Defend.
Based on these two graphs, we summarize them as the Attack_Defence. The left picture is the original variables which have positive effects for this, the right one is the variables that have a negative effect on this. 
 

●	Step5:
This step takes one parameter:
Ø  Position (eg:'RB','LM','RM','CF','CDM','ST','LW','CM','RWB')
Output shows what abilities a good player should have in that position. 
For the result below, we can see a high positive degree of Attack_Defence, meaning AD is the key to a good CF. Also special and accuracy physical fitness all have positive effects on  a good CF. 

 
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
 
 

