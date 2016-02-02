# DataVisualisations

###Summary
This plot shows the Body Mass Index (BMI) of the top 100 Baseball players based on number of career home runs from a list of 1157 Major League Baseball players. The axes indicate the Home runs and BMI of the players. Data point are colored by ........(player’s handedness and the legend can be used to toggle between them). The plot also highlights.......(the players who are in ideal BMI range to show how BMI relates to the performance of a player).

###Design
The inital Baseball Udacity dataset included 1157 player entires and corresponding handedness, weight (in pounds), height (in inches) , batting average and number of Home Runs. I used Plotly to explore the data:



The Body Mass Index (BMI) is a calculation used to determine the level of body fat. It helps to determine the overall fitness of an individual. Much research has been conducted into the importance of BMI on sporting performance so I wanted to explore what impact the BMI level had on performance in Baseball. To calculate BMI I used:

**BMI** = (**weight**(in kilograms)/**height**(in metres))/**height**(in metres)  

  
The following table contains the BMI weight groups for men who are aged 20 years or older:  

| Category      | BMI range         |
|---------------|:-----------------:|  
| Underweight   | BMI < 18.5        |  
| Normal weight | 18.5 > BMI < 24.9 |  
| Overweight    | 25 > BMI < 29.9   |  
| Obese         | BMI > 30          |  
  
I added a *BMI* column to my data which contained the result of the above formula or each Baseball player as well as a *BMI category* column which provided the name of the category each BMI value corresponded to. 

Overall trends (home runs vs binned BMI)  
1st data visualisation using dimple.js  
Top 100 players using dimple.js  
version 2  
version 3  

###Feedback
Interview 1 text and changes to vis  
Interview 2 text and changes to vis  
Interview 3 text and changes to vis  
Final Visualisation and Summary of findings  

###Resources
I made use of the following resources during my project:

[Javascript Guide](https://google.github.io/styleguide/javascriptguide.xml)  
[Plotly](https://plot.ly/)  
[Dimple.js](http://dimplejs.org/)    
[How to calculate BMI](http://www.calcbmi.com/)    
[BMI category ranges](http://www.cancer.org/cancer/cancercauses/dietandphysicalactivity/bodyweightandcancerrisk/body-weight-and-cancer-risk-adult-bmi)    
[Article comparing BMI scores for top Baseball performers over past 100 years](http://valueoverreplacementgrit.com/2011/04/26/baseball-and-the-bmi/)  
