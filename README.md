# Udacity Data Visualisations Project

##Summary

This plot shows the Body Mass Index (BMI) of the top 100 Baseball players based on number of career home runs from a list of 1157 Major League Baseball players. The axes indicate the Home runs and BMI of the players. Data points are coloured by BMI and the legend can be used to toggle between them. The trend line shows the average number of home runs for each BMI value.

##Design
####Exploratory Data Analysis using Plotly

The initial baseball dataset included 1157 player entries and corresponding handedness, weight (in pounds), height (in inches), batting average and number of home runs. I wanted to explore the relationship between these different variables to determine if there was a data driven reason behind successful baseball players, for this reason I decided to visualise my data using a scatter plot. I used Plotly to explore the initial data to see the relationship between home runs and a player's batting average:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BattingAvg(hand).png" width="800">  
  
This initial plot suggested a skewed bell curve with an optimal batting average of between 0.25-0.28 to maximise the number of home runs. This made me want to find out how the other features in the data affected career home runs and whether I could determine optimal features for a baseball player. Rather than using height and weight as independent features I decided to use the BMI number for each player. The BMI is a calculation used to determine the level of body fat, and helps to determine the overall fitness of an individual. Much research has been conducted into the importance of BMI on sporting performance so I wanted to explore what impact the BMI level had on performance in baseball. To calculate BMI I used:

**BMI** = (**weight**(in kilograms)/**height**(in metres))/**height**(in metres)  

The following table listed the BMI weight groups for men who were aged 20 years or older:  

| Category      | BMI range         |
|---------------|:-----------------:|  
| Underweight   | BMI < 18.5        |  
| Normal weight | 18.5 > BMI < 24.9 |  
| Overweight    | 25 > BMI < 29.9   |  
| Obese         | BMI > 30          |  
  
I added a *BMI* column to my data which contained the result of the above formula or each baseball player as well as a *BMI category* column which provided the name of the category each BMI value corresponded to. The following chart compared Home Runs vs BMI:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI%20(hand).png" width="800"> 

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI%20(BMI).png" width="800">  

Taking the above data and binning the rounded BMI values I was able to show the average number of home runs for each BMI value:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/HR.vs.BMI(bins).png" width="800">

####Data Visualisations using dimple.js
Using dimple.js I recreated a similar plot to the one I had sketched previously using plotly. This plot is contained within index.html:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis1.png" width="800">

The chart translated well into dimple however it was very busy and the colours didn't add anything so I decided to first encode the handedness of the baseball player into the colour of the data points on the scatter plot as shown in index1.html:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis2.png" width="800">

This started to convey a more coherent story of the baseball data however I still felt the chart was too busy and so the real detail and message was getting lost. There were many players who never hit a single home run and therefore the chart was very busy along the x-axis without really telling us anything. I decided at this point to focus only on the top 100 home run hitters within the dataset, index2.html showed the updated chart:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis3.png" width="800">

The x-axis of the chart has been limited to BMI values between 20 and 30 to focus on the subset of the data. From this chart it was clear that the majority of the top 100 baseball players ranked by career home runs were right handed with a BMI score of between 23 and 27. Finally I wanted to incorporate the interesting find at the start of my EDA on batting averages for the top home run hitters, index3.html displayed the final chart:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/dimpleVis4.png" width="800">

This chart clearly shows that the highest home run hitters in this dataset didn't have the best batting average, instead they consistently hit around 0.27. Despite there being a larger number of right handers in the top 100 home run hitters in baseball the percentage of left handers was 32% which far exceeded the expected 10% of the population who are estimated to be left handed. The 7% of batters who used both hands was also much higher than would be expected from a sample population of 100.

##Feedback
After finishing my baseball data visualisation I asked three Data Analyst colleagues to look at my visualisation and provide feedback on what worked and what could be improved to make it a more effective visualisation.

####Interview 1
*"The chart would benefit from more interaction, you've achieved a walk through the data and I like the tooltip but my preference would be to have an interactive legend to highlight the groups more. Also I would remove the gridlines as it distracts from the chart."*

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/interview1.png" width="800">

####Interview 2
*"It's interesting to compare the BMI vs Run rate and previously you spoke about the BMI category ranges however these don't appear on the chart. It would be great it you could have this in the background so its clear which category each player is in."*

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/interview2.png" width="800">

####Interview 3
*"I really like the chart and the tooltip works well. Similar to the other two I would look to include info on the BMI categories and make the chart more interactive. Would be useful to tidy up the tooltip information and include a more informative title. Overall I think it's starting to look awesome!"*

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/interview3.png" width="800">

####Udacity Reviewer feedback
*"I look at the final visualization first before the README file, code or past iterations. Even though the chart is well designed and encoded, on its own, the visualization is more exploratory than explanatory; it allows the chart reader to explore the statistics of the top 100 players in the data set, but it isn't really showing a specific trend or explaining some sort of conclusion made after analyzing the data.*

*I see big circles and small circles at all ranges on the y-axis. Looking at the tooltip, by process of elimination, circle radius is probably encoded to batting average although that isn't stated on the chart.*

*Circle radius was encoded linearly to the batting average variable and then the limits on the variable were overridden in the code. A batting average of 0.24 looks tiny compared to a batting average of 0.28, which is misleading. The bigger circle looks about 10 times larger than the smaller circle, so the larger circle should map to a value of about 2.4 rather than 0.28. Circle radius should be encoded to the square root of the variable so that doubling the value doubles the area."*

####Final Design and Summary 
My final baseball data visualisation was:

<img src="https://github.com/Bonz07/DataVisualisations/blob/master/images/final_chart.png" width="800">

I decided to focus the final chart on the finding that the average career Home Runs increases with BMI. The earlier exploratory chart showed this trend and I wanted to explore this further. Focusing on the top 100 home run hitters reduced the prominance of this change but did allow me to look at similar players to see whether the positive relationship remains.

The final chart also shows that as BMI increases average home runs also increase. This could be explained by the players with a larger BMI having a greater power ratio increasing the chances of a successful hit resulting in a home run. As seen earlier in the EDA a large number of the players have a similar batting average meaning that something like BMI might make the difference between a good and a great home run hitter.  

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

