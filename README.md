Team name: I love coding
Team members: Yahan Hu, Chenchen He, Lili Yan, Shipei Feng
 
Introduction:
The growing interests in soccer and FIFA drive the creation of our project.   Our project provides a well-rounded library presenting summarized statistics and analysis by extracting player personal attributes, player performance attributes, and ratings at all positions. User interaction and data visualization enable users to customize their questions and find answers out of our project. In general, our project is further separated into 4 parts that bring different insights about FIFA to users.
 
Part I: Find the best Squad (User Interaction)
This section is to find out the best squad given selected information by users.  
 
Part II: Player/Country/Club comparisons (User Interaction)
This part is used to compare different players, clubs, and countries regarding their age, current overall rating, potential rating and value.  The comparison can further extend to players’ specific skills.
 
Part III: Help determine whether it is worthwhile to buy a player or not (User Interaction)
The aim of this part is to give a suggestion when considering buying a certain player. First, plot the trend between two factors: age and score (overall and potential), and mark out the point of the player user want to know, help to figure out which stage the player is at. Then, do multiple linear regression to find out the relationship between response variable: value and explanatory variables: age and potential score. After that, separately polyfit value and three factors: age, overall score, and potential score , then use the regression coefficients to help decide the certain player is worth buying or not. Finally, use the same process to find out 10 players who has high performance-value ratio with highest overall scores, they are most worth buying.
 
Part IV: Since there are too many data to estimate the ability of players, we want to reduce the dimensions and sum up these data to 4 abilities that a soccer player should have. Also, use the new variables to explain the original dataset and show which is the most important ability that a certain position player should have. We use Principal components analysis to solve this problem.
 
Data Description:
 
 
 
 
 
 Run instruction:
 
Part I:
The goal of this section is to find the best Squad (including player’s name, preferred position, overall rate, nationality, and club), given the selected information. The performance is measured by the overall rating.
 
·      Find the best Squad given the selected formation among all players.
The program takes one parameter:
Ø  Formation (eg. 433, 424, 442, 343, 451)
The best Squad for the formation user chose is predicted by the program showing below:
·      Find the best Squad for different formation given the selected country.

This program takes one parameter:
Ø  Country/Nationality (eg. Brazil, Spain, Germany etc.)
The best Squads for different formations are listed below given the selected country.
·      Find the best Squad for different formation given the selected club.
      This program takes one parameter:


Ø  Club (eg. Manchester United, Manchester City, Juventus etc.)
       The best Squads for different formations are listed below given the selected country.
 
 

 
 
 
 
Part II:
This part is used to compare different players, clubs and countries regarding of their age, current overall rating, potential rating and value.  The comparison can further extend to players’ specific skills.
·      Compare two players. This program is designed to present the comparison between two FIFA players in terms of their age, overall rating, potential rating, value and skill sets.
This program takes two parameters:
Ø  Two player names (eg. Cristiano Ronaldo, Neymar)


        	
·      Compare two clubs.
This portion is created to compare two different clubs regarding of their average age, average overall rating, average potential rating, value and skillsets.
This program takes two parameters:
ØTwo club’s name (eg. Paris Saint-Germain,FC Barcelona)


 
·      Compare two countries.
This portion is created to compare two different countries regarding of their average age, average overall rating, average potential rating, value and skillsets.
This program takes two parameters:
ØTwo countries (eg. Germany, France)


 
Part III:
The aim of this part is to plot the trend between two factors
·      Find the trend between factors and rating (overall and potential)
This program takes one parameter
Ø  Player name (eg. A. Aseri)
 
Part IV:
Step1: 
This step we calculate the mean of dataset group by the position. 
For this step just run the cell.
Step2:
Draw the graph of Cumulative Variance to decide how many new variables should we choose. From the result, we can see that 4 is the best number. 

Step3:
Use the PCA model to reduce the dimension of the dataset. The result_position show how the new four variables replace the original variables. 

The picture below is the relationship between the new variables and the original variables.
 
Step4:
We visualize the result.  
First: [Volleys, FInishing, Longshots, Penalties…] All of these data are related to attack so that this is the ability of Attack. 
Second: [Sliding tackle, Standing tackle, Interception…] All these are related to defense, so this is the ability to Defend.
This two are the picture about the second new variables and we summarize it as Attack_Defence. The left picture is the original variables which have positive effects for this, the right one is the variables that have a negative effect on this. 


 Step5:
You can input the position you are interested in, and the output is a graph, that shows what abilities a good player should have in that position. 
For the result below, we can see that the Attack_Defence, it is really big for positive, which means the attack is really important, also, special and accuracy physical fitness is important for a player at the center forward position. 
The input could be 'RB','LM','RM','CF','CDM','ST','LW','CM','RWB','CB','LWB','RW','CAM','LB'

Bibliography:
Libraries:
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
 
Websites:
http://www.soccer-training-guide.com/soccer-formations.html#.XAHCHpNKjEp
 
 

