# Predicting Impressions for Snapchat Ads Based On Spending and Country Targeted
For my linear regression models, I chose to look at the open data on Snapchat political ads. My simple regression model used Amount spent by advertiser over current campaign in US dollars (USD$) as the independent variable and Number of ad views ("impressions") by Snapchatters as the dependent variable. The VLOOKUP function was used to convert all non-USD currency amounts to USD. A scatterplot showed, not at all unexpectedly, a positive relationship between the two variables.

## Simple Linear Regression Model
![](Images/Original%20Visualization.PNG)

### Table used to convert Amount spent to USD$
![](Images/Currency_Conversion_Table.PNG)

R-squared was 0.7086, indicating that 70.86% of the variation in Number of views was explained by variation in Amount spent, a fairly strong relationship. Standard error was 2.89E6. The coefficient for Amount spent was 343.46, with a p-value of 0, suggesting extremely high confidence in the significance of the coefficient. This was supported by an F significance equivalent to zero.
Overall, these stats support my hypothesis that there would be a strong positive relationship between Amount Spent and Number of views.
Below, I've provided a zoomed-in version of the simple regression model, excluding all outliers, to better model the relationship.

### Simple Linear Regression Model Less Outliers
![](Images/Visualization%20less%20Outliers.PNG)

My multiple regression model also used Number of views as the dependent variable. The independent variables were Amount spend by advertisers and Country of views. The VLOOKUP function was used to convert all currency amounts to USD$, exactly as in the simple regression model, and also to match each country targeted with a unique one- or two-digit code. The codes were assigned to countries alphabetically.

## Multiple Linear Regression Model
![](Images/Multiple_Lin_Reg_Orig.PNG)

### Table of Country Codes Assigned Alphabetically
![](Images/Orig_Country_Codes.PNG)

Adjusted R-squared was 0.84239, indicating a strong relationship between the independent and dependent variables. Standard error was 2.89E6, as before. The coefficient for Amount spent was 343.64, with a p-value of 0, indicating extremely high statistical confidence. The coefficient for Country of views was -21,108.812, with a p-value of 0.00046, indicating a strong relationship with Number of views than Amount spent. Significance F was 0.

I was also curious to see what effect it would have to assign the countries codes on the basis of GDP per capita, rather than alphabetically. To this end, I matched GDP per capita in 2018 to each country in the dataset, using open data from the World Bank. 2018 was used because 2019 data is not yet available. Additionally, it felt more appropriate to use financial data that would correspond to the beginning of 2019 when discussing advertising spending over that year.
Next, I assigned the lowest country code, 1, to India, the country with the lowest GDP per capita. The highest code, 27, went to Switzerland, with the highest GDP per capita.

### Table of Country Codes Assigned by GDP per Capita
![](Images/Country_Codes_GDP.PNG)

I anticipated such a change to result in a positive coefficient for Country of views, indicating a positive relationship between a country's wealth, as measured in GDP per capita, and the Number of ads viewed by Snapchatters. I hypothesized such a relationship would be positive because wealthier countries tend to have more advanced cellular and internet infrastructures, which would make those countries a more likely audience for Snapchat-based advertising.
However, the coefficient for Country of views remained negative and its absolute value changed very little from -21,108.812 to -26,377.22. Although it remained low enough to be statistically significant, the p-value actually increased from 0.00046 to 0.00329, indicating that there is less statistical confidence in the new coefficient than the old one, although it remains statistically significant.

### Multiple Linear Regression Model with Country Codes Assigned by GDP per Capita
![](Images/Multiple_Lin_Reg_GDP.PNG)

Furthermore, Adjusted R-squared was 0.7092, indicating a weakened relationship between the independent and dependent variables. Standard error was 2.89E6, as before. The coefficient for Amount spent was nearly the same, at 343.62, with a p-value once again of zero. Significance F was also zero once again. Altogether, this indicates that the independent and dependent variables have an clearly strong relationship, irregardless of data manipulations.
