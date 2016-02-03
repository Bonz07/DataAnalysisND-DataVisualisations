# DataVisualisations

##Summary
This plot shows the Body Mass Index (BMI) of the top 100 Baseball players based on number of career home runs from a list of 1157 Major League Baseball players. The axes indicate the Home runs and BMI of the players. Data point are colored by ........(player’s handedness and the legend can be used to toggle between them). The plot also highlights.......(the players who are in ideal BMI range to show how BMI relates to the performance of a player).

##Design
####Exploratory Data Analysis using Plotly

The inital Baseball Udacity dataset included 1157 player entries and corresponding handedness, weight (in pounds), height (in inches) , batting average and number of Home Runs. I used Plotly to explore the inital data to see the relationship between Home Runs and a player's Batting Average:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BattingAvg(hand).png" width="600">  
  
This initial plot suggested a skewed bell curve with an optimal batting average between 0.25-0.28 to maximse the number of home runs. This made me want to find out how the other features in the data affected Home Runs and whether I could determine optimal features for a Baseball player. Rather than using height and weight as independant features I decided to use the BMI number for each player. The Body Mass Index (BMI) is a calculation used to determine the level of body fat, and helps to determine the overall fitness of an individual. Much research has been conducted into the importance of BMI on sporting performance so I wanted to explore what impact the BMI level had on performance in Baseball. To calculate BMI I used:

**BMI** = (**weight**(in kilograms)/**height**(in metres))/**height**(in metres)  

The following table contains the BMI weight groups for men who are aged 20 years or older:  

| Category      | BMI range         |
|---------------|:-----------------:|  
| Underweight   | BMI < 18.5        |  
| Normal weight | 18.5 > BMI < 24.9 |  
| Overweight    | 25 > BMI < 29.9   |  
| Obese         | BMI > 30          |  
  
I added a *BMI* column to my data which contained the result of the above formula or each Baseball player as well as a *BMI category* column which provided the name of the category each BMI value corresponded to. The following chart compares Home Runs vs BMI:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI%20(hand).png" width="600"> 

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI%20(BMI).png" width="600">  

Taking the above data and binning the rounded BMI values to show the average number of Home Runs for each BMI:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI(bins).png" width="600">

####Data Visualisations using dimple.js
Using dimple.js I plotted recreated a similar plot to the one I had sketched using plotly (index.html):

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis1.png" width="600">

The chart displayed.......  
- change colouring to reflect handedness (index1.html)
- focus on top 100 players based on home runs (index2.html)

##Feedback
After finishing my visualisation I asked three data analyst colleagues to look at my vicualisation and provide feedback on what worked and what could be improved to make it a more effective visualisation.

####Interview 1
-change size based on batting average
-remove gridlines

####Interview 2
-add in BMI ranges in background of chart
-improve data in hover over

####Interview 3
-make more interactive using clickable legend

####Final Design and Summary 
Final Visualisation and Summary of findings  

##Resources

I made use of the following resources during my project:

[Javascript Guide](https://google.github.io/styleguide/javascriptguide.xml)  
[Plotly](https://plot.ly/)  
[Dimple.js](http://dimplejs.org/)    
[How to calculate BMI](http://www.calcbmi.com/)    
[BMI category ranges](http://www.cancer.org/cancer/cancercauses/dietandphysicalactivity/bodyweightandcancerrisk/body-weight-and-cancer-risk-adult-bmi)    
[Article comparing BMI scores for top Baseball performers over past 100 years](http://valueoverreplacementgrit.com/2011/04/26/baseball-and-the-bmi/)  
