# DataVisualisations

##Summary
This plot shows the Body Mass Index (BMI) of the top 100 Baseball players based on number of career home runs from a list of 1157 Major League Baseball players. The axes indicate the Home runs and BMI of the players. Data point are colored by ........(player’s handedness and the legend can be used to toggle between them). The plot also highlights.......(the players who are in ideal BMI range to show how BMI relates to the performance of a player).

##Design
####Exploratory Data Analysis using Plotly

The inital Baseball Udacity dataset included 1157 player entries and corresponding handedness, weight (in pounds), height (in inches) , batting average and number of Home Runs. I wanted to explore the relationship between these different variables to determine if there was a data driven reason behind successful baseball players, for this reason I decided to visualise my data using a scatter plot. I used Plotly to explore the inital data to see the relationship between Home Runs and a player's Batting Average:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BattingAvg(hand).png" width="800">  
  
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

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI%20(hand).png" width="800"> 

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI%20(BMI).png" width="800">  

Taking the above data and binning the rounded BMI values to show the average number of Home Runs for each BMI:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI(bins).png" width="800">

####Data Visualisations using dimple.js
Using dimple.js I plotted recreated a similar plot to the one I had sketched using plotly (index.html):

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis1.png" width="800">

The chart translated well into dimple however it was very busy and the colours didn't add anything so I decided to first encode the handedness of the Baseball player into the colour of the data points on the scatter plot as shown in index1.html :

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis2.png" width="800">

This started to convey a more coherant story of the Baseball data however I still felt the chart was too busy and so the real detail and message was getting lost. There were many players who never hit a single Home Run and therefore the chart was very busy along the x-axis without really telling us anything. I decided at this point to focus only on the top 100 Home Run hitters within the dataset, index2.html shows the updated chart:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis3.png" width="800">

The x-axis of the chart has been limited to BMI values between 20 and 30 to focus on the subset of the data. From this chart it was clear that the majority of the top 100 Baseball players ranked by career Home Runs were right handed with a BMI score of between 23 and 27. Finally I wanted to incorporate this interesting find at the start of my EDA on batting averages for the top Home Run hitters, index3.html shows the final chart:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis4.png" width="800">

This chart clearly shows that the all time greatest home run hitters in Baseball didn't have the best batting average, they consistently hit around 0.27. Despite there being a larger numnber of right handers in the top 100 home run hitters in Baseball the percentage of left handers is 32% which far exceeds the expected 10% of the population who are estimated to be left handed. The 7% of batters who use both hands is also much higher than would be expected for a sample population of 100.

##Feedback
After finishing my visualisation I asked three data analyst colleagues to look at my visualisation and provide feedback on what worked and what could be improved to make it a more effective visualisation.

####Interview 1
*"The chart would benefit from more interaction, you've achieved a walk through the data and I like the tooltip but my preference would be to have an interactive legend to highlight the groups more. Also I would remove the gridlines as it distracts from the chart."*

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/interview1.png" width="800">

####Interview 2
*"It's interesting to compare the BMI vs Run rate and previously you spoke about the BMI category ranges however these don't appear on the chart. It would be great it you could have this in the background so its clear which category each player is in."*

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/interview2.png" width="800">

####Interview 3
*"I really like the chart and the tooltip works well. Similar to the other two I would look to include info on the BMI categories and make the chart more interactive. Would be useful to tidy up the tooltip information and include a more informative title. Overall I think it's starting to look awesome!"*

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/interview3.png" width="800">

####Final Design and Summary 
My final baseball data visualisation was:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/final_chart.png" width="800">

51% of the top 100 Home Run hitters would be classed as Overweight according to their BMI score, with the other 49% in the normal weight category. A more helpful measure is that 85% of the top 100 Baseball players according to number of career Home Runs have a BMI score between 23 and 27.

39% of these top 100 baseball players have the ability to play with their left hand. This is a much higher percentage than would be expected from a random sample of the male population and highlights the impact of either playing left handed or having the ability to play baseball with either hand.

I chose to use colour to encode handedness as there were only three types so only a few colours needed to be used and it helped bring out the fact that there were more successful left handed baseball players than expected in this size sample. 

It was important to include batting average in the visualisation as there was an interesting bell curve relationship between it and the number of career home runs. The most effective batting average to maximise career home runs seemed to be around 0.27. Above this and the number of total home runs appeared to decrease, this could be due to having more hits of the ball of less power and consistently making base. Below this and the player might not hit enough balls consistently to have the opportunity to achieve a large number of career home runs. Using the bubble size to encode this variable helped communicate that the larger circles are not at the top of the chart and there a number of small circles high up on the home run count.


##Resources

I made use of the following resources during my project:

[Javascript Guide](https://google.github.io/styleguide/javascriptguide.xml)  
[Plotly](https://plot.ly/)  
[Dimple.js](http://dimplejs.org/)    
[How to calculate BMI](http://www.calcbmi.com/)    
[BMI category ranges](http://www.cancer.org/cancer/cancercauses/dietandphysicalactivity/bodyweightandcancerrisk/body-weight-and-cancer-risk-adult-bmi)    
[Article comparing BMI scores for top Baseball performers over past 100 years](http://valueoverreplacementgrit.com/2011/04/26/baseball-and-the-bmi/)  
[CSS font stack](http://www.cssfontstack.com/)  
[Article on Handedness](https://en.wikipedia.org/wiki/Handedness)  

