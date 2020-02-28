# Predicting Views for Snapchat Ads Based On Spending and Country Targeted
For my linear regression models, I chose to look at the open data on Snapchat political ads. My simple regression model used Amount spent by advertiser over current campaign in US dollars (USD$) as the independent variable and Number of ad views by Snapchatters as the dependent variable. The VLOOKUP function was used to convert all non-USD currency amounts to USD. A scatterplot showed, not unexpectedly, a positive relationship between the two variables.

## Simple Linear Regression Model
![](Images/Original%20Visualization.PNG)

### Table used to convert Amount spent to USD$
image

R-squared was BLANK, indicating BLANK. Standard error was BLANK, indicating ?? The coefficient for Amount spent was BLANK, with a p-value of BLANK, indicating BLANK. F significance was BLANK, indicating BLANK.
Overall, CONCLUSIONS.
Below, I've provided a zoomed-in version of the simple regression model, excluding all outliers, to better model the relationship.

### Simple Linear Regression Model Less Outliers
![](Images/Visualization%20less%20Outliers.PNG)

My multiple regression model also used Number of views as the dependent variable. The independent variables were Amount spend by advertisers and Country of views. The VLOOKUP function was used to convert all currency amounts to USD$, exactly as in the simple regression model, and also to match each country targeted with a unique one- or two-digit code. The codes were assigned to countries alphabetically.

## Multiple Linear Regression Model
image

### Table of Country Codes Assigned Alphabetically
image

R-squared was BLANK, indicating BLANK. Standard error was BLANK, indicating ?? The coefficient for Amount spent was BLANK, with a p-value of BLANK, indicating BLANK. The coefficient for Country of views was BLANK, with a p-value of BLANK, indicating BLANK. F significance was BLANK, indicating BLANK.

I was also curious to see what effect it would have to assign the countries codes on the basis of GDP per capita, rather than alphabetically. To this end, I matched GDP per capita in 2018 to each country in the dataset, using open data from the World Bank. 2018 was used because 2019 data is not yet available. Additionally, it felt more appropriate to use financial data that would correspond to the beginning of 2019 when discussing advertising spending over that year.
Next, I assigned the lowest country code, 1, to India, the country with the lowest GDP per capita. The highest code, 27, went to Switzerland, with the highest GDP per capita.

### Table of Country Codes Assigned by GDP per Capita
image

I anticipated such a change to result in a positive coefficient for Country of views, indicating a positive relationship between a country's wealth, as measured in GDP per capita, and the Number of ads viewed by Snapchatters. I hypothesized such a relationship would be positive because wealthier countries tend to have more advanced cellular and internet infrastructures, which would make those countries a more likely audience for Snapchat-based advertising.
However, the coefficient for Country of views remained negative and its absolute value ??barely?? changed from BLANK to BLANK. Although it remained low enough to be statistically significant, the p-value actually increased from BLANK to BLANK, indicating that there is less statistical confidence in the new coefficient than the old one.

### Multiple Linear Regression Model with Country Codes Assigned by GDP per Capita
image

Furthermore, R-squared was BLANK, indicating BLANK. Standard error was BLANK, indicating ?? The coefficient for Amount spent was BLANK, with a p-value of BLANK, indicating BLANK. F significance was BLANK, indicating BLANK.
