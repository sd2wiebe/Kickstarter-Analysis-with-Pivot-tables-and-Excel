# Kickstarter Analysis

## Overview of Project 
The purpose of this analysis is to filter and visualize data that will help Louise launch a successful fundraising campaign for her play, “Fever”. To aid Louise, I have utilized data points from successful and unsuccessful Kickstarter campaigns similar to hers, in order to give insight on the specific factors that might contribute to success or failure. 

## Analysis and Challenges

### Analysis of Outcomes based on Launch Date
For this analysis I was able to use a large data set of Kickstarter campaigns with many variables, including: Goal amount, Launch Date, Outcome, Country, Category and Subcategory, and more. The first thing I did was created a pivot table to summarize the data points I was interested in. I wanted to see if there was any correlation between the month of ‘Launch Date’ and whether the campaign was successful or not. However, the data produced was still too vague, so I filtered the data in the pivot table to only show campaigns more similar to Louise’s. For this, I filtered to show only the data with subcategory “Theater” and based out of the United States. Thus, I was able to create this [pivot table.](https://github.com/sd2wiebe/Kickstarter-Analysis-1/blob/main/Pivot%20Table.png)
From the data in the pivot table, I created a line chart to visualize the relationship: 

<p align="center"

![alttext](https://github.com/sd2wiebe/Kickstarter-Analysis-1/blob/main/Theater_Outcomes_vs_Launch.png)

</p>
We can see that the biggest gap between successful campaigns and failed campaigns occurs in May and carries over into June. To further clarify this relationship, I made a new column that displays the percentage of successful campaigns for each month, along with the mean:

<p align="center"

![alttext](https://github.com/sd2wiebe/Kickstarter-Analysis-1/blob/main/Launch%20Success%20percentages.png)

</p>
We can see from the data that the highest success rate occurs in May at 66.87%, and the next highest rate isn't far off at 65.36% in June. It is worth noting that those months also have the largest amount of data points, May: 166, and June: 153. Conversely, December has the lowest amount of campaigns launched (75), and the lowest success rate by far at 49.33%. 

### Challenges

A challenge proposed during this analysis was that the data set only had one column that displayed both category and subcategory. In order to filter for “Theater” in my pivot table I would need to create two columns, ‘Parent Category’ and “Subcategory”. I was able to do this by using the ‘Convert texts to Columns Wizard” to extract the parent category and the subcategory into new columns respectively. 

### Analysis of Outcomes Based on Goals

Using the same Kickstarter data, I was able to look at the fundraiser goal amount and how it might be correlated with a successful or unsuccessful outcome. To do this I broke up the goal amounts into 12 ranges:
<p align="center"

![alttext](https://github.com/sd2wiebe/Kickstarter-Analysis-1/blob/main/Goal%20Range.png)
</p>

Then I wanted to populate columns that totaled the number of successful kickstarter campaigns that had the subcategory “plays” for each goal range. In order to populate the columns “Number Successful”, “Number Failed” etc. I had to use the =countifs() function for each goal range. For example this is the formula used to populate the cell corresponding to “Number Successful” in the “<1000” goal range:
```
=COUNTIFS('Kickstarter Data'!$D:$D,"<1000",'Kickstarter Data'!$F:$F,"successful",'Kickstarter Data'!Q:Q,"plays")
```
I ran a similar formula for the “Number Failed” column, and then used ```Sum()``` to populate the total projects column in order to create columns for “Percentage Successful” and “Percentage Failed. From [this table](https://github.com/sd2wiebe/Kickstarter-Analysis-1/blob/main/Goals%20Percentage%20Table.png) I created a line graph:
<p align="center"

![alttext](https://github.com/sd2wiebe/Kickstarter-Analysis-1/blob/main/Outcomes_vs_Goals.png)
</p>








